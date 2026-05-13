# منصة المقارنة المباشرة | ZeroClaw vs OpenClaw vs Hermes

منصة وموقع مخصص للمقارنة المباشرة بين أنظمة الذكاء الاصطناعي والأدوات التحليلية (ZeroClaw و OpenClaw و Hermes)، بالإضافة إلى ارتباطها بمختبر تقييم نماذج الذكاء الاصطناعي (Gemini و GLM-5 وغيرها).

## 🚀 حول المشروع

هذا المستودع يحتوي على الأكواد المصدرية لموقع المقارنة النهائي، والذي يتيح واجهة مستخدم تفاعلية (HTML/CSS/JS) ومزود بـ **Cloudflare Worker** كوسيط آمن للتخاطب مع الـ APIs الخاصة بنماذج الذكاء الاصطناعي لضمان إخفاء المفاتيح السرية عن الواجهة الأمامية.

## 🔗 الروابط المباشرة

- **الموقع المباشر (المقارنات):** [https://hormuz-site.pages.dev](https://hormuz-site.pages.dev)
- **مختبر التقييم المباشر لنماذج AI:** [http://34.136.31.84:8080/](http://34.136.31.84:8080/)

## 📂 بنية المشروع

- `public/index.html` - الصفحة الرئيسية للمقارنة ومحادثة الـ AI.
- `worker.js` - كود Cloudflare Worker ليعمل كمخدم وكيل (Proxy) آمن يخفي الـ API Keys.
- `wrangler-worker.toml` - إعدادات تكوين ونشر الـ Worker عبر Wrangler.
- `README.md` - هذا الملف.

## 🛠 التقنيات المستخدمة

- **Frontend:** HTML5, TailwindCSS (عبر الـ CDN), Vanilla JavaScript, Marked.js (لتحويل Markdown إلى HTML منسق).
- **Backend/Proxy:** Cloudflare Workers.
- **التكامل:** Gemini API, OpenClaw APIs.

## ☁️ آلية النشر والتحديث (Cloudflare)

### 1. نشر الموقع الثابت (Cloudflare Pages)
```bash
wrangler pages deploy public/ --project-name=hormuz-site
```

### 2. نشر مخدم الوكيل (Cloudflare Worker)
```bash
# نشر الـ Worker 
wrangler deploy -c wrangler-worker.toml

# إعداد مفتاح API بشكل آمن كمتغير بيئة (Secret)
wrangler secret put GEMINI_API_KEY -c wrangler-worker.toml
```

## 🔒 آلية الحماية والأمان

لضمان عدم تسريب مفاتيح الـ API في الكود المصدري للمتصفح، يتم إرسال أسئلة المستخدم من الـ Frontend إلى الـ Worker الخاص بنا، حيث يقوم الـ Worker بإرفاق المفتاح السري وإرسال الطلب بشكل آمن إلى سيرفرات مزود الـ AI، ثم يقوم بإرجاع النتيجة (مُنسقة كـ Markdown) ليتم تقديمها إلى المستخدم بسلاسة عبر `marked.js`.

---
*تم تطوير وصيانة هذا المشروع ضمن مختبرات تقييم الذكاء الاصطناعي (OpenClaw Environment).*
