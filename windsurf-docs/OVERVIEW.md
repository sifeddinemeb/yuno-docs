# Yuno – Human-First Bot Detection

**Yuno** is a modern CAPTCHA alternative that verifies humans through short, engaging challenges instead of distorted text or image grids. It combines UX-friendly micro-games with behavioural signals and machine-learning heuristics to stop bots while staying delightful for real users.

**Who is it for?** Any product team that cares about sign-up fraud, spam, or abuse but refuses to sacrifice user experience.

**Core Features**

1. **Adaptive Challenge Library** – 6 game-like tasks (drag-to-fit, odd-one-out, etc.) with difficulty escalation.
2. **Behavioural Analytics** – Response time, pointer trajectory, and device fingerprinting.
3. **ML Scoring Engine** – K-means clustering & rules to classify attempts as human vs bot.
4. **Supabase Backend** – Stores challenges, responses, API keys, and analytics views.
5. **Admin Dashboard** – Real-time metrics, content management, and challenge authoring.
6. **Embeddable Widget** – Drop-in `<script>` for client sites → communicates via REST.
7. **AI Challenge Generation (Gemini)** – Auto-generate fresh content to combat memorisation.

Yuno strives for **99%+ pass-rate for humans** while blocking automated traffic with **<0.3% false positives**.
