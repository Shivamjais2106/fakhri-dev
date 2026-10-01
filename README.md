# Fakhri Dev

Official website for **Fakhri Software Development** — built with Next.js (App Router), TypeScript, and MongoDB.

## Tech Stack

- **Framework:** Next.js (App Router, TypeScript)
- **Styling:** Tailwind CSS
- **Database:** MongoDB (via Mongoose)
- **Auth:** JWT (jose) + bcryptjs
- **Animations:** Framer Motion, GSAP
- **Containerization:** Docker

## Getting Started (Local Development)

### Prerequisites

- Node.js 20+
- npm
- MongoDB (local instance or a connection string, e.g. MongoDB Atlas)
- Docker Desktop (optional, only needed for container-based setup)

### 1. Clone the repository

```bash
git clone <repo-url>
cd fakhri-dev
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Copy the example env file and fill in your own values:

```bash
cp .env.example .env.local
```

Required variables:

```
MONGODB_URI=
NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

### 4. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Running with Docker

### Build and run (app only)

```bash
docker build -t fakhri-dev .
docker run -p 3000:3000 --env-file .env.local fakhri-dev
```

### Build and run (app + MongoDB together)

```bash
docker compose up --build
```

This starts both the Next.js app and a MongoDB container. The app will be available at [http://localhost:3000](http://localhost:3000).

To stop:

```bash
docker compose down
```

## Project Structure

```
fakhri-dev/
├── app/              # Next.js App Router pages and layouts
├── components/       # Reusable UI components
├── lib/              # Utilities, DB connection, server actions
├── public/           # Static assets (images, fonts, etc.)
├── styles/           # Global styles and CSS variables
├── Dockerfile
├── docker-compose.yml
└── next.config.ts
```

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Build the app for production |
| `npm run start` | Start the production server |
| `npm run lint` | Run ESLint |

## Deployment

This app can be deployed as a standalone Docker container on any server, or on platforms like Vercel for the Next.js app alone (with an external MongoDB instance).

## License

Private — Fakhri Software Development. All rights reserved.