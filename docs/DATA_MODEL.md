# Data Model

This document defines the shape of the data used by the MVP. It is plain JavaScript data, not a database schema.

## 1. Game state

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

### Field definitions

| Field | Type | Meaning |
|---|---|---|
| `player.name` | string | Player display name |
| `player.health` | number | Current health |
| `player.inventory` | array of strings | IDs of collected items |
| `currentRoomId` | string | ID of the room currently displayed |
| `timeLeft` | number | Remaining seconds |
| `status` | string | `playing`, `won` or `lost` |
| `progress.researchTerminalUnlocked` | boolean | Puzzle A completion |
| `progress.securityDisabled` | boolean | Puzzle B completion |

## 2. Room definition

```js
const rooms = [
    {
        id: "reception",
        name: "Reception",
        description: "You wake up in a silent reception room.",
        itemIds: ["access_card"],
        exits: [
            {
                targetRoomId: "research_lab",
                requirement: {
                    type: "item",
                    itemId: "access_card"
                }
            }
        ]
    }
];
```

A room contains:
- unique `id`;
- user-facing `name`;
- `description`;
- IDs of items available in the room;
- exits and their requirements.

## 3. Item definition

```js
const items = [
    {
        id: "access_card",
        name: "Access Card",
        description: "A staff card marked LEVEL 1.",
        roomId: "reception"
    }
];
```

An item is collected by adding its `id` to `gameState.player.inventory`. Do not store duplicate IDs.

## 4. Puzzle definition

```js
const puzzles = [
    {
        id: "research_terminal",
        title: "Research Terminal",
        clue: "Read the research note to discover the password.",
        answer: "ORION",
        resultFlag: "researchTerminalUnlocked"
    }
];
```

Normalize text input before comparison: trim whitespace and compare without case sensitivity. Do not expose the answer in the visible UI before the player solves the puzzle.

## 5. Stable identifiers

Use lowercase `snake_case` IDs:
- rooms: `reception`, `research_lab`, `security_room`, `emergency_exit`;
- items: `access_card`, `research_note`, `override_chip`;
- puzzles: `research_terminal`, `security_override`.

Changing a display name should not break game logic. Changing an ID requires updating every reference to that ID.

## 6. Data integrity rules

- Every ID must be unique within its entity type.
- Every `itemId` must refer to an existing item.
- Every `targetRoomId` must refer to an existing room.
- Inventory may contain only valid item IDs.
- A room cannot be entered if its requirement is not met.
- A completed puzzle must not become incomplete unless the game is restarted.
