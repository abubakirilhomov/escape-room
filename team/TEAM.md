# Jamoa

## A'zolar

| Ism | Yosh | Qiziqishlari | Branch | Vazifa (Stage 1) |
|---|---|---|---|---|
| Ibrohim | 15 | Futbol, PUBG | `feature/room-panel` | Room Panel — asosiy o'yin ekrani |
| Sarvar | 14 | IT, YouTube | `feature/header-status` | Header va Status Bar — health, timer |
| Jahongir | 12 | Taekwondo, PUBG | `feature/feedback-ending` | Feedback Panel va Game Ending overlay |
| Abdurahmon | 13 | Futbol, PUBG | `feature/inventory-panel` | Inventory Panel — buyumlar ro'yxati |

## Ish tartibi

1. `main` branch dan o'z branch ingni yarat:
   ```bash
   git checkout main
   git pull origin main
   git checkout -b feature/[seniki]
   ```
2. Faqat o'z vazifangni bajar — boshqalarning kodiga tegma
3. Har bir kichik o'zgarishdan keyin commit qil:
   ```bash
   git add .
   git commit -m "qisqa tavsif"
   ```
4. Tayyor bo'lganda push qil:
   ```bash
   git push origin feature/[seniki]
   ```
5. Teamlead tekshiradi va `main` ga merge qiladi

## Qoidalar

- ⛔ `main` branch ga to'g'ridan-to'g'ri yozish mumkin emas
- ✅ Faqat o'z section ingga HTML va Tailwind class lar qo'sh
- ✅ `npm run dev` da xatosiz ishlashini tekshir
- ✅ Tushunmagan narsani so'ra — yashirma
- ✅ Har bir commit da nima qilganingni yoz

## Foydali buyruqlar

```bash
npm run dev          # dev serverni ishga tushirish
git status           # o'zgarishlarni ko'rish
git log --oneline    # commit tarixini ko'rish
git diff             # nima o'zgarganini ko'rish
```
