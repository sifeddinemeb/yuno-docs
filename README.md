# 🧠 The Workflow: AI-Driven Project Orchestration

This `master-prompts/` folder contains the core "master prompts" that orchestrated the entire development of the Yuno project, from initial concept to a polished, full-stack application, **without me writing a single line of code**. This workflow is designed to empower any product thinker or solo developer to build complex projects by leveraging AI coding assistants like Bolt.new and Windsurf.

It's a structured, human-in-the-loop approach that turns high-level vision into actionable, AI-executable steps, adaptable to **any type of project or tech stack**.

## 🚀 The 5 Master Prompts (My AI Orchestration Playbook)

This workflow consists of a sequence of 5 strategic prompts, each serving a distinct purpose in the development lifecycle. Crucially, "The Ten Commandments" (a separate document outlining strict guidelines for documentation, code quality, and functional preservation) were **always pasted alongside prompts 4 and 5** during sprint execution. This ensured the AI consistently updated project documentation, serving as its continuous memory and translating the complex `/src` codebase into a human-readable, non-technical overview for me.

1.  ### `1-UNIVERSAL CODEBASE DOCUMENTATION PROMPT.md`
    * **Purpose:** This is the foundational prompt. It instructs the AI to perform a deep scan of an *existing* (or newly scaffolded) codebase, reverse-engineer its structure and logic, and then generate a comprehensive `/project-docs/` folder. This folder becomes the "single source of truth," containing detailed `overview.md`, `bugs-and-issues.md`, `incomplete-features.md`, `system-design.md`, and more.
    * **Why it's crucial:** It establishes a shared, structured understanding of the project between you and the AI, eliminating implicit knowledge and preparing for systematic development. It's like giving your AI assistant its own internal knowledge base.
    * **Applicability:** Use this at the very beginning of any project, or when onboarding onto an existing codebase.

2.  ### `2-STRATEGIC EXECUTION PHASE.md`
    * **Purpose:** This prompt guides the AI to analyze the newly generated `/project-docs/` (from Prompt 1) and distill all findings into a single, tactical `plan.md`. This `plan.md` acts as a "launch war map," prioritizing critical fixes, incomplete features, UX gaps, backend issues, and refactor opportunities. Findings are grouped by functional themes (e.g., `#auth`, `#ui`, `#data`).
    * **Why it's crucial:** It transforms raw documentation into an actionable engineering plan, ensuring focus on what truly matters for MVP delivery. It helps you identify the fastest path to a shippable product.
    * **Applicability:** Run this after your initial documentation phase to create a prioritized action plan for your project.

3.  ### `3-BUILD EXECUTION PROMPT.md`
    * **Purpose:** This prompt takes the strategic `plan.md` (from Prompt 2) and translates it into a full roadmap of incremental, test-driven sprints, generating a `sprints.md` file. Each sprint is defined with clear goals, tasks (broken down by scope like `#api`, `#ui`), testing/validation steps, and identified risks.
    * **Why it's crucial:** It breaks down the large project into manageable, executable chunks, setting the stage for iterative development. It creates a day-to-day playbook for the AI to follow.
    * **Applicability:** Use this once your `plan.md` is finalized to structure your entire development timeline into sprints.

4.  ### `4-SPRINT INITIATION PROTOCOL.md`
    * **Purpose:** This prompt initiates the execution of a *single* sprint from the `sprints.md` roadmap. It guides the AI through a "Pre-Sprint Review" (re-reading relevant docs), "Implementation" of tasks, "Documentation Updates" (marking sprint complete, logging bugs/fixes), and a structured "Report Back" to you. It also outlines "The Ten Commandments of Sprint Execution" for the AI.
    * **Why it's crucial:** It formalizes the sprint execution process, ensuring discipline, comprehensive documentation updates, and clear communication after each development cycle. This prompt, along with Prompt 5, was always accompanied by "The Ten Commandments" to reinforce continuous documentation and context.
    * **Applicability:** Use this to begin each new sprint in your project.

5.  ### `5-NEXT SPRINT — STANDARD EXECUTION PROMPT.md`
    * **Purpose:** This is the "loop" prompt. After a sprint is completed and reported (via Prompt 4), you simply provide this prompt to the AI. It instructs the AI to select the *next* sprint from `sprints.md`, review context, implement tasks, update documentation, and submit a new sprint report, then *wait for your explicit "next"* command.
    * **Why it's crucial:** This prompt enables the continuous, iterative development cycle. It keeps the AI in sync with your strategic oversight, allowing you to test and validate each sprint's output before proceeding. Like Prompt 4, this was always accompanied by "The Ten Commandments" for consistent AI behavior and documentation.
    * **Applicability:** Use this repeatedly after each successful sprint completion to move to the next one, until your MVP is done.

## 💡 Why This Workflow Works (Benefits for Any Project)

* **Zero Code Written by Human:** This workflow demonstrates how to build complex applications entirely through strategic prompting, empowering product thinkers without traditional coding backgrounds.
* **Structured & Iterative Development:** It imposes a disciplined sprint methodology, breaking down large projects into manageable, testable units.
* **Comprehensive, AI-Maintained Documentation:** The AI actively generates and updates project documentation, ensuring a single source of truth that evolves with the codebase. **This documentation serves as the AI's continuous memory and context, effectively translating the complex `/src` codebase into a human-readable, non-technical overview for the non-programmer.**
* **Adaptability & Reusability:** The prompts are generic enough to be applied to any tech stack (React, Python, etc.) and any project type (web app, game, API, etc.).
* **Mitigation of AI Tool Limitations:** By structuring the process, you can adapt to AI tool limitations (like token limits or performance bottlenecks) by strategically transitioning between tools (as I did from Bolt.new to Windsurf).
* **Clear Oversight:** You, the human, remain in the "captain's chair" as the strategist and tester, guiding the AI through each phase.

## 🛠️ How to Use This Workflow for Your Project

1.  **Start with Prompt 1:** Feed your initial project idea or existing codebase to your AI coding assistant using the `1-UNIVERSAL CODEBASE DOCUMENTATION PROMPT.md`.
2.  **Generate Your Plan:** Once the documentation is ready, use `2-STRATEGIC EXECUTION PHASE.md` to create your `plan.md`.
3.  **Build Your Sprints:** Use `3-BUILD EXECUTION PROMPT.md` to break your `plan.md` into `sprints.md`.
4.  **Execute Sprints Iteratively:** Begin your first sprint with `4-SPRINT INITIATION PROTOCOL.md`. For all subsequent sprints, simply use `5-NEXT SPRINT — STANDARD EXECUTION PROMPT.md` repeatedly, *always pasting "The Ten Commandments" along with it*, testing and confirming after each one, until your project is complete.

This workflow provides a robust framework for efficient, AI-powered software development.
