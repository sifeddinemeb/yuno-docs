**The 10 Commandments for YOU**

*Remember to always adhere to these principles in addition to the specific task in the prompt. Your primary directive is to assist in building a functional and maintainable Image Processor MVP, following the user's iterative workflow.*

1.  **Master the Blueprint (`refactor.md`):** Before *any* code modification, internalize the project structure and principles defined in `refactor.md`. All new code and refactoring *must* align with this blueprint. If a task seems to conflict, seek clarification.
2.  **Re-Affirm the Current Task Context:** At the beginning of processing any new prompt, briefly state your understanding of the immediate goal *and* how it fits into the broader picture outlined in `plan.md`.
3.  **Document Diligently & Immediately:** *After successfully completing any code changes that are confirmed to be kept*, you *must* update all relevant documentation files (`plan.md` checklists, `bugs-and-issues.md` status, `dev-roadmap.md` progress, `refactor.md` if its plan is being executed/modified, etc.). **All documentation updates must include a UTC timestamp.** This is non-negotiable.
4.  **Stay Focused, Work Incrementally:** Execute only the specific tasks requested in the prompt. Do not modify unrelated files or implement features not explicitly asked for. If a task is large, propose to break it down into smaller, verifiable steps.
5.  **Preserve Functionality Above All:** Unless the task is a specific, intentional breaking change (like the initial refactor), ensure the application remains functional after your modifications. Prioritize keeping the MVP in a testable state.
6.  **Explain Your Work Clearly:** After completing the task, provide a concise summary of:
    *   What files you changed.
    *   A brief overview of the changes made in each file.
    *   Confirmation that documentation has been updated (or specify which docs if not all were relevant).
7.  **Adhere to Code Quality & Conventions:** Follow the coding style, naming conventions, and architectural patterns established in `refactor.md` and existing well-structured code. Write clean, readable, and maintainable Python code.
8.  **Anticipate the Feedback Loop:** Understand that your output will be tested by the user. Structure your changes and explanations in a way that facilitates easy review and testing. If you foresee potential issues or edge cases related to your changes, mention them.
9.  **Implement Robust Error Handling (Proactively):** For any new logic involving data operations, user input, or potential external interactions (even mocked ones for now), implement appropriate error handling (e.g., try-catch blocks, clear user feedback for UI errors).
10. **Verify File Paths & Imports:** Double-check all file paths and import statements, especially after refactoring or moving files, to ensure they align with the `refactor.md` structure and that the application can compile and run.