# UI Specification

## 1. Visual direction

Theme: mysterious science-fiction research facility.

Suggested visual language:
- dark charcoal / near-black background;
- muted steel panels;
- restrained cyan or green accent;
- amber for warnings;
- red for critical health or defeat;
- monospace font for terminal text, readable sans-serif for normal UI.

Avoid excessive glow, tiny text and low-contrast labels. The interface should be usable on a classroom projector.

## 2. Main game screen

### Header / status bar

Contains:
- game title or facility identifier;
- health value and health bar;
- countdown timer;
- current room label.

### Main room panel

Contains:
- room image or placeholder illustration;
- room name;
- room description;
- interactive objects / action buttons.

### Interaction panel

May show:
- inspect object;
- collect item;
- use terminal;
- enter password;
- move through a door;
- activate emergency exit.

Only show actions that make sense in the current room. If an action is unavailable, show why.

### Inventory panel

Contains:
- heading `Inventory`;
- collected item names;
- short descriptions on selection or inspection;
- empty-state text when no items are collected.

### Feedback area

Displays short messages:
- item collected;
- door locked and requirement missing;
- incorrect password;
- puzzle solved;
- game won or lost.

Feedback should be visible without requiring the player to inspect the browser console.

## 3. Screens / overlays

1. **Start screen** (optional): title, short story, Start button.
2. **Playing screen**: room, status, inventory and interactions.
3. **Puzzle dialog/panel**: clue, text input and submit button.
4. **Victory screen**: success message and Restart.
5. **Defeat screen**: reason for failure and Restart.

## 4. Interaction requirements

- Use `<button>` for actions.
- Use `<label>` with puzzle inputs.
- Keyboard focus must be visible.
- Enter may submit a puzzle form.
- Buttons must have clear labels.
- Do not rely on hover as the only way to reveal important information.
- On narrow screens, stack the room and inventory panels vertically.

## 5. DOM structure suggestion

```html
<body>
  <header class="game-header">
    <!-- title and status -->
  </header>

  <main class="game-layout">
    <section class="room-panel" aria-labelledby="room-title">
      <!-- room content and actions -->
    </section>

    <aside class="sidebar">
      <section class="inventory-panel">
        <!-- inventory -->
      </section>
      <section class="feedback-panel" aria-live="polite">
        <!-- game feedback -->
      </section>
    </aside>
  </main>

  <section class="game-ending" hidden>
    <!-- victory / defeat -->
  </section>
</body>
```

This is a suggested structure, not a requirement to copy without understanding.

**Styling note:** Use Tailwind CSS utility classes directly on HTML elements for layout, spacing, colors and typography. Use semantic class names or `id` attributes only when JavaScript needs to query the element (e.g., `id="room-title"`, `id="inventory-panel"`).
