# Pivot Area Calculator — حاسبة مساحة البيفوت

تطبيق ويب خفيف **يعمل بدون إنترنت** بعد أول فتح، بدون إعلانات، قابل للتثبيت على شاشة الهاتف (Android / iOS) كأيقونة مستقلة.

A lightweight offline-first PWA for center-pivot irrigation: tracks per wheel and area per wheel (Feddan). No ads, no external scripts.

---

## الملفات (هيكل المشروع)

```
pivot-area-calculator/
├── index.html              # التطبيق كامل (واجهة + معادلات)
├── sw.js                   # Service Worker — تخزين مؤقت للعمل أوفلاين
├── manifest.webmanifest    # بيان PWA (اسم، أيقونات، عرض standalone)
├── icon-192.png
├── icon-512.png
├── icon-maskable-512.png
└── README.md
```

لا توجد مكتبات خارجية — كل شيء محلي داخل الملفات أعلاه.

---

## الرفع على GitHub + النشر المجاني

### 1) إنشاء مستودع ورفع الملفات

```bash
cd pivot-area-calculator
git init
git add .
git commit -m "Pivot Area Calculator — offline PWA"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/pivot-area-calculator.git
git push -u origin main
```

### 2) تفعيل GitHub Pages

1. افتح المستودع على GitHub → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)` → Save
4. بعد دقيقة يظهر الرابط مثل:  
   `https://YOUR_USERNAME.github.io/pivot-area-calculator/`

افتح الرابط مرة واحدة على الهاتف (بإنترنت) حتى يُخزَّن التطبيق، بعدها يعمل **بدون نت**.

---

## التثبيت على الشاشة الرئيسية

| الجهاز | الطريقة |
|--------|---------|
| **Android (Chrome)** | زر ⬇️ الأخضر يظهر أول مرة → اضغطه، أو قائمة المتصفح ← «تثبيت التطبيق» / «إضافة إلى الشاشة الرئيسية». بعد التثبيت يختفي الزر. |
| **iPhone / iPad (Safari)** | مشاركة ⎙ ← «إضافة إلى الشاشة الرئيسية». (Safari لا يدعم زر التثبيت التلقائي؛ التطبيق يعرض تلميحاً عند الضغط على ⬇️) |

الأيقونة تظهر بشعار البرنامج (الدائرة الزرقاء مع العجلات الصفراء).

---

## المميزات

- يعمل أوفلاين بالكامل بعد أول زيارة (Service Worker)
- بدون إعلانات وبدون تتبع
- عربي / إنجليزي + وضع داكن
- ماركات جاهزة (Valley / Zimmatic / Western) + ماركات مخصصة محفوظة محلياً
- المعادلات كما هي (مساحة تراكمية حسب نصف القطر والجرر)

---

## ملاحظات تقنية

- `manifest.webmanifest` مطلوب لـ Android ولتثبيت PWA.
- `sw.js` يخزّن: الصفحة، المانيفست، والأيقونات.
- البيانات المحلية (الماركات المحفوظة، اللغة، الثيم) في `localStorage` على الجهاز فقط.
- لتجربة محلية: أي خادم ثابت على المنفذ (مثال: `npx serve .`) — Service Worker لا يعمل من `file://`.

---

**تصميم:** مهندس محمد إبراهيم (فرمينيو)  
المعادلات مبنية على معادلة بيرو.
