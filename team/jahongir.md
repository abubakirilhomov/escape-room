# 🥋 Jahongir — Feedback Panel va Game Ending

> PUBG da o'yin oxirida "Winner Winner Chicken Dinner" yoki "Better Luck Next Time" chiqadi. Bu o'yinda ham shunday! Plus, o'yin davomida xabarlar chiqadigan panel bo'ladi — kill feed ga o'xshab.

## 📋 Vazifa

**Branch:** `feature/feedback-ending`

`index.html` dagi ikki joyni to'ldir:
1. `<!-- ===== JAHONGIR: Feedback Panel ===== -->` — o'yin ichidagi xabarlar
2. `<!-- ===== JAHONGIR: Game Ending Overlay ===== -->` — o'yin yakuniy ekrani

---

## ✅ 1-qism: Feedback Panel

### 1-qadam: Panel tashqi ko'rinishi
`<section id="feedback-panel">` ga class lar qo'sh:
```html
<section id="feedback-panel" class="bg-gray-900 rounded-lg border border-amber-700/50 p-4" aria-live="polite">
  <!-- ichiga elementlar ketadi -->
</section>
```
- `border-amber-700/50` — sariqish chegara (50% shaffof)
- `aria-live="polite"` — ekran o'quvchi uchun (accessibility)

### 2-qadam: Sarlavha
```html
<h3 class="text-md font-bold text-amber-400 mb-2">📋 Log</h3>
```

### 3-qadam: Xabar matni
```html
<p id="feedback-text" class="text-gray-400 text-sm">
  Maxfiy laboratoriyaga xush kelibsiz...
</p>
```

---

## ✅ 2-qism: Game Ending Overlay

### 1-qadam: Ichki panel
`<section id="game-ending">` ning ichiga qo'sh:
```html
<div class="bg-gray-900 border border-gray-600 rounded-xl p-8 text-center max-w-md">
  <h2 id="ending-title" class="text-2xl font-bold mb-4">🏆 Tabriklaymiz!</h2>
  <p id="ending-message" class="text-gray-300 mb-6">
    Siz laboratoriyadan muvaffaqiyatli chiqdingiz!
  </p>
  <button id="restart-button" class="bg-cyan-600 hover:bg-cyan-500 text-white font-bold py-2 px-6 rounded-lg transition-colors">
    🔄 Qaytadan o'ynash
  </button>
</div>
```

### Qanday ishlaydi

Tashqi `<section id="game-ending">` da `class="hidden"` bor — shuning uchun ko'rinmaydi. JavaScript keyin `hidden` ni olib tashlaydi va overlay ko'rinadi:
- `fixed inset-0` — butun ekranni qoplaydi
- `bg-black/80` — qora fon, 80% shaffof (orqadagi o'yin ko'rinib turadi)
- `z-50` — eng ustki qatlam

### 2-qadam: Test uchun ko'rish

Overlay qanday ko'rinishini ko'rmoqchi bo'lsang, `hidden` class ni vaqtincha o'chir:
```html
<!-- hidden o'chirilgan — faqat test uchun! -->
<section id="game-ending" class="fixed inset-0 bg-black/80 flex items-center justify-center z-50">
```
> ⚠️ **Muhim:** Test qilib ko'rgandan keyin `hidden` ni qaytib qo'y!

## 🧪 Tekshirish

1. `npm run dev` ishga tushir
2. **Feedback panel** (o'ng pastda):
   - "📋 Log" sarlavhasi (sariq)
   - "Maxfiy laboratoriyaga xush kelibsiz..." matni
   - Sariqish chegara bilan panel
3. **Game ending** (hidden o'chirganda):
   - Butun ekranni qoplaydigan qora shaffof fon
   - Markazda oq panel: sarlavha, xabar, button
   - "Qaytadan o'ynash" button iga sichqoncha olib borganda rang o'zgaradi
4. `hidden` ni qaytib qo'y va overlay yo'qolganini tekshir
5. Consol da xatolik yo'q

## 💡 Tailwind tushuntirish

| Class | Nima qiladi |
|---|---|
| `fixed inset-0` | Butun ekranni qoplaydi (overlay) |
| `bg-black/80` | Qora fon, 80% shaffoflik |
| `z-50` | Eng yuqori qatlam (boshqa element lar ustida) |
| `hidden` | Element ni yashiradi (ko'rinmaydi) |
| `rounded-xl` | Katta yumaloq burchak |
| `text-center` | Matnni markazga tekislaydi |
| `max-w-md` | Panelning maksimal kengligi (o'rtacha) |
| `border-amber-700/50` | Sariqish chegara, 50% shaffof |
| `aria-live="polite"` | Ekran o'quvchi yangi xabarni aytib beradi |
