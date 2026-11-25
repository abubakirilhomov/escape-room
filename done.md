# Bajarilgan ishlar

## Documentation arxitekturasi — 2026-11-23

**Maqsad:** Loyiha dokumentatsiyasini Vite + Tailwind CSS v4 stackiga moslashtirish.

### O'zgartirilgan fayllar

- [x] `AGENTS.md` — §2 "Technology stack": Vite, Tailwind CSS v4 ruxsat etildi
- [x] `docs/ARCHITECTURE.md` — Runtime flow, project structure yangilandi
- [x] `docs/PRODUCT_SPEC.md` — Technology qatoriga Tailwind CSS v4 va Vite qo'shildi
- [x] `docs/ROADMAP.md` — Stage 0 vazifalarini Vite + Tailwind setup ga o'zgartirildi
- [x] `docs/DECISIONS.md` — ADR-006 (Vite), ADR-007 (Tailwind v4), ADR-008 (libraries) qo'shildi
- [x] `README.md` — Tech stack tavsifi va quick start yangilandi
- [x] `docs/CURRICULUM_MAP.md` — Build tools va CSS frameworks mavzulari qo'shildi
- [x] `docs/UI_SPEC.md` — Tailwind utility class qoidasi qo'shildi
- [x] `docs/AI_WORKFLOW.md` — Constraint yangilandi

---

## Stage 0 — Project foundation — 2026-11-25

**Maqsad:** Vite + Tailwind CSS v4 loyiha asosini yaratish va jamoa uchun tayyorlash.

### Yaratilgan fayllar

- [x] `package.json` — Vite scripts (`dev`, `build`, `preview`)
- [x] `vite.config.js` — `@tailwindcss/vite` plugin bilan
- [x] `index.html` — Asosiy layout: header, main (room + sidebar), ending overlay
- [x] `src/style.css` — `@import "tailwindcss"`
- [x] `src/main.js` — CSS import + placeholder
- [x] `.gitignore` — node_modules, dist
- [x] `public/images/.gitkeep` — rasm papkasi
- [x] `public/sounds/.gitkeep` — ovoz papkasi

### Jamoa fayllari

- [x] `team/TEAM.md` — Jamoa ro'yxati, branch strategiya, qoidalar
- [x] `team/sarvar.md` — Header va Status Bar vazifasi
- [x] `team/ibrohim.md` — Room Panel vazifasi
- [x] `team/abdurahmon.md` — Inventory Panel vazifasi
- [x] `team/jahongir.md` — Feedback Panel va Game Ending vazifasi

### Qarorlar

- Har bir o'quvchiga alohida branch va UI section berildi
- index.html da TODO kommentlar bilan bo'limlar belgilandi
- Merge conflict lar minimal bo'lishi uchun section lar ajratilgan
