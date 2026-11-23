# Technical Architecture

## 1. Architecture summary

The MVP is a small client-side application. It uses a simple layered structure:

1. **Game data** — static definitions of rooms, items and puzzles.
2. **Game state** — current mutable state of the player and game.
3. **Game logic** — rules for collecting, moving, solving and ending.
4. **UI rendering** — functions that display state in the DOM.
5. **Event handling** — connects user actions to game logic.

The goal is separation of responsibilities without introducing advanced patterns that distract beginner students.

## 2. Runtime flow

```text
Vite dev server
   |
   +--> index.html
          |
          +--> src/style.css (@import "tailwindcss")
          |
          +--> src/main.js (import "./style.css")
                 |
                 +--> initializeGame()
                 |       |
                 |       +--> createInitialState()
                 |       +--> renderGame()
                 |       +--> startTimer()
                 |
                 +--> Event listeners
                         |
                         +--> Game logic
                         |      +--> collectItem()
                         |      +--> moveToRoom()
                         |      +--> submitPuzzleAnswer()
                         |      +--> activateExit()
                         |
                         +--> render functions
                                +--> renderRoom()
                                +--> renderInventory()
                                +--> renderStatus()
                                +--> renderFeedback()
```

## 3. Suggested project structure

### Beginner stage

Start with the standard Vite + Tailwind CSS v4 structure:

```text
escape-room/
├── index.html
├── vite.config.js
├── package.json
├── public/
│   ├── images/
│   └── sounds/
├── src/
│   ├── style.css
│   └── main.js
├── README.md
├── AGENTS.md
└── docs/
```

Students should initially be able to find all JavaScript logic in `src/main.js`. This makes the relationship between functions and state visible.

### Later refactoring stage (only when the class is ready)

If `src/main.js` becomes too large, split it into ES modules within `src/`:

```text
escape-room/
├── index.html
├── vite.config.js
├── package.json
├── public/
│   ├── images/
│   └── sounds/
└── src/
    ├── style.css
    ├── main.js
    ├── data/
    │   ├── rooms.js
    │   ├── items.js
    │   └── puzzles.js
    ├── state/
    │   └── gameState.js
    ├── logic/
    │   ├── inventory.js
    │   ├── navigation.js
    │   ├── puzzles.js
    │   └── timer.js
    └── ui/
        ├── render.js
        └── events.js
```

Do not create this modular structure before students understand functions, objects, arrays and imports/exports.

## 4. Responsibilities

| Area | Responsibility | Must not do |
|---|---|---|
| Data | Define rooms, items, puzzle metadata | Change live player state |
| State | Hold current game values | Render HTML |
| Logic | Apply game rules and update state | Directly build large HTML fragments |
| UI | Read state and update DOM | Decide whether a door is actually unlocked |
| Events | Read user input and call logic | Contain all game rules inline |

## 5. State ownership

The game state is the single source of truth. The DOM is a visual representation of that state.

Example:

```js
const gameState = {
    player: {
        name: "Player",
        health: 100,
        inventory: []
    },
    currentRoomId: "reception",
    timeLeft: 1800,
    status: "playing",
    progress: {
        researchTerminalUnlocked: false,
        securityDisabled: false
    }
};
```

When state changes, call the appropriate render function. Do not treat text currently displayed in the DOM as the source of game data.

## 6. Main functions

| Function | Responsibility |
|---|---|
| `initializeGame()` | Set up a new game and event listeners |
| `createInitialState()` | Return a fresh initial state |
| `renderGame()` | Update all main UI areas |
| `renderRoom()` | Display the current room |
| `renderInventory()` | Display collected items |
| `collectItem(itemId)` | Validate and collect an item |
| `hasItem(itemId)` | Check inventory |
| `canEnterRoom(roomId)` | Check room access conditions |
| `moveToRoom(roomId)` | Change current room if allowed |
| `submitPuzzleAnswer(puzzleId, answer)` | Validate an answer and update progress |
| `startTimer()` | Start the countdown |
| `endGame(status)` | Finish the game once |
| `restartGame()` | Reset state and restart |

Function names can change if there is a clear reason, but responsibilities should remain distinct.

## 7. Important implementation rules

- Use IDs for rooms and items, not visible names.
- Do not use `innerHTML` with untrusted user input. Prefer `textContent` for player-provided text.
- Attach event listeners from JavaScript.
- Avoid registering duplicate listeners every time the screen renders.
- Keep timer interval ID so it can be cleared at game end and restart.
- Clear the old timer before starting a new one.
- Make `endGame()` idempotent: calling it twice must not create multiple end screens or intervals.
- Validate state before every important transition.
- Keep puzzle answers in one data definition.
- Use one function to refresh the UI after a state change.

## 8. State machine

Allowed game statuses:

- `menu` — start screen (optional first iteration).
- `playing` — game active.
- `won` — player escaped.
- `lost` — timer or health reached zero.

Only `playing` may transition to `won` or `lost`. Restart creates a fresh state and returns to `playing` (or `menu` if a start screen is implemented).
