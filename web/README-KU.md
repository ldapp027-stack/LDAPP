# بڵاوکردنەوەی وێب تەنها (بێ موبایل)

ئەم فۆڵدەرە **تەنها وێب**ە — بۆ upload / Vercel / Netlify.

| فۆڵدەر | چییە | لینک نمونە |
|--------|------|-----------|
| `web/store` | فرۆشگای کڕیار | `https://ldstore.com` |
| `web/admin` | پانێڵی ئەدمین | `https://admin.ldstore.com` |

---

## نوێکردنەوەی بیلد (پێش بڵاوکردنەوە)

لە ڕەگی پڕۆژە:

```powershell
cd "C:\Users\Laptop Duhok\Desktop\LD APP"
npm run prepare:web
```

یان:

```powershell
powershell -ExecutionPolicy Bypass -File .\scripts\prepare-web.ps1
```

ئەمە `ld-app` + `admin-web` بیلد دەکات و دووبارە دەیانخاتە ناو `web/`.

---

## ڕێگای ١ — Vercel (باشترین)

### فرۆشگا
1. [vercel.com](https://vercel.com) → Add New Project
2. **Upload** فۆڵدەری `web/store`  
   یان Git → Root Directory: `web/store` (دوای push)
3. Deploy — دۆمەین دەگرێت

### ئەدمین
هەمان شت بۆ `web/admin` (پڕۆژەی جیا)

> تێبینی: کلیلەکانی `EXPO_PUBLIC_*` / `VITE_*` لە کاتی بیلددا ناو کۆدەکەن. ئەگەر `.env` بگۆڕیت، دووبارە `npm run prepare:web` بکە.

---

## ڕێگای ٢ — Netlify Drop (خێراترین، بێ حسابی Git)

1. بڕۆ بۆ [app.netlify.com/drop](https://app.netlify.com/drop)
2. فۆڵدەری `web/store` ڕاکێشە سەر پەڕەکە
3. لینک دەستبەجێ دەردەکەوێت

بۆ ئەدمین: `web/admin` جیا ڕاکێشە.

---

## ڕێگای ٣ — هەر هاستێکی ستاتیک (cPanel / Hostinger)

1. ناوەڕۆکی `web/store` زیپ بکە
2. Upload بکە بۆ `public_html` (یان subdirectory)
3. دڵنیابە `index.html` لە ڕەگدایە

---

## گرنگ

- **موبایل (Play/App Store)** لێرە نییە — تەنها وێب
- فرۆشگا و ئەدمین **دوو سایت**ن؛ هەمان داتابەیس (Supabase) بەکاردەهێنن
- دوای گۆڕانکاری لە کۆد: هەمیشە `npm run prepare:web` پێش deploy
