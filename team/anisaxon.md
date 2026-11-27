# 🌸 Anisaxon — Start Screen (Tuzatish / Fix)

> Dizayning juda zo'r chiqdi! Ayniqsa laboratoriya kolbasi (SVG), yulduzli fon va matnlar juda chiroyli! 👏
> Lekin loyiha qoidalariga (`AGENTS.md`) to'liq mos kelishi uchun **3 ta kichik narsani** tuzatish kerak. Shundan keyin `main` ga qo'shamiz!

## 📋 Vazifa

**Branch:** `feature/start-screen`

Avval `main` dan yangilanishlarni ol:
```bash
git checkout feature/start-screen
git pull origin main
```

Keyin quyidagi 3 ta tuzatishni bajar:

---

## 🔧 Tuzatish 1: Tugmadagi `onmouseover` / `onmouseout` ni olib tashlash

`AGENTS.md` qoidasiga ko'ra HTML ichida `onmouseover`, `onmouseout`, `onclick` kabi inline JavaScript yozish **taqiqlangan**.

**Hozirgi holat (`index.html`):**
```html
<button id="start-button" class="..." style="..."
  onmouseover="this.style.boxShadow='...'; this.style.transform='scale(1.03)'"
  onmouseout="this.style.boxShadow='...'; this.style.transform='scale(1)'">
  🚀 O'yinni boshlash
</button>
```

**Qanday bo'lishi kerak (Tailwind bilan):**
```html
<button id="start-button" type="button" class="w-full bg-cyan-600 hover:bg-cyan-500 hover:scale-105 border border-cyan-400 text-white font-bold text-xl py-4 px-12 rounded-xl shadow-lg shadow-cyan-500/30 transition-all cursor-pointer focus:outline-none focus-visible:ring-2 focus-visible:ring-cyan-400">
  🚀 O'yinni boshlash
</button>
```
- `hover:bg-cyan-500` va `hover:scale-105` — sichqoncha ustiga kelganda rang o'zgaradi va biroz kattalashadi (JS kerak emas!)
- `transition-all` — animatsiya silliq bo'ladi
- `type="button"` — tugma turi aniq ko'rsatiladi

---

## 🔧 Tuzatish 2: Oddiy `style="..."` larni Tailwind class lariga almashtirish

Orqa fon gradienti va SVG rasm qolaversin — ular juda chiroyli! Lekin oddiy rang, shrift va bo'sh joylar uchun `style="..."` o'rniga Tailwind ishlat:

**Sarlavha:**
```html
<h1 class="text-4xl md:text-5xl font-bold text-cyan-400 mb-2">
  Escape Room
</h1>
<p class="text-base font-semibold text-cyan-300 tracking-widest mb-8">
  SECRET LABORATORY
</p>
```

**Hikoya paneli:**
```html
<div class="bg-cyan-950/40 border border-cyan-400/40 rounded-xl p-6 mb-8 text-left">
  <p class="text-white text-sm leading-relaxed mb-3">
    <span class="text-amber-400 font-semibold">⚠️ OGOHLANTIRISH:</span> Siz yer osti laboratoriyasida uyg'ondingiz.
  </p>
  <p class="text-white text-sm leading-relaxed mb-3">
    🔊 Sirena ovozi eshitilmoqda. Monitorda <span class="text-red-400 font-mono font-bold">"LOCKDOWN"</span> deb miltillayapti.
  </p>
  <p class="text-amber-400 font-semibold text-sm leading-relaxed">
    ⏱️ Laboratoriyadan <span class="text-red-400 font-mono font-bold">30 daqiqa</span> ichida chiqishingiz kerak!
  </p>
</div>
```

**Pastki matn:**
```html
<p class="text-cyan-300/60 text-sm tracking-wide mt-6">
  Xonalarni tekshiring &nbsp;·&nbsp; Buyumlarni yig'ing &nbsp;·&nbsp; Chiqish yo'lini toping
</p>
```

---

## 🔧 Tuzatish 3: `tasks.md` ni toza saqlash

- `tasks.md` ning tepasiga yangi bo'lim qo'shma — pastda allaqachon `Anisaxon — Start Screen` bo'limi bor.
- O'sha mavjud bo'limdagi `[ ]` larni `[x]` qilib belgilab qo'y.

---

## 🧪 Tekshirish

1. `npm run dev` ishga tushir va tugma ustiga sichqoncha olib borganda kattalashishini tekshir.
2. `npm run build` xatosiz o'tishini tekshir.
3. F12 → Console da xatolik yo'q.
4. Commit va push qil:
   ```bash
   git add index.html tasks.md
   git commit -m "fix: start screen Tailwind class larga o'tkazildi, inline JS olib tashlandi"
   git push origin feature/start-screen
   ```
