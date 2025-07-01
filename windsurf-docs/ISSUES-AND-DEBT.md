# Issues & Technical Debt

> Source: automated scan + manual inspection (2025-06-26)

## 🐞 Confirmed Bugs

| ID | Area | Description | Repro Steps |
|----|------|-------------|-------------|
| B-001 | Admin Auth | Login triggers auth loop causing blank screen freeze | Login as admin and observe blank dashboard for several seconds |
| B-002 | Admin Dashboard | Challenge list pagination not implemented | Visit `/admin/challenges` with >25 records |
| B-003 | Widget Performance | Animation jank & high CPU on Safari | Load widget on Safari 15, observe 60→30 FPS drop |
| B-004 | Bundle Size | JS bundle >200 KB, fails mobile perf budget | Run `npm run build` and inspect `/dist` |

## ⚠️ UX Gaps

1. **Admin Layout Scroll:** Extra empty space below content → unwanted vertical scroll.
2. **Mobile → Widget:** Some challenge components overflow <375px width.
2. **Dark/Light Switch:** Toggling themes during an active challenge resets timer.
3. **Accessibility:** Keyboard focus not trapped inside modal in older Safari.

## ✨ Resolved Since Legacy Docs
- 30+ critical bugs from Sprints 1-8 (see `older-docs/bugs-and-issues.md`) have been fixed: authentication flow, widget integration, challenge types, AI content, etc.

## 🏚️ Technical Debt

| Area | Debt | Impact |
|------|------|--------|
| State Management | Multiple stores reading from `localStorage` directly – should be abstracted behind a single persistence layer | Medium |
| Supabase Types | Types are duplicated in both `.sql` comments and `supabase.ts` – risk of drift | High |
| CSS | Some ad-hoc classes in `index.css` bypass Tailwind – inconsistent theming | Low |
| Performance | Excessive runtime re-renders in `YunoWidget` – requires memoization & code-splitting | High |

---

_Priority for hackathon: performance/B-003, pagination B-002, then type duplication cleanup._
