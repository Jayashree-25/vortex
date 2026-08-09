# Vortex

Full-stack hackathon management platform for "Tech Xpress | SOA University Railways Division". A React + Vite frontend paired with an Express + Prisma (SQLite) API that handles participant registration, team formation, evaluations, and live leaderboards, styled with a high-tech "Vande Bharat" railway aesthetic.

## Features

- Individual participant registration with domain/theme selection
- Shortlist status tracking and crew dashboard
- Team creation/joining with domain matching and diversity (at least one woman per team) rules
- Problem statement submission tied to a team's selected domain
- Jury evaluations per round with scores and feedback
- Live leaderboard with round-based scoring and rank positions
- Domains, awards, and team management APIs
- Machined, rail-inspired UI (track dividers, nose-cone accents, sharp geometry)

## Tech Stack

- Frontend: React 19, Vite, React Router, Tailwind CSS, lucide-react
- Backend: Node.js, Express, Prisma, better-sqlite3, zod, jsonwebtoken, helmet
- Package manager: pnpm

## Getting Started

### Backend

```bash
cd backend
pnpm install
cp .env.example .env     # set DATABASE_URL, JWT secrets, PORT (default 3001)
pnpm db:push             # create the SQLite schema
pnpm db:seed             # optional: seed sample data
pnpm dev                 # start API with hot reload
```

The API exposes routes under `/api`: `domains`, `awards`, `students`, and `teams`, plus a `/api/health` check.

### Frontend

```bash
cd frontend
pnpm install
pnpm dev                 # Vite dev server (default http://localhost:5173)
```

## Project Structure

```
backend/
  src/
    index.js             Express app entry point
    routes/              API route definitions
    controllers/         Request handlers
    middleware/          Validation
    config/              Env and DB setup
  prisma/
    schema.prisma        Database schema
    seed.js              Sample data
frontend/
  src/
    pages/               Dashboard, Crew, Requests, Registration, Manifest, Leaderboard
    components/common/   TopAppBar, NavigationDrawer, Footer, MachinedCard, TrackDivider
```

## License

[GNU AGPL v3](LICENSE)
