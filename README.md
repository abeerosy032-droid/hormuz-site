# موقع بين الصفر وهرمز | Zero to Hormuz

موقع تعليمي يربط بين ثلاثة مواضيع: الصفر، OpenClaw، ومضيق هرمز.

## المحتوى

- **الصفر (Zero)**: تاريخ وأهمية الصفر في الرياضيات
- **OpenClaw**: بوابة الذكاء الاصطناعي المستضافة ذاتياً
- **مضيق هرمز (Strait of Hormuz)**: الممر المائي الاستراتيجي

## النشر على Cloudflare Pages

### الطريقة 1: عبر Git

1. أنشئ مستودع Git جديد:
```bash
cd /home/abeerosy032/.openclaw/workspace/hormuz-site
git init
git add .
git commit -m "Initial commit"
```

2. اربط المستودع بـ GitHub/GitLab

3. في Cloudflare Dashboard:
   - اذهب إلى Pages
   - أنشئ مشروع جديد
   - اختر "Connect to Git"
   - اختر المستودع
   - اضغط "Save and Deploy"

### الطريقة 2: عبر Wrangler CLI

1. ثبت Wrangler:
```bash
npm install -g wrangler
```

2. سجّل الدخول:
```bash
wrangler login
```

3. أنشئ المشروع:
```bash
cd /home/abeerosy032/.openclaw/workspace/hormuz-site
wrangler pages project create hormuz-site
```

4. انشر الموقع:
```bash
wrangler pages deploy . --project-name=hormuz-site
```

### الطريقة 3: Direct Upload

1. في Cloudflare Dashboard:
   - اذهب إلى Pages
   - اضغط "Create a project"
   - اختر "Upload assets"
   - ارفع مجلد `hormuz-site`
   - اضغط "Deploy site"

## الملفات

- `index.html` - الصفحة الرئيسية
- `README.md` - هذا الملف

## التقنيات المستخدمة

- HTML5
- CSS3 (مع Flexbox و Grid)
- تصميم متجاوب (Responsive)
- دعم RTL للعربية

## المميزات

- تصميم عصري مع تدرجات لونية
- تأثيرات hover تفاعلية
- بطاقات إحصائيات
- خط زمني
- دعم كامل للعربية والإنجليزية
- متجاوب مع جميع الأجهزة

## الترخيص

MIT License