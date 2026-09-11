# Film Making — Production Workflow Dashboard

Film Making is a Next.js front end for sending screenplay text through an external production-analysis API and reviewing the resulting schedule, budget, characters, one-liners, and system logs.

## Core features

- Plain-text screenplay upload and in-browser text loading.
- Script-analysis views for scenes, metadata, locations, and characters.
- API-driven shooting schedule and resource-allocation workflow.
- API-driven budget, scene one-liner, character, and system-sync views.
- API statistics and request-log display with log clearing.
- Responsive Material UI dashboard with sidebar navigation and light/dark themes.

## Technology stack

- Next.js 15, React 19, and TypeScript
- Material UI 7 with Emotion styling
- Tailwind CSS 4 build tooling
- Browser Fetch API for backend requests

## Prerequisites

- Node.js and npm
- A separate compatible HTTP API available at `http://localhost:8000/api`

## Local setup

```bash
git clone https://github.com/varunisrani/film_making1.git
cd film_making1
npm ci
npm run dev
```

The front end uses `http://localhost:3000` by default. Start the separate backend on port 8000 before using analysis features.

Production commands:

```bash
npm run build
npm run start
```

The repository also defines `npm run lint`.

## Configuration

No environment variables are referenced. The backend base URL is hard-coded as `http://localhost:8000/api` in `app/page.tsx`.

## Project structure

- `app/page.tsx` — dashboard UI, workflow state, and all backend requests.
- `app/layout.tsx` — root layout and metadata.
- `app/globals.css` — global styling.
- `public/` — default static assets.
- `next.config.ts`, `tsconfig.json`, and `eslint.config.mjs` — framework and tooling configuration.

## Status and limitations

This repository contains only the front end; it cannot perform analysis without a separately supplied API implementing `/script`, `/schedule`, `/budget`, `/one-liners`, `/characters`, `/system-sync`, and `/logs` endpoints. The backend URL is not configurable without changing source. Uploaded files are read as text, and no automated test script is defined. The lint script uses `next lint`, which may not work with this Next.js version.