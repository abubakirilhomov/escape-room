# Vazifalar

## Stage 0 — Project foundation ✅ TAYYOR

- [x] Vite + Tailwind CSS v4 loyiha yaratildi
- [x] `vite.config.js`, `package.json` sozlandi
- [x] `src/style.css` va `src/main.js` yaratildi
- [x] `index.html` asosiy layout bilan yaratildi
- [x] `npm run dev` ishlaydi
- [x] Jamoa fayllari tayyorlandi

## Stage 1 — Static game interface ⬅️ hozirgi bosqich

### Sarvar — Header va Status Bar (`feature/header-status`)
- [ ] Game title qo'shish
- [ ] Health display (❤️ 100, yashil)
- [ ] Timer display (⏱️ 30:00, sariq)
- [ ] Responsive layout (flex, justify-between)
- [ ] Batafsil: `team/sarvar.md`

### Ibrohim — Room Panel (`feature/room-panel`)
- [ ] Room title va description qo'shish
- [ ] Action button lar (Tekshirish, Eshik ochish)
- [ ] Panel styling (bg-gray-900, rounded, border)
- [ ] Hover effect lar
- [ ] Batafsil: `team/ibrohim.md`

### Abdurahmon — Inventory Panel (`feature/inventory-panel`)
- [ ] Inventory sarlavha va ro'yxat
- [ ] Bo'sh holat ("Hech narsa yo'q")
- [ ] Buyum namunasi (placeholder, keyin o'chiriladi)
- [ ] Panel styling
- [ ] Batafsil: `team/abdurahmon.md`

### Jahongir — Feedback Panel va Game Ending (`feature/feedback-ending`) ✅ TAYYOR
- [x] Feedback panel (Log sarlavha + xabar matni)
- [x] Game ending overlay (hidden, markazda panel)
- [x] Restart button
- [x] Overlay test va `hidden` qaytarish
- Batafsil: `team/jahongir.md`

### Anisaxon — Start Screen (`feature/start-screen`) 🔄 TUZATISH KERAK
- [x] O'yin nomi (Escape Room + Secret Laboratory)
- [x] Hikoya matni (qorong'i panelda)
- [x] "O'yinni boshlash" tugmasi (moviy, katta)
- [x] Responsive dizayn (telefon va kompyuter uchun)
- [ ] **Fix:** Tugmadagi `onmouseover`/`onmouseout` ni olib tashlab Tailwind `hover:` ishlatish
- [ ] **Fix:** Matn va ranglardagi inline `style="..."` larni Tailwind class lariga o'tkazish
- [ ] **Fix:** `tasks.md` da dublikat bo'lim qo'shmaslik
- Batafsil: `team/anisaxon.md`

---

## Stage 2 — Player and room data

### Jahongir — Game State va Feedback Logic (`feature/game-state`)
- [ ] `GAME_CONFIG` va `createInitialState()` yaratish (`src/main.js`)
- [ ] `gameState` obyektini sozlash (`player`, `currentRoomId`, `timeLeft`, `status`, `progress`)
- [ ] `renderFeedback(message)` funksiyasini yozish
- [ ] `initializeGame()` bilan test qilish
- [ ] Batafsil: `team/jahongir.md`

### Keyingi vazifalar (Stage 1 tugagach taqsimlanadi)
- [ ] 4 ta xonani array da aniqlash (`rooms`)
- [ ] Item larni array da aniqlash (`items`)
- [ ] Joriy xona nomi va tavsifini data dan ko'rsatish (`renderRoom`)

## Stage 3 — Inventory

- [ ] Item yig'ish funksiyasi
- [ ] Takroriy yig'ishni oldini olish
- [ ] Inventory ni state dan render qilish
- [ ] Bo'sh inventory holati

## Stage 4 — Room navigation

- [ ] Eshik / xona navigatsiyasi
- [ ] Eshik talablarini tekshirish
- [ ] Qulflangan eshik uchun feedback
- [ ] Ruxsat bo'lgandagina xona almashtirish

## Stage 5 — Puzzles

- [ ] Research terminal puzzle
- [ ] Javobni normalize qilish
- [ ] Security override puzzle
- [ ] Yechilgan holatni saqlash

## Stage 6 — Timer and game endings

- [ ] Countdown timer
- [ ] Vaqt formatlash
- [ ] Victory va defeat panel lari
- [ ] Restart funksiyasi

## Stage 7 — Polish and playtesting

- [ ] Vizual feedback yaxshilash
- [ ] Barcha yo'llarni test qilish
- [ ] Bug fix

## Stage 8 — Optional extensions

- [ ] `localStorage` bilan best time
- [ ] Sound toggle
- [ ] Qo'shimcha xonalar
