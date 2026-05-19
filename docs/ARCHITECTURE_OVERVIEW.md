# Architecture Overview

VMNorth.com is built as a single-origin product platform: the same production server serves the frontend, API routes, admin flows, chat endpoints, and health checks.

## System Shape

```text
Public website + Admin workspace
        |
        v
React / TypeScript / Vite frontend
        |
        v
Node.js HTTP server
        |
        +-- Static frontend delivery
        +-- Visitor chat API
        +-- Project brief submission
        +-- Admin authentication
        +-- Admin dashboard, analytics, content CMS, and portfolio publishing
        +-- Backups/retention, release CI, and system health APIs
        +-- Health/readiness endpoints
        |
        v
PostgreSQL + JSON runtime storage
```

## Frontend

The public frontend is organized around reusable route shells and page-specific content modules. This keeps the visible product flexible while avoiding repeated page chrome.

Main surfaces:

- Homepage and marketing sections
- About, pricing, services, and process pages
- Regional pages for Canada, the United States, and Europe
- Dynamic portfolio project pages
- Guided project brief flow
- App catalog and app-specific support/privacy pages
- Visitor support chat
- Admin workspace for inbox, briefs, analytics, client observability controls, content copy, health, release status, and portfolio publishing

## Backend

The backend uses a custom Node.js server rather than a purely static host. It handles operational features that need server-side behavior:

- Visitor chat session creation and restore
- Chat messages, typing state, and Server-Sent Events
- Email notifications and reply follow-up
- Project brief submission
- Admin login and account bootstrap
- Passkey, TOTP, and recovery-code flows
- Portfolio publishing and profile updates
- Saved brief review, local analytics summaries, client observability controls, content copy overrides, audit log, release CI status, and backup/retention reporting
- Health checks for deployment monitoring

## Data Boundaries

PostgreSQL is used for live operational data such as chat sessions, messages, admin sessions, and presence state.

JSON-backed runtime files are used for editable content and operational metadata that benefit from easy inspection and backup, such as portfolio content, saved briefs, local analytics, client observability settings, content copy overrides, admin profile data, auth metadata, and audit logs.

## Security Model

The admin surface is designed with production-oriented controls:

- Passkey-first authentication
- TOTP fallback
- One-time recovery codes
- Secure HTTP-only session cookies
- Optional IP allowlist for admin routes
- Auth audit logging
- Configurable WebAuthn relying-party settings for production domains

## Delivery Model

The project is designed for a Dockerized production deployment:

- Frontend build is served by the Node.js runtime
- API and frontend run on the same origin
- PostgreSQL runs as a separate service
- Persistent runtime files are mounted outside the container
- Caddy can sit in front of the app on a VPS
- Release checks cover linting, tests, type checks, production build, environment validation, and smoke checks
