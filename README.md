# VMNorth.com

**Multilingual digital product studio platform with public sales flows, real-time visitor communication, and a secure operating workspace.**

[Live website](https://vmnorth.com) · [Pricing](https://vmnorth.com/pricing) · [Project brief](https://vmnorth.com/brief) · [Selected work](https://vmnorth.com/work/brand-websites)

![VMNorth.com product overview](./screenshots/overview.png)

## Product

VMNorth.com is a production-oriented platform for presenting services, converting visitors into qualified leads, publishing project work, supporting app releases, and operating the business from an internal admin workspace.

The public experience supports English, French, Spanish, and Russian routes. The operational side includes visitor chat, saved project briefs, portfolio publishing, analytics summaries, content controls, release status, health monitoring, and account security.

## My Role

**End-to-end product ownership:** product structure, UX, visual system, frontend, backend APIs, persistence, authentication, localization, deployment, release verification, and engineering documentation.

## Core Stack

| Frontend | Backend | Data and realtime | Delivery |
| --- | --- | --- | --- |
| React, TypeScript, React Router, Vite | Node.js HTTP server | PostgreSQL, JSON content stores, Server-Sent Events | Docker, Docker Compose, GitHub Actions, smoke checks |

Additional implementation areas include CSS Modules, Three.js, SMTP notifications, WebAuthn passkeys, TOTP, recovery codes, secure cookies, and audit logging.

## Selected Screens

<table>
  <tr>
    <td width="50%">
      <strong>Commercial pricing surface</strong><br><br>
      <img src="./screenshots/pricing.png" alt="VMNorth pricing page">
    </td>
    <td width="50%">
      <strong>Guided project brief</strong><br><br>
      <img src="./screenshots/project-brief.png" alt="VMNorth guided project brief">
    </td>
  </tr>
  <tr>
    <td width="50%">
      <strong>Dynamic project presentation</strong><br><br>
      <img src="./screenshots/brand-websites.png" alt="VMNorth project case page">
    </td>
    <td width="50%">
      <strong>App release destination</strong><br><br>
      <img src="./screenshots/flipclock-display-product.png" alt="FlipClock Display release page">
    </td>
  </tr>
  <tr>
    <td width="50%">
      <strong>Public product experience</strong><br><br>
      <img src="./screenshots/homepage.png" alt="VMNorth homepage">
    </td>
    <td width="50%">
      <strong>Passkey-first admin access</strong><br><br>
      <img src="./screenshots/admin-login.png" alt="VMNorth admin sign-in">
    </td>
  </tr>
</table>

## Mobile Experience

Captured with a real mobile browser context at a `390 × 844` CSS viewport. Each page was verified with no horizontal document overflow.

<table>
  <tr>
    <td width="33%">
      <strong>Homepage</strong><br><br>
      <img src="./screenshots/mobile-home.png" alt="VMNorth mobile homepage">
    </td>
    <td width="33%">
      <strong>Pricing</strong><br><br>
      <img src="./screenshots/mobile-pricing.png" alt="VMNorth mobile pricing page">
    </td>
    <td width="33%">
      <strong>Project brief</strong><br><br>
      <img src="./screenshots/mobile-brief.png" alt="VMNorth mobile project brief">
    </td>
  </tr>
  <tr>
    <td width="33%">
      <strong>Selected work</strong><br><br>
      <img src="./screenshots/mobile-work.png" alt="VMNorth mobile project page">
    </td>
    <td width="33%">
      <strong>App release</strong><br><br>
      <img src="./screenshots/mobile-app.png" alt="VMNorth mobile app release page">
    </td>
    <td width="33%">
      <strong>Admin access</strong><br><br>
      <img src="./screenshots/mobile-admin.png" alt="VMNorth mobile admin sign-in">
    </td>
  </tr>
</table>

## Product Surfaces

- Public marketing routes for services, process, pricing, regions, and contact
- Dynamic portfolio pages backed by editable project content
- Guided brief intake for structured project discovery
- Visitor chat with session restore, attachments, typing state, presence, and follow-up
- App catalog with product, support, privacy, and privacy-choice routes
- Admin workspace for inbox, briefs, analytics, content, portfolio, releases, and system health

## Engineering Highlights

- Shared route shells keep navigation, localization, theme, support chat, and metadata consistent.
- The Node.js runtime serves the frontend and APIs from one origin.
- Server-Sent Events provide live visitor and admin updates without a third-party chat service.
- PostgreSQL stores operational data; inspected JSON stores support editable content and selected admin state.
- Admin authentication is passkey-first with TOTP and one-time recovery-code fallback.
- Release verification covers linting, tests, type checks, environment validation, production build, performance budgets, and smoke checks.

## System Shape

```mermaid
flowchart LR
    Visitor["Visitors"] --> Web["React + TypeScript"]
    Admin["Admin workspace"] --> Web
    Web --> Server["Node.js server"]
    Server --> Database[("PostgreSQL")]
    Server --> Content["Editable content stores"]
    Server --> Email["Email notifications"]
```

Detailed technical context is available in [Architecture Overview](./docs/ARCHITECTURE_OVERVIEW.md). A short interview walkthrough is available in [Demo Script](./docs/DEMO_SCRIPT.md).

## Source Code

This repository is intentionally presentation-only. Source code, production configuration, databases, credentials, logs, and private operational materials are not public.
