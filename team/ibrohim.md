# 🏟️ Ibrohim — Room Panel

> PUBG da map ochib xonalarga kirgandek — bu o'yinda ham har bir xonaning o'z ko'rinishi bor. Sen shu xona ekranini yaratasan!

## 📋 Vazifa

**Branch:** `feature/room-panel`

`index.html` dagi `<!-- ===== IBROHIM: Room Panel ===== -->` qismini to'ldir.

## ✅ Nima qilish kerak

### 1-qadam: Xona nomi
```html
<h2 id="room-title" class="text-lg font-bold text-cyan-300 mb-2">Reception</h2>
```
- `id="room-title"` — JavaScript keyinroq shu ID orqali topadi
- `text-lg` — katta shrift
- `font-bold` — qalin
- `text-cyan-300` — moviy rang
- `mb-2` — pastdan bo'sh joy

### 2-qadam: Xona tavsifi
```html
<p id="room-description" class="text-gray-300 mb-4">
  Siz jim qolgan qabul xonasida uyg'ondingiz. Devorga biriktirilgan monitor "LOCKDOWN" deb miltillayapti.
</p>
```

### 3-qadam: Amallar bo'limi
```html
<div id="room-actions" class="flex flex-wrap gap-2">
  <button class="bg-cyan-700 hover:bg-cyan-600 text-white py-2 px-4 rounded-lg transition-colors">
    🔍 Tekshirish
  </button>
  <button class="bg-cyan-700 hover:bg-cyan-600 text-white py-2 px-4 rounded-lg transition-colors">
    🚪 Eshikni ochish
  </button>
</div>
```
- `flex flex-wrap gap-2` — buttonlar yonma-yon turadi
- `hover:bg-cyan-600` — sichqoncha ustiga kelganda rang o'zgaradi
- `transition-colors` — rang o'zgarishi smooth bo'ladi

### 4-qadam: Section ga fon berish
Tashqi `<section>` ga class lar qo'sh:
```html
<section id="room-panel" class="flex-1 bg-gray-900 rounded-lg border border-gray-700 p-6" aria-labelledby="room-title">
```
- `bg-gray-900` — qora fon
- `rounded-lg` — yumaloq burchak
- `border border-gray-700` — chegara
- `p-6` — ichidan 6 unit bo'sh joy

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. Brauzerda ochilgan sahifada quyidagilar ko'rinishi kerak:
   - "Reception" sarlavhasi (moviy rangda)
   - Xona tavsifi (kulrang matn)
   - "Tekshirish" va "Eshikni ochish" button lari
   - Qora fon, yumaloq burchakli panel
3. Button ustiga sichqoncha olib borganda rang o'zgaradi
4. Consol da hech qanday xatolik yo'q (F12 → Console)

## 💡 Tailwind tushuntirish

| Class | Nima qiladi |
|---|---|
| `bg-gray-900` | Fon rangini qora-kulrang qiladi |
| `text-cyan-300` | Matn rangini moviy qiladi |
| `rounded-lg` | Burchaklarni yumaloqlaydi |
| `p-6` | Ichidan 6 unit padding beradi |
| `mb-4` | Pastdan 4 unit margin beradi |
| `flex` | Flexbox layout yoqadi |
| `gap-2` | Element lar orasiga bo'sh joy qo'yadi |
| `hover:` | Faqat sichqoncha ustida bo'lganda ishlaydi |
| `transition-colors` | Rang o'zgarishini sekin (animated) qiladi |
