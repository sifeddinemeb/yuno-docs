# Developer Guide

Welcome to **Yuno**! This guide gets you from zero to a running dev environment in minutes.

---
## 🖥️ Prerequisites

1. **Node.js >= 18** (LTS recommended)
2. **npm** (ships with Node) or **pnpm / yarn** if you prefer – examples below use `npm`.
3. A modern browser (Chrome, Edge, Firefox) for local testing.

---
## ⚡ Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/your-org/yuno.git
cd yuno

# 2. Install dependencies
npm install

# 3. Configure environment
cp .env.example .env        # then fill in real keys

# 4. Launch the dev server
npm run dev                 # http://localhost:5173 (Vite default)
```

The dev server supports **HMR** (instant reload) and full **TypeScript** checking.

---
## ⛩️ Environment Variables

Create a `.env` at the project root. An example template is provided below:

```dotenv
# ───────────────────────────────────────────
# Supabase
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=

# Google Gemini AI (optional – used for challenge generation)
VITE_GEMINI_API_KEY=
```

> Note: The `VITE_` prefix makes variables available to the client at build-time (Vite requirement).

---
## 📜 NPM Scripts

| Script           | Purpose                                |
| ---------------- | -------------------------------------- |
| `npm run dev`    | Start Vite dev server with HMR         |
| `npm run build`  | Production build to `/dist`            |
| `npm run preview`| Preview the production build locally   |
| `npm run lint`   | ESLint code quality checks             |
| `npm run test`   | Jest unit tests                        |
| `npm run test:e2e` | Playwright end-to-end test suite     |

---
## 🏗️ Project Conventions

1. **Feature-first folders** inside `src/` keep related components, hooks, and tests together.
2. **TypeScript** is strict – leverage types to prevent bugs.
3. **Tailwind CSS** is the default styling layer; avoid ad-hoc inline styles.
4. Prefer **Zustand** for global state over React context.
5. Keep **supabase** queries in `/lib` or dedicated data services to avoid scattering SQL.

Happy hacking! ✨
