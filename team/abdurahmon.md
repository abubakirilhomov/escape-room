# 🎒 Abdurahmon — Inventory Panel

> PUBG da backpack ochib nima borligini ko'rasan — qurol, dori, armor. Bu o'yinda ham shunday panel bor. O'yinchi topgan narsalar shu yerda ko'rinadi!

## 📋 Vazifa

**Branch:** `feature/inventory-panel`

`index.html` dagi `<!-- ===== ABDURAHMON: Inventory Panel ===== -->` qismini to'ldir.

## ✅ Nima qilish kerak

### 1-qadam: Panel tashqi ko'rinishi
`<section id="inventory-panel">` ga class lar qo'sh:
```html
<section id="inventory-panel" class="bg-gray-900 rounded-lg border border-gray-700 p-4">
  <!-- ichiga elementlar ketadi -->
</section>
```

### 2-qadam: Sarlavha
```html
<h3 class="text-md font-bold text-cyan-300 mb-2">🎒 Inventory</h3>
```

### 3-qadam: Buyumlar ro'yxati (hozircha bo'sh)
```html
<ul id="inventory-list" class="space-y-1">
  <li class="text-gray-500 text-sm italic">Hech narsa yo'q</li>
</ul>
```
- `space-y-1` — har bir `<li>` orasiga kichik bo'sh joy
- `italic` — kursiv shrift (bo'sh holat ekanligini ko'rsatadi)

### 4-qadam: Buyum namunasi (placeholder)
Keyinroq JavaScript qo'shganda buyumlar shunday ko'rinadi. Hozircha qo'shib ko'r, keyin o'chirib tashlaysan:
```html
<ul id="inventory-list" class="space-y-1">
  <li class="text-gray-300 text-sm flex items-center gap-2 bg-gray-800 rounded p-2">
    <span>🪪</span>
    <span>Access Card</span>
  </li>
  <li class="text-gray-300 text-sm flex items-center gap-2 bg-gray-800 rounded p-2">
    <span>📝</span>
    <span>Research Note</span>
  </li>
</ul>
```
- `bg-gray-800` — har bir buyum uchun biroz ochroq fon
- `rounded` — kichik yumaloq burchak
- `flex items-center gap-2` — emoji va matn yonma-yon

> ⚠️ **Muhim:** Test qilib ko'rgandan keyin namuna buyumlarni o'chirib, faqat bo'sh holatni ("Hech narsa yo'q") qoldir. JavaScript da buyumlar dinamik qo'shiladi.

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. Brauzerda o'ng tomonda (kichik ekranda pastda) quyidagilar ko'rinishi kerak:
   - "🎒 Inventory" sarlavhasi
   - "Hech narsa yo'q" matni (kulrang, kursiv)
3. Namuna buyumlarni qo'shganda har biri alohida qator da, emoji bilan ko'rinadi
4. Consol da xatolik yo'q

## 💡 Tailwind tushuntirish

| Class | Nima qiladi |
|---|---|
| `bg-gray-900` | Qorong'i fon (panel) |
| `bg-gray-800` | Biroz ochroq fon (buyum) |
| `rounded-lg` | Katta yumaloq burchak (panel) |
| `rounded` | Kichik yumaloq burchak (buyum) |
| `p-4` | Ichidan 4 unit padding |
| `space-y-1` | `<li>` lar orasiga vertikal bo'sh joy |
| `italic` | Kursiv (egik) shrift |
| `text-gray-500` | Och kulrang matn (bo'sh holat) |
| `flex items-center gap-2` | Yonma-yon, markazlangan, 2 unit oraliq |
