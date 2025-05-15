
# VibeTravels

> **AI-powered trip-planner that converts plain travel notes into personalised itineraries in minutes.**

![Version](https://img.shields.io/badge/version-0.0.1-blue)
![Node](https://img.shields.io/badge/node-22.14.0-brightgreen)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

## Table of Contents
1. [Project Description](#project-description)  
2. [Tech Stack](#tech-stack)  
3. [Getting Started Locally](#getting-started-locally)  
4. [Available Scripts](#available-scripts)  
5. [Project Scope](#project-scope)  
6. [Project Status](#project-status)  
7. [License](#license)  

---

## Project Description

VibeTravels is a minimal-viable product (MVP) that slashes the pain of itinerary planning.  
Feed the app a couple of bullet-point notes—destination, dates, group size—and the built-in AI (via Openrouter) returns a full, preference-aware travel plan: where to go, why it matters, and how it fits your style. The first release targets:

* Secure sign-up / login (Supabase Auth).  
* Travel-preference profile to shape recommendations.  
* Note management (create / read / update / delete).  
* AI itinerary generation with per-user query limits.  
* History of generated plans for easy recall.  

---

## Tech Stack

| Layer      | Technology                               | Why we picked it |
|------------|------------------------------------------|------------------|
| Frontend   | **Astro 5** • **React 19** • **TypeScript 5** | Static-first speed (Astro) and interactive islands (React) with strong typing. |
| Styling    | **Tailwind CSS 4**, **shadcn/ui**, **lucide-react** | Rapid, consistent, accessible UI components and icons. |
| Backend    | **Supabase** (PostgreSQL + BaaS + Auth) | Open-source, self-host-able, zero-boilerplate backend. |
| AI layer   | **Openrouter.ai**                        | Access to multiple LLMs, cost caps per API key. |
| DevOps     | **GitHub Actions** • Docker • **DigitalOcean** | Straight-through CI/CD to container hosting. |

---

## Getting Started Locally

### Prerequisites
* **Git**  
* **Node 22.14.0** (see `.nvmrc`)  
* **npm ≥ 10** or pnpm/yarn  
* A Supabase project (URL & anon key).  
* An Openrouter API key with spending limit.

### 1. Clone the repo
```bash
git clone https://github.com/your-org/vibe-travels.git
cd vibe-travels
```

### 2. Install dependencies
```bash
npm install    # or pnpm install
```

### 3. Configure environment variables
Create a `.env` file (or `.env.local`) with at least:
```dotenv
SUPABASE_URL=...
SUPABASE_ANON_KEY=...
OPENROUTER_API_KEY=...
# Optional per-user AI query cap
AI_REQUEST_LIMIT=10
AI_REQUEST_WINDOW_HOURS=24
```

### 4. Run the dev server
```bash
npm run dev
```
The site will be available at **http://localhost:4321** by default.

### 5. Build for production
```bash
npm run build
npm run preview   # quick sanity check
```

### 6. Deploy
The project ships a `Dockerfile`. Push the image to your registry of choice and run on DigitalOcean, Fly.io, or any container host.  
CI pipelines are defined in `.github/workflows/`.

---

## Available Scripts

| Script            | Command                 | Purpose                           |
|-------------------|-------------------------|-----------------------------------|
| **dev**           | `astro dev`            | Start local dev server with HMR.  |
| **build**         | `astro build`          | Generate production build.        |
| **preview**       | `astro preview`        | Serve the built site locally.     |
| **astro**         | `astro`                | Run arbitrary Astro CLI tasks.    |
| **lint**          | `eslint .`             | Static code analysis.             |
| **lint:fix**      | `eslint . --fix`       | Auto-fix lint issues.             |
| **format**        | `prettier --write .`   | Consistent code formatting.       |

---

## Project Scope

### Included in the MVP
- **Auth**: email sign-up, email verification, secure login.  
- **Profile**: travel-preference capture & real-time edits.  
- **Notes CRUD**: destination, trip length, head-count, ages, optional dates.  
- **AI itineraries**: personalised plans, generated fast (< 30 min end-to-end).  
- **Usage limits**: time-window or budget caps per user.  
- **History**: list, re-download, or delete generated plans.

### Out of Scope (for now)
- Sharing itineraries between accounts.  
- Multimedia analysis (photos, videos).  
- Full logistics & booking engines.

---

## Project Status

| Item                   | State |
|------------------------|-------|
| **Stage**              | MVP, active development |
| **Timeline**           | 4-week sprint (single TS dev) |
| **Current version**    | 0.0.1 |
| **Roadmap / issues**   | See the [GitHub Projects](../../projects) board |
| **Goal for shipping**  | Functional, tested prototype ready for early adopters |

---

## License

This project is licensed under the **MIT License** – see the [`LICENSE`](LICENSE) file for details.  