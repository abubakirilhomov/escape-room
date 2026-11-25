# 🌸 Anisaxon — Start Screen (Boshlang'ich Ekran)

> O'yinga kirganda birinchi ko'rinadigan ekran — xuddi kitob muqovasi kabi. Chiroyli sarlavha, qiziqarli hikoya va "Boshlash" tugmasi. Sening vazifang — o'yinchini shu ekrandan qiziqtirib, o'yinga tortish!

## 📋 Vazifa

**Branch:** `feature/start-screen`

`index.html` dagi `<!-- ===== ANISAXON: Start Screen ===== -->` qismini to'ldir.

## ✅ Nima qilish kerak

### 1-qadam: Ichki panel yaratish

`<section id="start-screen">` ning ichiga markaziy panel qo'sh:

```html
<div class="text-center max-w-lg px-6">
  <!-- ichiga elementlar ketadi -->
</div>
```
- `text-center` — hamma narsa markazda
- `max-w-lg` — panel juda keng bo'lmasligi uchun
- `px-6` — yon tomonlardan bo'sh joy

### 2-qadam: O'yin nomi (sarlavha)

```html
<h1 class="text-4xl md:text-5xl font-bold text-cyan-400 mb-4">
  🔬 Escape Room
</h1>
<p class="text-xl text-gray-400 mb-8">Secret Laboratory</p>
```
- `text-4xl` — katta shrift (telefonlarda)
- `md:text-5xl` — katta ekranda yanada kattaroq
- `text-cyan-400` — moviy rang (laboratoriya uslubi)
- `mb-8` — pastdan katta bo'sh joy

### 3-qadam: Hikoya matni

```html
<div class="bg-gray-900 rounded-xl border border-gray-700 p-6 mb-8 text-left">
  <p class="text-gray-300 mb-3">
    ⚠️ Siz yer osti laboratoriyasida uyg'ondingiz.
  </p>
  <p class="text-gray-300 mb-3">
    Sirena ovozi eshitilmoqda. Monitorda "LOCKDOWN — 30 daqiqa" deb yozilgan.
  </p>
  <p class="text-amber-400">
    ⏱️ Laboratoriyadan 30 daqiqa ichida chiqishingiz kerak!
  </p>
</div>
```
- `rounded-xl` — katta yumaloq burchaklar
- `text-left` — matn chapga tekislangan (panel ichida)
- `text-amber-400` — sariq rang (ogohlantirish uchun)

### 4-qadam: Boshlash tugmasi

```html
<button id="start-button" class="bg-cyan-600 hover:bg-cyan-500 text-white font-bold text-lg py-3 px-10 rounded-xl transition-colors">
  🚀 O'yinni boshlash
</button>
```
- `py-3 px-10` — tugma katta va bosiladigan
- `hover:bg-cyan-500` — sichqoncha ustiga kelganda yorqinlashadi
- `rounded-xl` — yumaloq burchaklar
- `transition-colors` — rang o'zgarishi smooth

### 5-qadam: Pastki matn (bonus)

Agar vaqt bo'lsa, tugma ostiga kichik matn qo'sh:

```html
<p class="text-gray-600 text-sm mt-6">
  Xonalarni tekshiring. Buyumlarni yig'ing. Chiqish yo'lini toping.
</p>
```

## 🎨 Qanday ko'rinishi kerak

```
┌──────────────────────────────────┐
│                                  │
│        🔬 Escape Room            │
│       Secret Laboratory          │
│                                  │
│  ┌────────────────────────────┐  │
│  │ ⚠️ Siz yer osti           │  │
│  │ laboratoriyasida           │  │
│  │ uyg'ondingiz...            │  │
│  │                            │  │
│  │ ⏱️ 30 daqiqa ichida       │  │
│  │ chiqishingiz kerak!        │  │
│  └────────────────────────────┘  │
│                                  │
│      [ 🚀 O'yinni boshlash ]    │
│                                  │
│   Xonalarni tekshiring.         │
│   Buyumlarni yig'ing.           │
│   Chiqish yo'lini toping.       │
│                                  │
└──────────────────────────────────┘
```

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. Brauzerda ochilganda **birinchi bo'lib** start screen ko'rinishi kerak:
   - "🔬 Escape Room" sarlavhasi (katta, moviy)
   - "Secret Laboratory" (kulrang)
   - Hikoya matni (qora panelda)
   - "🚀 O'yinni boshlash" tugmasi (moviy)
3. Tugma ustiga sichqoncha olib borganda rang o'zgaradi
4. Orqadagi o'yin ekrani ko'rinmaydi (start screen butun ekranni qoplaydi)
5. Brauzer oynasini toraytirganda hammasi to'g'ri ko'rinadi
6. Consol da xatolik yo'q (F12 → Console)

> 💡 **Eslatma:** Hozircha tugma bosilganda hech narsa bo'lmaydi — bu normal! JavaScript keyingi stage da qo'shiladi. Sening vazifang — faqat chiroyli ko'rinish yaratish.

## 💡 Tailwind tushuntirish

| Class | Nima qiladi |
|---|---|
| `fixed inset-0` | Butun ekranni qoplaydi |
| `flex items-center justify-center` | Ichidagi elementni markazga qo'yadi |
| `z-50` | Eng ustki qatlam (boshqa narsa ustida ko'rinadi) |
| `text-4xl` | Juda katta shrift |
| `md:text-5xl` | Katta ekranda yanada kattaroq shrift |
| `max-w-lg` | Maksimal kenglikni cheklaydi |
| `rounded-xl` | Katta yumaloq burchaklar |
| `bg-gray-900` | Qorong'i fon |
| `text-cyan-400` | Moviy matn |
| `text-amber-400` | Sariq matn (ogohlantirish) |
| `hover:bg-cyan-500` | Sichqoncha ustida yorqinroq rang |
| `transition-colors` | Rang o'zgarishini sekin (animated) qiladi |
