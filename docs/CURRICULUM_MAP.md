# Curriculum Map — JavaScript Topics in the Game

This project is designed to reinforce the topics already covered in class. It should not become an excuse to skip the fundamentals.

| Course topic | Game feature | Student practice |
|---|---|---|
| Introduction to JavaScript | Initialize game | Variables, `console.log`, script loading |
| Data types and arithmetic | Health, timer, player name | strings, numbers, booleans, arithmetic |
| `Math` and conditional operators | Timer, puzzle checks, random optional events | `Math.floor`, comparisons, `if/else` |
| String methods | Password input | `trim`, `toUpperCase`, `toLowerCase`, `includes` |
| Object | Player, room, item | Read and update object properties |
| Array | Rooms, items, inventory | `push`, `includes`, `find` (when taught) |
| `for` and `forEach` | Render room items and inventory | Iterate over collections |
| DOM and BOM | Update panels, handle clicks, countdown | `querySelector`, `textContent`, events, `setInterval` |
| Functions | Game actions and rendering | Parameters, return values, reusable logic |
| Package managers and build tools | Project setup, dev server | `npm install`, `npm run dev`, `package.json`, Vite |
| CSS frameworks | UI styling and layout | Tailwind utility classes, responsive design, `@import` |

## Teaching checkpoints

After each feature, ask students to explain:

1. What data is stored?
2. Which function changes that data?
3. Which function updates the page?
4. What happens if the user gives invalid input?
5. How can we test the feature?

## Avoid premature concepts

Do not require students to learn all of these for the MVP:
- classes and inheritance;
- complex closures;
- async/await and network requests;
- state-management libraries;
- advanced algorithms.

If an agent introduces one of these concepts, ask it to rewrite the solution using the current course level or explain why the concept is genuinely necessary.
