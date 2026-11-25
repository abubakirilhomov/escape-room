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

## 2. Technology stack

- Use HTML5, Tailwind CSS v4 and Vanilla JavaScript.
- Use Vite as the development server and build tool.
- Use Tailwind CSS utility classes for styling. Write custom CSS only when Tailwind utilities are insufficient.
- Vite uses ES modules (`type="module"`) natively. Keep all game logic in a single `src/main.js` file until the roadmap reaches the modularization stage.
- Additional libraries may be introduced when the roadmap requires them. Record each new dependency in `docs/DECISIONS.md`.
- No React, Vue, Angular or TypeScript for the MVP.
- No backend server, database or external APIs.
- The game must run through the Vite dev server (`npm run dev`) during development.
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

## 8. Git workflow rules

This project uses a branch-based workflow. The teamlead manages `main`. Each student works on their own feature branch.

### Branch rules

- **Never commit or push directly to `main`.** Only the teamlead merges into `main`.
- Each student has an assigned branch (see `team/TEAM.md`). Create it from the latest `main`:
  ```
  git checkout main
  git pull origin main
  git checkout -b feature/[branch-name]
  ```
- If the branch already exists remotely, check it out instead of creating a new one:
  ```
  git checkout feature/[branch-name]
  git pull origin feature/[branch-name]
  ```
- Do not create branches outside your assignment without teamlead approval.

### Commits

- Commit after every small, meaningful change — not at the end of a long session.
- Write commit messages in lowercase Uzbek or English, describing what was done:
  ```
  git add .
  git commit -m "header ga health display qo'shildi"
  ```
- Do not commit `node_modules/`, `dist/` or `.DS_Store`. These are in `.gitignore`.
- Do not commit broken code that crashes on load. Run `npm run dev` and check the browser before committing.

### Push and pull

- Always pull before starting work:
  ```
  git pull origin feature/[branch-name]
  ```
- Push your branch when a task is finished or at the end of a session:
  ```
  git push origin feature/[branch-name]
  ```
- Do not run `git push origin main`.

### Merging

- **Do not merge your branch into `main` yourself.** Tell the teamlead when your task is ready.
- Do not run `git merge main` into your branch unless the teamlead asks you to.
- If the teamlead asks you to update your branch from `main`, use:
  ```
  git checkout feature/[branch-name]
  git pull origin main
  ```
  Resolve any conflicts, then commit and push.

### Conflict resolution

- If `git pull` reports a merge conflict, do not force-push or delete files.
- Open the conflicted file, look for `<<<<<<<`, `=======` and `>>>>>>>` markers.
- Keep the correct version of both changes, remove the markers, then:
  ```
  git add .
  git commit -m "merge conflict hal qilindi"
  ```
- If the conflict is unclear, stop and ask the teamlead.

### Forbidden commands

Do not run these commands without explicit teamlead permission:
- `git push --force` or `git push -f`
- `git reset --hard`
- `git rebase`
- `git merge main` (into your branch)
- `git branch -D` (deleting branches)
- Any command that rewrites history on a shared branch.
