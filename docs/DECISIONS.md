# Architecture Decision Log

This file records decisions that should not be changed silently.

## ADR-001 — Use Vanilla JavaScript

**Status:** Partially superseded by ADR-006 and ADR-007

**Decision:** The MVP uses Vanilla JavaScript for game logic. Styling uses Tailwind CSS (see ADR-007). Build tooling uses Vite (see ADR-006).

**Reason:** The project is a learning exercise for students currently studying JavaScript fundamentals. A framework would hide or replace some of the DOM and JavaScript work they need to practice.

**Consequences:**
- No React or other UI framework.
- DOM updates are written explicitly.
- Code should remain simple and readable.

## ADR-002 — No backend for MVP

**Status:** Accepted

**Decision:** The game runs entirely in the browser.

**Reason:** The game does not currently need accounts, multiplayer, shared data or server-side validation.

**Consequences:**
- Game data is local JavaScript data.
- Puzzle answers are inspectable and are not secure secrets.
- Progress resets when the page is reloaded unless a later extension adds local storage.

## ADR-003 — Start with one JavaScript file

**Status:** Accepted

**Decision:** Start with `script.js`; split into ES modules only when students are ready.

**Reason:** The current curriculum includes functions, objects, arrays and DOM, but the project should not front-load module architecture.

**Consequences:**
- Keep clear sections in `script.js`.
- Avoid giant functions.
- Refactor only after the MVP behavior works and students understand the code.

## ADR-004 — Game state is the source of truth

**Status:** Accepted

**Decision:** Store player progress in one JavaScript state object. Render the DOM from that state.

**Reason:** This avoids inconsistent UI and makes state changes easier to debug.

**Consequences:**
- Event handlers call game logic functions.
- Rendering functions read state.
- DOM text is not used to determine whether an item was collected or a puzzle was solved.

## ADR-005 — Shared agent instructions

**Status:** Accepted

**Decision:** Use root `AGENTS.md` as the shared project instruction file for Codex and Antigravity.

**Reason:** Both tools recognize `AGENTS.md` as a workspace instruction file according to their current documentation.

**References:**
- Codex guidance: https://learn.chatgpt.com/docs/agent-configuration/agents-md
- Antigravity rules: https://antigravity.google/docs/rules/

**Consequence:** Keep `AGENTS.md` concise, stable and focused on project-wide constraints. Put detailed product and architecture information in `docs/`.

## ADR-006 — Use Vite as development server and build tool

**Status:** Accepted

**Decision:** Use Vite for the development server (HMR) and production builds.

**Reason:** Vite provides fast hot module replacement, native ES module support, and seamless integration with Tailwind CSS v4. Students learn modern development workflows including `npm install`, `npm run dev` and `package.json`.

**Consequences:**
- `npm` and `package.json` are part of the project from Stage 0.
- The game runs via `npm run dev`, not by opening `index.html` directly.
- ES modules (`type="module"`) are used natively by Vite.
- A `vite.config.js` file is required in the project root.

## ADR-007 — Use Tailwind CSS v4 for styling

**Status:** Accepted

**Decision:** Use Tailwind CSS v4 with the `@tailwindcss/vite` plugin as the primary styling tool.

**Reason:** Tailwind's utility-first approach accelerates UI development and teaches students a widely used CSS framework. Version 4 simplifies configuration with CSS-based setup (`@import "tailwindcss"`) and requires no separate config files.

**Consequences:**
- Styling is done primarily with Tailwind utility classes in HTML.
- Custom CSS is written in `src/style.css` only when Tailwind utilities are insufficient.
- No separate `tailwind.config.js` or `postcss.config.js` needed (Tailwind v4 uses CSS-based config and the Vite plugin).
- `tailwindcss` and `@tailwindcss/vite` are dev dependencies.

## ADR-008 — Allow additional libraries when needed

**Status:** Accepted

**Decision:** Additional npm libraries may be introduced at later roadmap stages when they serve a clear purpose.

**Reason:** Restricting all dependencies limits learning opportunities. Students should learn to evaluate, install and use libraries as part of modern JavaScript development.

**Consequences:**
- Each new library must be recorded as a decision in this file.
- Libraries must not replace JavaScript fundamentals the student needs to practice.
- Prefer lightweight, well-documented libraries.
