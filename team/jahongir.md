# 🥋 Jahongir — Game State va Feedback Logic (Stage 2)

> PUBG da o'yin boshlanganda sening HP = 100, backpack bo'sh, vaqt ketmoqda va o'yin holati "playing" bo'ladi. Shularning barchasini bitta JavaScript obyektida saqlaymiz — bu o'yinning "miyasi" (`gameState`)!

## 📋 Vazifa

**Branch:** `feature/game-state`

Stage 1 da sen zo'r ishlading! Endi `src/main.js` faylida o'yinning asosiy holatini (`gameState`) va o'zing yaratgan `#feedback-text` panelini boshqaruvchi funksiyani yozasan.

> ⚠️ **Muhim:** `index.html` fayliga tegma! Boshqa bolalar hozir `index.html` da ishlayapti, shuning uchun `src/main.js` da ishlaymiz.

---

## ✅ Nima qilish kerak

`src/main.js` faylini ochib, `import "./style.css";` dan keyin quyidagilarni qo'sh:

### 1-qadam: O'yin sozlamalari (`GAME_CONFIG`)

Raqamlarni shunchaki kod ichiga tashlab ketmaslik uchun ularni bitta obyektga yig'amiz:

```js
const GAME_CONFIG = {
  initialHealth: 100,
  initialTimeSeconds: 1800,
  startingRoomId: "reception"
};
```
- `1800` soniya = `30` daqiqa (`30 * 60`).
- Qo'shtirnoqlar doim ikkitalik (`"..."`) bo'lsin!

### 2-qadam: Boshlang'ich holatni yaratuvchi funksiya (`createInitialState`)

Har safar yangi o'yin yoki Restart bosilganda toza holat qaytaradigan funksiya:

```js
function createInitialState() {
  return {
    player: {
      name: "Player",
      health: GAME_CONFIG.initialHealth,
      inventory: []
    },
    currentRoomId: GAME_CONFIG.startingRoomId,
    timeLeft: GAME_CONFIG.initialTimeSeconds,
    status: "playing",
    progress: {
      researchTerminalUnlocked: false,
      securityDisabled: false
    }
  };
}

let gameState = createInitialState();
```
- `let gameState` — chunki Restart paytida unga yangi obyekt beriladi.
- `status` qiymatlari: `"playing"`, `"won"`, `"lost"`.

### 3-qadam: Feedback chiqarish funksiyasi (`renderFeedback`)

Stage 1 da sen `index.html` da `<p id="feedback-text">` yaratgan eding. Endi JS orqali uning matnini o'zgartiramiz:

```js
function renderFeedback(message) {
  const feedbackElement = document.querySelector("#feedback-text");
  if (!feedbackElement) {
    return;
  }
  feedbackElement.textContent = message;
}
```
- `document.querySelector("#feedback-text")` — HTML dan elementni ID bo'yicha topadi.
- `textContent` — matnni xavfsiz o'zgartiradi (`innerHTML` ishlatmaymiz!).

### 4-qadam: Boshlang'ich ishga tushirish (`initializeGame`)

Sahifa yuklanganda o'yinni boshlash va `renderFeedback` ni tekshirish:

```js
function initializeGame() {
  gameState = createInitialState();
  renderFeedback("Laboratoriya qulflandi. Chiqish yo'lini toping!");
  console.log("O'yin holati:", gameState);
}

initializeGame();
```

---

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. Brauzerda sahifani och:
   - O'ng pastki **📋 Log** panelida `"Laboratoriya qulflandi. Chiqish yo'lini toping!"` yozuvi ko'rinishi kerak.
3. **F12 → Console** ni och:
   - Hech qanday qizil xatolik yo'q.
   - `O'yin holati:` va uning ichida `player`, `currentRoomId: "reception"`, `timeLeft: 1800`, `status: "playing"` ko'rinishi kerak.
4. `npm run build` qilib ham tekshir — xatosiz yig'ilishi kerak.

---

## 💡 JavaScript tushuntirish

| Tushuncha | Nima qiladi |
|---|---|
| `const` | O'zgarmaydigan o'zgaruvchi (odatda shuni ishlatamiz) |
| `let` | Keyinroq qayta qiymat beriladigan o'zgaruvchi |
| `Object ({ ... })` | Ma'lumotlarni kalit-qiymat juftligida saqlaydi (`player.health`) |
| `Array ([])` | Ro'yxat saqlaydi (hozircha `inventory` bo'sh) |
| `function` | Qayta ishlatiladigan kod bloki |
| `document.querySelector` | HTML elementini JS da topib beradi |
| `textContent` | Element ichidagi matnni o'zgartiradi |
