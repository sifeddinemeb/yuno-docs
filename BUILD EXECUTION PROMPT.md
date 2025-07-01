**3-BUILD EXECUTION PROMPT**
You’ve completed the strategic `plan.md`.

Now it’s time to **translate it into action**: a full roadmap of **incremental sprints** to ship a polished, working application — fast, clean, and tested.

---

### 📁 INPUT

Scan **all files inside `/project-docs/`**, including:

- `overview.md`
    
- `incomplete-features.md`
    
- `bugs-and-issues.md`
    
- `ui-ux-gaps.md`
    
- `dev-roadmap.md`
    
- `plan.md`
    
- `database-setup.md` or `data-integrations.md`
    
- Any other related technical docs
    

---

### 🎯 OUTPUT

Generate a new file:

```
/project-docs/sprints.md
```

This file is a **step-by-step execution plan** divided into smart, test-driven **sprints**, each with:

- 🎯 **Sprint Name**
    
- 🧩 **Goals**: Clear outcomes or what "done" looks like
    
- 📋 **Tasks**: Broken down by scope (`#api`, `#ui`, `#data`, etc.)
    
- 🧪 **Testing/Validation Needed**
    
- ⚠️ **Risk of breaking existing features?**
    
- ✅ **Linting/console errors to clean up** in this scope
    

---

### 🔁 GUIDELINES

- **No unnecessary complexity.** Only what’s needed to ship cleanly.
    
- Prioritize **MVP-critical** features first.
    
- Group tasks in logical order (e.g. schema before logic, logic before UI).
    
- Include **testing tasks** when functionality or logic needs to be verified before continuing.
    
- Always check and fix **linter errors** and visible **console warnings** during each sprint.
    
- Don’t break existing functionality — if something might, **note it + add a test**.
    
- Add `[🧪 TEST]` tags for anything needing manual or automated testing.
    

---

### 🔨 SPRINT STRUCTURE EXAMPLE

```markdown
### 🚀 Sprint 1: Core Auth + User Onboarding

**Goals:**
- Complete full working auth flow with login, register, logout
- Basic onboarding state flow (new user → app ready)

**Tasks:**
- [ ] Connect login/signup UI to working Supabase auth (#auth)
- [ ] Handle auth errors (wrong creds, weak pass) (#ui)
- [ ] Setup onboarding logic and DB flag for `first_time_user` (#data, #logic)
- [ ] Add fallback loading state + redirection (#ui)

**Testing/Validation:**
- [🧪 TEST] Signup → login → logout flow
- [🧪 TEST] First-time user triggers onboarding
- ✅ Check and fix any auth-related console errors

**Risks:**
- Might affect routing guards
- Be careful not to break session persistence logic
```

---

### ✅ FINAL GOAL

Produce a sequence of **focused, doable sprints** — from critical fixes to MVP polish — with enough clarity that any engineer can just **start from Sprint 1 and build forward without confusion or regressions.**

This `sprints.md` becomes your **day-to-day playbook** until launch.