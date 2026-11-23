# Test Plan

Testing should be performed in the browser. The browser console should remain open during development.

## 1. Startup

- [ ] Page loads without errors.
- [ ] Initial room is Reception.
- [ ] Health starts at 100.
- [ ] Timer starts at 30:00.
- [ ] Inventory is empty.
- [ ] Game status is `playing`.

## 2. Inventory

- [ ] Access Card can be collected in Reception.
- [ ] Access Card appears in inventory.
- [ ] Access Card cannot be collected twice.
- [ ] Collected item is no longer offered as available in the room.
- [ ] Inventory is cleared on restart.

## 3. Navigation

- [ ] Research Laboratory is locked without Access Card.
- [ ] Locked message explains the missing requirement.
- [ ] Player can enter Research Laboratory after collecting Access Card.
- [ ] Player cannot jump directly to later rooms.
- [ ] Current room display updates after navigation.

## 4. Puzzles

- [ ] Empty password is rejected with a helpful message.
- [ ] Incorrect password is rejected.
- [ ] Password with extra spaces is normalized.
- [ ] Password with different letter casing is normalized.
- [ ] Correct password unlocks the research terminal.
- [ ] Solved state remains true while playing.
- [ ] Security puzzle cannot be bypassed by clicking unrelated UI.

## 5. Timer and endings

- [ ] Timer decreases once per second.
- [ ] Timer displays minutes and seconds correctly.
- [ ] Timer reaching zero causes defeat.
- [ ] Timer stops after defeat.
- [ ] Activating the exit with all requirements causes victory.
- [ ] Exit cannot be activated after the game ends.
- [ ] Restart resets room, inventory, health, timer and progress.
- [ ] Restart does not create multiple running timers.

## 6. UI and accessibility

- [ ] All actions can be activated with keyboard.
- [ ] Focus state is visible.
- [ ] Feedback is readable.
- [ ] Puzzle input has a label.
- [ ] Layout does not overflow at narrow width.
- [ ] Important information is not communicated by color alone.

## 7. Regression test

After each new stage, replay the previously completed stages. A new feature must not break item collection, navigation, puzzles or restart.
