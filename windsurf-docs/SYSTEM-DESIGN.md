# System Design

![Architecture Diagram](./_assets/high-level-arch.png) <!-- optional placeholder -->

## 1. Front-end (SPA)

| Layer            | Tech            | Purpose |
| ---------------- | --------------- | ------- |
| UI Components    | React + Tailwind CSS | Render interactive challenges, admin dashboards, widget iframe |
| State Management | Zustand         | Lightweight global stores (auth, settings, game state) |
| Routing          | React Router v6 | Nested routes & code-splitting |
| Data-Fetching    | `@supabase/supabase-js` & `react-query` | Real-time snapshots + RPC |

All requests flow through a typed **Supabase client** defined in `src/lib/supabase.ts`, which exposes `auth`, `from`, and `rpc` helpers.

## 2. Authentication Flow

1. **User Sign-in/Sign-up** screens (`/pages/auth/*`).
2. Supabase **email+password** or **OAuth** (future) handled via `supabase.auth`.
3. On success, a **JWT access token** is stored in `localStorage` (managed by Supabase).
4. Protected React routes use `useAuth` hook to gate access and redirect unauthenticated users.
5. RBAC is enforced server-side via Supabase **Row Level Security** policies; client additionally checks `session.user.role` for admin-only screens.

## 3. Database Schema (PostgreSQL / Supabase)

| Table              | Purpose |
| ------------------ | ------- |
| `admin_users`      | Admin accounts & preferences |
| `challenges`       | Challenge metadata and content JSON |
| `user_responses`   | Normalised responses linked to challenges |
| `api_keys`         | Client API credentials & usage stats |

Views:
* `challenge_performance_view`
* `daily_metrics_view`

All types are declared in `supabase.ts` ensuring compile-time safety.

## 4. APIs & Core Logic

| Endpoint (via Supabase REST / RPC) | Description |
| ---------------------------------- | ----------- |
| `GET /rest/v1/challenges?type=`     | Fetch active challenges filtered by type & difficulty |
| `POST /rest/v1/user_responses`      | Record widget attempt, including behavioural signals |
| `RPC verify_answer()`               | Server-side validation & ML scoring |
| `RPC generate_challenge()`          | (Admin) Invoke Gemini API to create new tasks |

On the **widget** side the flow is:

1. Host page loads `<script src="https://yuno-cdn/widget.js"></script>` (future CDN).
2. Script embeds an **iframe** served from the same Vite app with `#widget` route.
3. Widget fetches a challenge, draws UI, times response & pointer traces.
4. On submission, data is posted back – server returns `{ is_human: true/false }`.

## 5. External Integrations

| Service   | Reason |
| --------- | ------ |
| **Supabase** | Managed Postgres, Auth, Storage, Edge Functions |
| **Google Gemini API** | AI content generation for new challenges |
| **FingerprintJS** | Device and browser fingerprint to augment signals |
| **Playwright + Axe** | Automated E2E & accessibility tests |

## 6. Deployment Pipeline

1. **CI (Bolt)** runs `npm run lint && npm run test` on PRs.
2. On `main` merge:
   * Build artefact via `vite build` → `/dist`.
   * Deploy to **Netlify** (TBD) or **Vercel**.
3. Preview URLs are generated for each PR.

---

> This design emphasises a **serverless, type-safe** stack with minimal operational burden and room for real-time features via Supabase channels.
