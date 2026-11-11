# SprichDe — Render.com'ga deploy (bepul, karta talab qilinmaydi)

Ilovaning haqiqiy havolasi: **https://sprichde-original.onrender.com/**
(bu nomni Render service yaratilganda "Instance Name" sifatida yozish kerak)

> **DIQQAT — public xavf:** admin panel hozircha parolsiz ishlaydi. Internetdagi har kim
> `/admin.html` ochib o'quvchi ma'lumotlarini va parollarini ko'rishi, o'chirib tashlashi mumkin.

## 5 daqiqada deploy

1. **https://render.com** → GitHub hisobingiz bilan kiring (4.qadamdagi repo ko'rinadi)
2. **New +** → **Web Service** → manba tanlash: **GitHub**
   - birinchi marta bo'lsa: **Configure account** → Render'ga `mobile-app` repoga kirish ruxsatini bering
3. **Repository tanlang**: `khusanovumarbek/mobile-app`, branch: `main`
4. Sozlamalar (render.yaml avtomatik aniqlanadi):
   - Instance Name: **sprichde-original**
   - Runtime: Python 3
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python backend/server.py`
   - Instance Type: **Free**
5. **Environment variables** (agar avtomatik qolmagan bo'lsa):
   - `SPRICHDE_HOST` = `0.0.0.0`
   - `SPRICHDE_PORT` = `10000`
   - `SPRICHDE_OPEN` = `none`
6. **Create Web Service** → 1–3 daqiqada build tugaydi → havola shu bo'ladi:
   **https://sprichde-original.onrender.com/**

## Havolalar

| Sahifa | URL |
|--------|-----|
| Ilova (kirish) | https://sprichde-original.onrender.com/ |
| Admin panel | https://sprichde-original.onrender.com/admin.html |
| Demo o'quvchi | `+998 90 111 22 33` / `demo1234` (va bekzod `+998 91 222 33 44` / dilnoza `+998 93 333 44 55`) |
| Admin | admin@sprichde.uz / admin123 |

## Muhim ogohlantirishlar

1. **Bepul Render 15 daqiqa faoliyatsizlikdan keyin uxlaydi** — birinchi ochilish 30–60 sekund davom etadi
2. **Baza vaqtinchalik** — har restart/deploy'da o'quvchilar va to'lovlar demo holatiga qaytadi
   (bu demo uchun me'yoriy; real ma'lumotlar uchun Postgres kerak)
3. **Admin panel parolsiz** — o'quvchilar ma'lumotlari ochiq; yo'l sifatida public qilsangiz, o'quvchilar
   bazasini ochiq ko'rmang; yopish uchun 1 daqiqada admin himoyasini yoqib beraman
4. **Telefonda o'rnatish (PWA)**: Android Chrome → "Ilovani o'rnatish"; iPhone Safari → Share → "Bosh ekranga qo'shish"
5. **Bepul plan davet/har qanday narsa uchun yetarli** — lekin professional ishlatish uchun pullik plan ($7/oy)
   kerak bo'ladi (tezroq + unlimited bandwidth)
