# Vazifalar

## Stage 0 — Project foundation ⬅️ hozirgi bosqich

- [ ] `npm create vite@latest` bilan loyiha yaratish (Vanilla JS template)
- [ ] `npm install -D tailwindcss @tailwindcss/vite` o'rnatish
- [ ] `vite.config.js` da `@tailwindcss/vite` plugin sozlash
- [ ] `src/style.css` yaratish (`@import "tailwindcss"`)
- [ ] `src/main.js` yaratish (`import "./style.css"` + placeholder init)
- [ ] `index.html` yangilash: `src/main.js` module sifatida ulash, semantic struktura
- [ ] `npm run dev` ishlashini tekshirish
- [ ] Placeholder section lar Tailwind class lar bilan qo'shish

## Stage 1 — Static game interface

- [ ] Header, health display, timer display yaratish
- [ ] Room panel va inventory panel yaratish
- [ ] Placeholder room text va button lar qo'shish
- [ ] Responsive layout (Tailwind breakpoints bilan)

## Stage 2 — Player and room data

- [ ] `gameState` object yaratish
- [ ] 4 ta xonani array da aniqlash
- [ ] Item larni array da aniqlash
- [ ] Joriy xona nomi va tavsifini data dan ko'rsatish

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
- [ ] Javobni `trim()` va case conversion bilan normalize qilish
- [ ] Security override puzzle
- [ ] Yechilgan holatni `gameState.progress` da saqlash

## Stage 6 — Timer and game endings

- [ ] `setInterval` bilan countdown
- [ ] Sekundlarni minut:sekund formatida ko'rsatish
- [ ] Win, loss va restart da timer to'xtatish
- [ ] Victory va defeat panel lari

## Stage 7 — Polish and playtesting

- [ ] Vizual feedback yaxshilash
- [ ] Room artwork / sound (vaqt bo'lsa)
- [ ] Barcha yo'llarni test qilish
- [ ] Console error va layout muammolarni tuzatish

## Stage 8 — Optional extensions

- [ ] `localStorage` bilan eng yaxshi vaqtni saqlash
- [ ] Sound toggle
- [ ] Qo'shimcha xonalar
- [ ] Hint tizimi
- [ ] Qiyinlik darajalari
