# Bajarilgan ishlar

## Documentation arxitekturasi — 2024-11-23

**Maqsad:** Loyiha dokumentatsiyasini Vite + Tailwind CSS v4 stackiga moslashtirish.

### O'zgartirilgan fayllar

- [x] `AGENTS.md` — §2 "Technology stack": Vite, Tailwind CSS v4 ruxsat etildi, `src/main.js` struktura belgilandi
- [x] `docs/ARCHITECTURE.md` — Runtime flow, beginner va refactoring project structure yangilandi (`src/`, `public/`, `vite.config.js`)
- [x] `docs/PRODUCT_SPEC.md` — Technology qatoriga Tailwind CSS v4 va Vite qo'shildi
- [x] `docs/ROADMAP.md` — Stage 0 vazifalarini Vite + Tailwind setup ga o'zgartirildi
- [x] `docs/DECISIONS.md` — ADR-001 superseded; ADR-006 (Vite), ADR-007 (Tailwind v4), ADR-008 (libraries) qo'shildi
- [x] `README.md` — Tech stack tavsifi va quick start (`npm install` → `npm run dev`) yangilandi
- [x] `docs/CURRICULUM_MAP.md` — "Package managers" va "CSS frameworks" mavzulari qo'shildi, "bundlers" taqiqi olib tashlandi
- [x] `docs/UI_SPEC.md` — Tailwind utility class qoidasi qo'shildi
- [x] `docs/AI_WORKFLOW.md` — Constraint "HTML, Tailwind CSS and Vanilla JavaScript" ga yangilandi

### Qabul qilingan qarorlar

- Vite — dev server va build tool sifatida ishlatiladi
- Tailwind CSS v4 — asosiy styling vositasi (`@tailwindcss/vite` plugin bilan)
- `src/main.js` — Vite standart strukturasi bo'yicha
- MVP uchun qo'shimcha library kerak emas (faqat `tailwindcss` + `@tailwindcss/vite`)
- Boshqa library/framework lar keyingi bosqichlarda qo'shilishi mumkin (har biri `DECISIONS.md` da qayd qilinadi)
