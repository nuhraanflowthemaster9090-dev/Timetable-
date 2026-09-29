# Base44 Dev Environment

## What this is
A single-file static web app (`index.html`) — a neon weekly timetable/life planner.
All HTML, CSS, and JS are inline in `index.html`. No build step, no backend, no npm/pip.

## Running
```
docker compose -f docker-compose.base44.yml up -d --build
```
Serves `index.html` via nginx on host port 3000. The repo is bind-mounted read-only,
so edits to `index.html` appear on browser refresh (no rebuild needed).

## Data
All user data lives in browser `localStorage` (key `workm-planner-v2`). No database.

## Secrets
None required. No external service integrations.

## Verifying it works
- `curl -s http://localhost:3000/ | grep WORKM` should return the page title.
- The preview should show the neon planner with a welcome modal on first load.
