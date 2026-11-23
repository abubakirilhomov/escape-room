# Architecture Decision Log

This file records decisions that should not be changed silently.

## ADR-001 — Use Vanilla JavaScript

**Status:** Accepted

**Decision:** The MVP uses HTML, CSS and Vanilla JavaScript.

**Reason:** The project is a learning exercise for students currently studying JavaScript fundamentals. A framework would hide or replace some of the DOM and JavaScript work they need to practice.

**Consequences:**
- No React or other UI framework.
- No build system required for the MVP.
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
