# 💻 Sarvar — Header va Status Bar

> YouTube dagi live stream larda ko'rasan — yuqorida subscriber count, timer, boshqa stat lar turadi. Shu narsani o'yinga qo'shasan!

## 📋 Vazifa

**Branch:** `feature/header-status`

`index.html` dagi `<!-- ===== SARVAR: Header va Status Bar ===== -->` qismini to'ldir.

## ✅ Nima qilish kerak

### 1-qadam: Ichki layout
Header ning ichiga container qo'sh:
```html
<div class="max-w-5xl mx-auto flex items-center justify-between">
  <!-- ichiga elementlar ketadi -->
</div>
```
- `max-w-5xl` — maksimal kenglik (juda keng bo'lib ketmasligi uchun)
- `mx-auto` — markazga joylash
- `flex` — elementlarni yonma-yon qo'yish
- `items-center` — vertikal markazlash
- `justify-between` — chap va o'ng tomonga tarqatish

### 2-qadam: O'yin nomi
```html
<h1 class="text-xl font-bold text-cyan-400">🔬 Secret Laboratory</h1>
```

### 3-qadam: Status ko'rsatkichlari
```html
<div class="flex items-center gap-6">
  <div id="health-display" class="text-sm">
    ❤️ Health: <span id="health-value" class="font-mono text-green-400">100</span>
  </div>
  <div id="timer-display" class="text-sm">
    ⏱️ Time: <span id="timer-value" class="font-mono text-amber-400">30:00</span>
  </div>
</div>
```
- `gap-6` — health va timer orasiga katta bo'sh joy
- `font-mono` — raqamlar uchun monospace shrift (aniqroq ko'rinadi)
- `text-green-400` — health yashil rangda
- `text-amber-400` — timer sariq rangda
- `id` lar — JavaScript keyinroq bu element larni topadi

### 4-qadam: Room label (bonus)
Agar vaqt bo'lsa, status qatoriga joriy xona nomini qo'sh:
```html
<div id="current-room-label" class="text-sm text-gray-400">
  📍 <span id="current-room-name">Reception</span>
</div>
```

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. Brauzerda sahifaning yuqorisida quyidagilar ko'rinishi kerak:
   - "🔬 Secret Laboratory" nomi (chapda)
   - "❤️ Health: 100" (o'ngda, yashil raqam)
   - "⏱️ Time: 30:00" (o'ngda, sariq raqam)
3. Brauzer oynasini toraytirganda elementlar bir-birining ustiga chiqmaydi
4. Consol da xatolik yo'q (F12 → Console)

## 💡 Tailwind tushuntirish

| Class | Nima qiladi |
|---|---|
| `flex` | Elementlarni yonma-yon qo'yadi (flexbox) |
| `items-center` | Vertikal o'rtaga tekislaydi |
| `justify-between` | Birinchi element chapda, oxirgisi o'ngda turadi |
| `gap-6` | Elementlar orasiga bo'sh joy qo'yadi |
| `text-xl` | Shriftni kattalashtiradi |
| `font-mono` | Monospace (barcha harflar bir xil kenglikda) shrift |
| `text-green-400` | Yashil rang |
| `text-amber-400` | Sariq-to'q rang |
| `max-w-5xl mx-auto` | Kontentni markazga cheklangan kenglikda qo'yadi |
