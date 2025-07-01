# Sprint Roadmap – Path to MVP

The team has already completed **8 foundational sprints** (documented in the legacy `older-docs/` folder) covering backend setup, full admin CRUD, widget integration, advanced bot-detection, UX optimisation, and AI-assisted content generation. This file now focuses on the **final polishing phase** to get Yuno hackathon-ready. Remaining work is organised into the current 4-sprint cadence (2 weeks each) that builds upon the achievements of the earlier sprints.

---

## 🛠️ Sprint 1: "Critical Polish & Bug Smash"

**Goals:**
- Eliminate admin authentication freeze (auth loop) → instant dashboard load.
- Remove extra blank scroll region on admin pages.
- Introduce server-side pagination on Challenges table.
- Maintain 100% green CI.

**Tasks:**
- 🔴 Diagnose auth loop via `useAuth` + `supabase.auth.onAuthStateChange` listener; add early-exit guard `#auth`
- 🔴 Throttle session refresh polling to 60 min (was 2 sec) `#auth #perf`
- 🔴 Ensure `React.Suspense` fallback for dashboard routes to prevent blank screen `#ui`
- 🔴 Fix CSS layout causing extra scroll: restrict wrapper min-height and remove stray `mt-*` margin `#ui`
- 🔴 Implement pagination params (`limit`, `offset`) in Supabase `from('challenges')` query; update `ChallengesTable` component with pagination controls `#ui #data`
- ✅ Keep CI pipeline green `#infra`

**Testing & Validation:**
- Login → dashboard should render <1 s with no blank stage (Playwright test).
- Scroll admin page: should end at content bottom (Jest + jsdom check on height).
- Challenges page: requesting 200 challenges returns pagination (10/page) and accurate page count.
- CI green on every PR.

**Risk Factors:**
- Session polling change may affect token refresh – monitor error logs.
- CSS change may introduce layout regressions on small screens.

---

## 🧩 Sprint 2: "Core Verification Loop"

**Goals:**
- Complete challenge verification pipeline end-to-end.
- Supabase `verify_answer()` RPC finalised and called by widget.
- Store user responses + update analytics views.

**Tasks:**
- ✅ Implement RPC & ML scoring logic `#api #ml`
- ✅ Wire widget submit → `verify_answer()` `#widget #api`
- ✅ Update `user_responses` insert typings `#db`
- ✅ Basic admin metrics chart (success rate) `#ui #admin`

**Testing & Validation:**
- Playwright script solves a challenge → expect `is_human=true`.
- DB reflects new row in `user_responses`.

**Risk Factors:**
- ML model thresholds – flag for tuning, wrap in feature flag.

---

## 🎨 Sprint 3: "Delight & Dashboard"

**Goals:**
- Polish widget UI/UX (mobile, a11y, dark mode flicker).
- Admin dashboard gets filters & pagination.
- Theme API exposed to host sites.

**Tasks:**
- ✅ Fix width overflow on <375px `#ui`
- ✅ Implement Tailwind dark-mode transitions `#ui`
- ✅ Add date/type filters to analytics page `#ui #admin`
- ✅ Accept `theme` param in widget `<script>` `#widget #api`

**Testing & Validation:**
- Axe accessibility scan passes with zero critical issues.
- Widget renders correctly on iPhone SE viewport.

**Risk Factors:**
- Styling changes may cascade; snapshot test key components.

---

## 🤖 Sprint 4: "AI & Launch Prep"

**Goals:**
- Ship Gemini-powered content generation with human review queue.
- OAuth (Google) auth option.
- Production deploy pipeline (Netlify) + preview URLs.

**Tasks:**
- ✅ Finish `generate_challenge()` edge function `#api #ai`
- ✅ Build review queue UI in admin `#ui #admin`
- ✅ Add Google OAuth in Supabase & front-end `#auth`
- ✅ Create Netlify workflow, deploy preview, backup script `#infra`

**Testing & Validation:**
- E2E: admin generates 3 challenges → approves → they appear in widget.
- OAuth sign-in returns valid session & role.
- Successful deploy & smoke test on Netlify preview.

**Risk Factors:**
- AI quota or latency; implement exponential-backoff retry.

---

> After Sprint 4 the refreshed roadmap delivers a production-quality MVP with CI/CD, AI content, and OAuth.
>
> **Next up → Sprint 5: Hackathon Polish**

---

## 🏆 Sprint 5: "Hackathon Polish & Performance"

**Goals:**
- Optimise bundle size (<140 KB gzipped) and first paint (<1 s on 4G).
- Resolve remaining performance / animation jank items from legacy issue #20.
- Accessibility: achieve WCAG AA audit score ≥ 95.
- Harden error boundaries and logging for live demo stability.

**Tasks:**
- ✅ Tree-shake Lucide icons & framer-motion `#perf #ui`
- ✅ Code-split widget and admin routes via React.lazy `#perf`
- ✅ Replace inline SVGs with `<Icon />` component wrapper `#ui`
- ✅ Add React Profiler metrics to CI budget check `#perf #infra`
- ✅ Run Axe & Lighthouse, fix critical violations `#a11y`
- ✅ Add Sentry for runtime error tracking (prod only) `#infra`

**Testing & Validation:**
- Lighthouse mobile performance ≥ 90.
- Axe CLI passes with zero critical issues.
- Widget loads on simulated 4G in <1 s (Chrome DevTools).

**Risk Factors:**
- Aggressive code-splitting could break dynamic imports; test thoroughly.

---

> Post-hackathon, further sprints can tackle enterprise features, monetisation, and deep ML enhancements.
