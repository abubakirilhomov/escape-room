# Product Specification

## 1. Product overview

**Name:** Escape Room: Secret Laboratory  
**Type:** Single-player, browser-based puzzle / escape-room game  
**Platform:** Desktop browser first; responsive layout as a secondary requirement  
**Technology:** HTML, Tailwind CSS v4, Vanilla JavaScript, Vite  
**Audience:** Students learning beginner JavaScript

## 2. Product goal

The player must escape from a locked underground laboratory by exploring rooms, collecting useful objects, reading clues, solving puzzles and unlocking doors before the countdown reaches zero.

The educational goal is equally important: students should implement the game in small stages and connect each feature to a JavaScript topic.

## 3. MVP success criteria

The MVP is successful when a player can:

1. Start a new game.
2. See the current room and its description.
3. Inspect and collect available items.
4. See collected items in an inventory.
5. interact with a computer puzzle and submit a password.
6. Unlock a door when the required condition is satisfied.
7. Move through all required rooms.
8. Reach the exit and see a victory screen.
9. Lose if the timer reaches zero or health reaches zero.
10. Restart the game.

## 4. Scope

### Included in MVP

- One player.
- Four connected rooms.
- One countdown timer.
- Health points.
- Inventory with collectible items.
- Room descriptions and clues.
- At least two puzzle interactions.
- Locked doors and item/flag requirements.
- Victory, defeat and restart states.
- Basic sound can be postponed; it is not required for MVP.

### Not included in MVP

- Multiplayer or online leaderboard.
- Accounts, authentication or cloud saves.
- Backend, database or API.
- Procedural room generation.
- Real encryption or real computer hacking.
- Mobile touch controls as a primary feature.
- Complex combat system.
- Monetization or advertisements.

## 5. Target experience

The interface should feel like a mysterious, slightly tense science-fiction laboratory. It should remain readable and usable: game text must be clear, important actions must be obvious, and puzzle instructions must not rely only on color.

## 6. Design principles

- The player should always understand their current objective.
- Every collectible item should have a purpose or provide a clue.
- A locked door should explain what is missing when the player tries it.
- Wrong answers should provide feedback without making the game unwinnable.
- The game should not require guessing arbitrary passwords without clues.
- Restart must restore the initial state completely.

## 7. MVP assumptions

The first version uses a fixed sequence of rooms and fixed puzzle answers. The 30-minute timer is a game setting, not a real-world security mechanism. Health is a simple game mechanic and does not need to reach zero in normal play unless a future hazard mechanic is added.
