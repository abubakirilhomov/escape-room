# Game Design Document

## 1. Story

The player wakes up in the reception area of an underground research facility. The facility has entered emergency lockdown. A terminal announces that the emergency protocol will destroy the facility in 30 minutes.

The player must explore the facility, find access items, understand the clues left by the staff and reach the emergency exit.

## 2. Main game loop

1. Read the room description.
2. Inspect available objects and clues.
3. Collect useful items.
4. Try available interactions.
5. Solve the room's puzzle or satisfy its door requirement.
6. Move to the next room.
7. Reach the exit before the timer ends.

## 3. Rooms

### Room 1 — Reception

**Purpose:** Tutorial room; introduces inspection and collecting.

- Starting room.
- Contains an access card.
- Contains a short note hinting that the research wing requires Level 1 access.
- Door to Room 2 requires `access_card`.

### Room 2 — Research Laboratory

**Purpose:** Introduces clues and password validation.

- Contains a research note with a clue.
- Contains a terminal interaction.
- Player must infer and enter a password from the clue.
- Solving the terminal sets `researchTerminalUnlocked = true`.
- Door to Room 3 requires the terminal to be unlocked.

### Room 3 — Security Room

**Purpose:** Combines inventory and puzzle state.

- Contains a security console.
- Player must have the access card and have solved the research terminal.
- A second puzzle or override code disables the lockdown.
- Solving it sets `securityDisabled = true`.
- Door to Room 4 requires `securityDisabled`.

### Room 4 — Emergency Exit

**Purpose:** Final check and ending.

- The exit is interactable.
- If security is disabled, the player can escape and win.
- Otherwise, the game explains what is still required.
- Successful escape changes game status to `won`.

## 4. Items

| ID | Display name | Description | Purpose |
|---|---|---|---|
| `access_card` | Access Card | A staff access card | Opens the research wing |
| `research_note` | Research Note | A note with a clue | Helps solve the terminal puzzle |
| `override_chip` | Override Chip | A security override component | Optional key item for the security console |

The final list of items may be adjusted during implementation, but IDs must remain stable and unique.

## 5. Puzzle design

Puzzles must be solvable from clues found in the game.

### Puzzle A — Research terminal

- Location: Research Laboratory.
- Input: text password.
- Clue: a note provides a short riddle or a clearly discoverable code.
- Correct answer: configured in game data, not scattered across click handlers.
- On success: show success feedback and set `researchTerminalUnlocked = true`.
- On failure: show a helpful error. Do not remove items or permanently block progress.

### Puzzle B — Security override

- Location: Security Room.
- Input: a short override code or a simple sequence puzzle.
- Prerequisite: player has the access card and solved Puzzle A.
- On success: set `securityDisabled = true`.
- On failure: show feedback and allow another attempt.

**Implementation note:** Keep the initial puzzle answers in local JavaScript game data. This is a learning game, not a secure system; answers in client-side code can be inspected.

## 6. Health and timer

- Initial health: 100.
- Initial countdown: 30 minutes (1800 seconds).
- Timer decreases once per second while the game is active.
- When remaining time reaches zero, status becomes `lost`.
- If a future hazard reduces health to zero, status becomes `lost`.
- MVP does not need random damage or combat. Do not invent damage rules without updating this document.

## 7. Victory and defeat

### Victory

Requirements:
- Player is in Room 4.
- Security system is disabled.
- Player activates the exit.

Show a victory panel with elapsed time or remaining time and a Restart button.

### Defeat

Triggered when:
- Timer reaches zero; or
- Health reaches zero (only if a health-loss mechanic is implemented).

Show a defeat panel and a Restart button.

## 8. Feedback and usability

- Every interaction gives visible feedback.
- Inventory indicates when an item is collected.
- A collected item cannot be collected twice.
- Locked doors explain the missing requirement.
- A wrong password does not crash the game.
- The player cannot continue interacting after the game ends.
