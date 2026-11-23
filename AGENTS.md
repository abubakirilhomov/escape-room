# Project Instructions — Escape Room

## 1. Project mission

Build a small educational browser game named **Escape Room: Secret Laboratory**. The project teaches beginner JavaScript through a playable game.

Before making changes, read:
- `README.md`
- `docs/PRODUCT_SPEC.md`
- `docs/GAME_DESIGN.md`
- `docs/ARCHITECTURE.md`
- `docs/DATA_MODEL.md`
- `docs/ROADMAP.md`

Read other documents when the task touches their area.

## 2. Fixed technology constraints

- Use only HTML5, CSS3 and Vanilla JavaScript.
- Use ES modules (`type="module"`) only when the roadmap reaches the modularization stage. Until then, keep the beginner-friendly structure described in `docs/ARCHITECTURE.md`.
- No React, Vue, Angular, TypeScript, Node.js backend, database, build tool or package dependencies for the MVP.
- No external APIs or authentication.
- The game must run in a modern browser from a local static server.
- Use semantic HTML and accessible buttons/labels.
- Store MVP progress in memory only. Do not add `localStorage` until explicitly requested in a later stage.

## 3. Educational constraints

- Prefer clear, readable code over clever abstractions.
- Use concepts currently covered by the students: variables, primitive types, conditions, `Math`, strings, objects, arrays, loops, functions, DOM and BOM.
- Do not introduce classes, complex design patterns, TypeScript, frameworks, state libraries or advanced tooling unless the user explicitly asks.
- Explain new JavaScript concepts before using them.
- Do not generate the entire project in one response. Implement only the requested roadmap stage.
- Keep code small enough for a beginner to read and explain.

## 4. Architecture rules

- Keep game data separate from rendering and event handling where practical.
- The player state is the source of truth for health, inventory, current room and game status.
- Do not directly edit the DOM from many unrelated places. Route UI updates through rendering functions.
- Do not duplicate game rules in click handlers. Event handlers call named game functions.
- Use stable item IDs and room IDs; do not identify game objects by their displayed text.
- Validate inventory and door requirements before changing rooms.
- Prevent actions after victory, defeat or timeout.
- Do not use `eval()` or execute user-provided strings as code.

## 5. Code style

- Use `const` by default and `let` only when reassignment is required.
- Use `camelCase` for variables and functions.
- Use descriptive names: `currentRoom`, `collectItem`, `renderInventory`.
- Use `===` and `!==`.
- Keep functions focused on one task.
- Avoid unexplained magic numbers; place game configuration in one object.
- Use double quotes for strings consistently.
- Add comments for game rules or non-obvious logic, not every line.
- Avoid inline JavaScript in HTML and avoid inline event attributes such as `onclick`.

## 6. Working process

For each task:
1. State which roadmap stage is being implemented.
2. Inspect the existing files before editing.
3. Give a short plan and list the files to change.
4. Implement the smallest complete slice.
5. Test it in the browser or provide exact manual test steps if browser testing is unavailable.
6. Report changed files, behavior implemented, tests performed and known limitations.
7. Update documentation if behavior or architecture changes.

Do not overwrite working features to make a task simpler. Do not silently remove existing behavior.

## 7. Definition of done

A task is complete only when:
- the requested behavior works;
- no unrelated feature was removed;
- browser console has no new errors;
- the relevant manual tests pass;
- the student can explain the code;
- documentation is updated if a rule or structure changed.
