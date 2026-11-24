# AREA

Automation platform (IFTTT / Zapier style): an application server, a web client and an Android client.

| Part | Stack | Folder |
|------|-------|--------|
| Server | NestJS (TypeScript), MongoDB (Mongoose) | `server/` |
| Web client | Vue 3 + Tailwind CSS | `web/` |
| Mobile client | Flutter (Android) | `mobile/` |

## Run

```sh
cp .env.example .env
docker compose up --build
```

| Endpoint | URL |
|----------|-----|
| API | http://localhost:8080 |
| API docs (Swagger UI) | http://localhost:8080/api/docs |
| OpenAPI spec (JSON) | http://localhost:8080/api/docs-json |
| Web client | http://localhost:8081 |
| Android APK | http://localhost:8081/client.apk |

MongoDB runs as a single-node replica set (`rs0`) so that multi-document transactions are available.

## Develop

```sh
docker compose up -d mongo
cd server && npm ci && npm run start:dev   # :8080
cd web && npm ci && npm run dev             # :5173
cd mobile && flutter pub get && flutter run
```

## CI / mirroring

- `.github/workflows/ci.yml`: lint, test and build for server, web and mobile, plus `docker compose build`, on every PR and push to `main`.
- `.github/workflows/mirror.yml`: pushes `main` to the Epitech repository. Requires:
  - repository **variable** `MIRROR_URL`: the Epitech repo SSH URL (`git@github.com:EpitechPGE…/….git`)
  - repository **secret** `GIT_SSH_PRIVATE_KEY`: a private key whose public key is registered on an account with push access to that repo.

## Project management

Planning board: GitHub Project **AREA++** (milestones: Plan 01/12/2026, MVP 22/12/2026, Final 17/01/2027).
