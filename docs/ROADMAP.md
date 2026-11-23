# Development Roadmap

Build the game in small, reviewable stages. Do not skip ahead to advanced features.

## Stage 0 — Project foundation

**Goal:** Create the repository with Vite and Tailwind CSS v4, verify the dev server runs.

Tasks:
- Initialize project with `npm create vite@latest` (Vanilla JS template).
- Install Tailwind CSS: `npm install -D tailwindcss @tailwindcss/vite`.
- Configure `vite.config.js` with the `@tailwindcss/vite` plugin.
- Create `src/style.css` with `@import "tailwindcss"`.
- Create `src/main.js` with `import "./style.css"` and a placeholder initialization.
- Update `index.html`: link `src/main.js` as module, add semantic page structure.
- Verify `npm run dev` starts without errors.
- Add a simple page title and placeholder sections with Tailwind utility classes.

Acceptance criteria:
- `npm run dev` starts the Vite dev server.
- Page opens in the browser at the Vite URL.
- Tailwind utility classes render correctly.
- JavaScript file is loaded.
- No console errors.

## Stage 1 — Static game interface

**Topics:** HTML, CSS.

Tasks:
- Create header, health display, timer display.
- Create room panel and inventory panel.
- Add placeholder room text and buttons.
- Make layout responsive.

Acceptance criteria:
- Interface resembles the UI specification.
- Buttons and labels are readable.
- Layout works at desktop width and narrow width.

## Stage 2 — Player and room data

**Topics:** variables, types, objects, arrays.

Tasks:
- Create `gameState`.
- Define the four rooms in an array.
- Define items in an array.
- Display current room name and description from data.

Acceptance criteria:
- Changing `currentRoomId` and rendering displays the matching room.
- No room content is hardcoded into multiple UI functions.

## Stage 3 — Inventory

**Topics:** arrays, `includes`, `push`, `forEach`, functions.

Tasks:
- Add item collection.
- Prevent duplicate collection.
- Render inventory from state.
- Show an empty inventory state.

Acceptance criteria:
- Item appears once after collection.
- Inventory updates after state changes.
- Collected item is no longer available in the room.

## Stage 4 — Room navigation

**Topics:** conditions, objects, functions, DOM events.

Tasks:
- Add doors / room navigation.
- Check door requirements.
- Show helpful locked-door feedback.
- Change room only if access is allowed.

Acceptance criteria:
- Room 2 cannot be entered without the access card.
- Room changes update room name, description and available actions.

## Stage 5 — Puzzles

**Topics:** strings, string methods, conditions, functions.

Tasks:
- Add research terminal puzzle.
- Normalize answer with `trim()` and case conversion.
- Add security override puzzle.
- Store solved state in `gameState.progress`.

Acceptance criteria:
- Correct answer unlocks the corresponding progress flag.
- Wrong answer displays feedback and does not crash.
- Solved puzzle remains solved during the current game.

## Stage 6 — Timer and game endings

**Topics:** Math, BOM, functions, conditions.

Tasks:
- Add countdown using `setInterval`.
- Format seconds as minutes and seconds.
- Stop timer on win, loss and restart.
- Add victory and defeat panels.

Acceptance criteria:
- Timer decreases once per second.
- Timer never becomes negative.
- Victory / defeat can happen only once per run.
- Restart restores all initial values and starts one timer.

## Stage 7 — Polish and playtesting

Tasks:
- Improve visual feedback.
- Add room artwork / sound if time allows.
- Test all paths through the game.
- Fix console errors and layout issues.
- Ask another student to play without hints.

Acceptance criteria:
- A new player can understand the objective.
- All four rooms are reachable in the intended order.
- The game can be won and lost.
- Restart works from both endings.

## Stage 8 — Optional extensions

Only after MVP is stable:
- Save best time using `localStorage`.
- Add sound toggle.
- Add more rooms and alternate routes.
- Add a hint system with a limited number of hints.
- Add difficulty levels.
- Add a simple event log.

Each extension requires updating the data model and tests.

## Agent task rule

At the start of each session, tell the agent the exact stage and task. Ask it not to implement future stages unless explicitly requested.
