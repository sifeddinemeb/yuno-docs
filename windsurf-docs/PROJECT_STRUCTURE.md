# Project Structure

```
/ (repo root)
├─ .bolt/                 # Remote preview & CI configuration
├─ .git/                  # Git history
├─ .gitignore             # VCS ignore rules
├─ index.html             # Vite single-page HTML shell
├─ package.json           # Dependency & script manifest
├─ package-lock.json      # npm lock-file (deterministic installs)
├─ vite.config.ts         # Vite bundler configuration
├─ tailwind.config.js     # Tailwind design-system configuration
├─ eslint.config.js       # ESLint shared rules
├─ tsconfig*.json         # TypeScript compiler configs
├─ jest.config.js         # Jest unit-test setup
├─ playwright.config.ts   # Playwright E2E test setup
├─ supabase/              # Database schema, SQL migrations & edge functions
│  └─ ... (sql, types, generated files)
├─ src/                   # Front-end source (React + Vite + TS)
│  ├─ App.tsx             # App root – routing & shell composition
│  ├─ main.tsx            # Vite entrypoint – ReactDOM hydration
│  ├─ index.css           # Tailwind base styles & custom layer utilities
│  ├─ components/         # Re-usable UI building blocks
│  │  ├─ ui/              # Atomic primitives (Button, Input, Modal…)
│  │  ├─ layout/          # Page-level layout wrappers (Header, Footer…)
│  │  ├─ widget/          # Public-facing Yuno verification widget
│  │  └─ admin/           # Admin-dashboard specific widgets
│  ├─ pages/              # Route-level screens (React Router v6)
│  │  ├─ auth/            # Sign-in / sign-up & password flows
│  │  ├─ admin/           # Admin area (analytics, content management)
│  │  ├─ Demo/            # Live challenge demo playground
│  │  └─ marketing pages  # Vision, Impact, etc.
│  ├─ lib/                # Client-side libraries & helpers
│  │  ├─ supabase.ts      # Supabase client & typed DB schema
│  │  ├─ gemini-api.ts    # Google Gemini wrapper for AI generation
│  │  └─ … utility files  # analytics, helpers, constants
│  ├─ hooks/              # Custom React hooks (useAuth, useStore…)
│  ├─ store/              # Zustand global state stores
│  ├─ data/               # Static seed data & fixtures
│  └─ types/              # Project-wide TypeScript interfaces & enums
└─ project-docs/          # 📚 Generated documentation (single source of truth)
```

> Each directory above is self-contained and follows a **feature-first** structure, promoting modularity and scalability.
