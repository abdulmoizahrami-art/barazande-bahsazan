# برازنده شمال — SvelteKit

## اجرا
```bash
npm install
npm run dev        # http://localhost:5173
npm run build      # خروجی آماده‌ی انتشار در پوشه‌ی build
npm run preview    # دیدن نسخه‌ی بیلد‌شده
```
نیاز: Node.js نسخه‌ی ۲۰ یا بالاتر.

## کجا چه چیزی هست
- `src/lib/data/site.js` ← همه‌ی متن‌ها (محصولات، مراحل، تماس)
- `src/app.css` ← رنگ‌ها و استایل پایه (TOKENS)
- `src/lib/components/` ← کامپوننت‌ها
- `src/routes/+page.svelte` ← صفحه‌ی اصلی
- `static/logo.png` ← لوگو
