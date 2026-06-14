# Кратко для HR

VMNorth.com — это не просто лендинг и не только визуальное портфолио. Это production-oriented full-stack проект: публичный мультиязычный сайт, страницы услуг и портфолио, форма проектного брифа, чат с посетителем, админ-панель, безопасная авторизация и подготовка к деплою.

## Что показывает проект

- Умение собрать продуктовый интерфейс от идеи до рабочей реализации
- Frontend на React, TypeScript и Vite
- Backend на Node.js
- Realtime-функции через Server-Sent Events
- Хранение данных в PostgreSQL и JSON runtime-файлах
- Админ-доступ через passkey, TOTP и recovery codes
- Админ-разделы для заявок, аналитики, audit log, content CMS, release CI, health и backup/retention
- Документацию, deployment flow, Docker и release checks

## Как сделан full stack

- Frontend: React, TypeScript, React Router, Vite, CSS Modules
- Backend: собственный Node.js HTTP server
- Realtime: Server-Sent Events для visitor/admin обновлений
- Database: PostgreSQL для чатов, сообщений, сессий и presence
- Runtime storage: защищённые JSON-файлы для briefs, portfolio, analytics, CMS, auth и audit log
- Files: persistent local storage или S3-compatible storage
- Email: Nodemailer и SMTP
- Security: passkey/WebAuthn, TOTP, recovery codes, secure cookies, rate limits и IP allowlist

## Как проект выложен

Production topology подготовлен для VPS:

```text
vmnorth.com
  -> Cloudflare DNS/proxy
  -> Caddy HTTPS reverse proxy
  -> Node.js container
  -> PostgreSQL + persistent runtime storage
```

Docker Compose запускает Caddy, Node.js и PostgreSQL. Node.js и база данных не публикуются напрямую в интернет. GitHub Actions проверяет security audit, lint, tests, TypeScript, production build, performance budgets и smoke tests. Отдельный workflow проверяет production URL каждые 30 минут.

## Как объяснять на интервью

Короткая формулировка:

> Built a multilingual React and Node.js product platform with real-time visitor chat, secure admin operations, saved brief review, local analytics, content management, portfolio publishing, Dockerized deployment, CI checks, and production documentation.

По-русски:

> Я сделал полноценную full-stack платформу для digital studio: мультиязычный React frontend, собственный Node.js backend, PostgreSQL, realtime-чат через SSE, passkey-first админку, аналитику, content CMS, Docker/VPS deployment через Caddy и Cloudflare, CI и production monitoring.

## Почему код не опубликован

Код не включен в публичный репозиторий намеренно. В проекте есть приватные production-детали, структура backend-логики, конфигурации и операционные материалы. Для HR и первичного отбора достаточно публичного портфолио: описания, скриншотов, архитектуры, стека и демо.

Формулировка для GitHub:

> Source code is not public because this project contains private implementation details and production configuration. This public repository is prepared for portfolio and hiring review.
