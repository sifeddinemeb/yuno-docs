## 🧾 The 10 Commandments

### 1. **Clarity Beats Cleverness**

Build for the next developer (even if that’s you in 6 months). Clear, readable, and boring is better than brilliant and broken.

---

### 2. **Everything Must Be Modular**

No hardcoding. No tangled logic. Break things into reusable, replaceable pieces — functions, modules, components, or services.

---

### 3. **Use Types and Docs Religiously**

Every function and class must have type hints and a docstring. If someone can’t understand it in 10 seconds, it’s not ready.

---

### 4. **Make Errors Helpful**

Handle every failure like it’s a user-facing experience. Throw custom exceptions, log context, and guide the developer or user to a fix.

---

### 5. **Never Mix Concerns**

UI ≠ logic ≠ storage ≠ services. Keep layers separate and interfaces clean. No business logic in the UI. No DB calls in utils.

---

### 6. **No Feature Without a Use Case**

Don’t build “just in case.” If it’s not needed now (or in the current sprint), it’s scope creep. Stick to what matters.

---

### 7. **Everything is Replaceable**

Code should be disposable. Use patterns that make it easy to swap in a new model, UI, or backend with minimal rewiring.

---

### 8. **One Source of Truth**

Whether it’s config, environment, state, or business rules — it should live in **one place only**. Avoid duplication at all costs.

---

### 9. **Docs are Part of the Product**

Every system, feature, or endpoint must have **markdown-level documentation**. Good docs aren’t extra — they’re deliverables.

---

### 10. **Done Means It Works Without You**

A feature is only “done” when it can be used, debugged, and extended **without the author’s help**. That’s real freedom.
