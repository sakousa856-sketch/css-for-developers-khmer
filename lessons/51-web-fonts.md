# មេរៀនទី ៥១៖ ការទាញយក Web Fonts ផ្ទាល់ខ្លួន (CSS @font-face)

> **CSS `@font-face` អនុញ្ញាតឱ្យ Developers ផ្ទុកពុម្ពអក្សរផ្ទាល់ខ្លួន (Custom Fonts) ពី Server មកប្រើប្រាស់លើគេហទំព័រ ទោះបីជាកុំព្យូទ័ររបស់អ្នកប្រើប្រាស់គ្មាន Font នោះក៏ដោយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្រើប្រាស់ `@font-face` rule ត្រឹមត្រូវតាមស្តង់ដារ
* ស្គាល់ទម្រង់ឯកសារ Font ទំនើប **WOFF2 (Web Open Font Format 2)**
* យល់ពី Property `font-display: swap` ដើម្បីបង្កើនល្បឿន Render អត្ថបទ

---

## 🔤 Syntax នៃ `@font-face`

```css
@font-face {
  font-family: 'KhmerCustomFont';
  src: url('fonts/KhmerCustomFont.woff2') format('woff2'),
       url('fonts/KhmerCustomFont.woff') format('woff');
  font-weight: 400;
  font-style: normal;
  font-display: swap; /* បង្ហាញ System font បណ្តោះអាសន្នពេល Font កំពុងទាញយក */
}

/* យកទៅប្រើប្រាស់ */
body {
  font-family: 'KhmerCustomFont', sans-serif;
}
```

---

## ⚡ ហេតុអ្វីបានជាត្រូវប្រើ `font-display: swap`?

ប្រសិនបើគ្មាន `font-display: swap` ទេ នៅពេលដែល Internet យឺត Browser នឹងលាក់អត្ថបទទាំងអស់បាត់ (មើលឃើញតែផ្ទៃសទទេ - ហៅថា **FOIT: Flash of Invisible Text**) រហូតដល់ Font ទាញយកចប់។

* **`font-display: swap`:** បញ្ជាឱ្យ Browser បង្ហាញពុម្ពអក្សរ System Fallback ជាបន្ទាន់ភ្លាមៗសិន ហើយនៅពេលដែល Custom Font ទាញយកចប់ វានឹង **ប្តូរ (Swap)** មក Custom Font ដោយស្វ័យប្រវត្តិ។

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS @font-face Demo</title>
  <style>
    /* Register Custom Font */
    @font-face {
      font-family: 'MyLocalFont';
      src: local('Helvetica Neue'), local('Arial');
      font-display: swap;
    }

    body {
      font-family: 'MyLocalFont', sans-serif;
      padding: 30px;
      line-height: 1.6;
    }
  </style>
</head>
<body>

  <h1>ស្វាគមន៍មកកាន់ការប្រើប្រាស់ Custom Web Fonts</h1>
  <p>កូដ <code>@font-face</code> ជួយឱ្យគេហទំព័រមាន Brand Identity ផ្ទាល់ខ្លួនច្បាស់លាស់។</p>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ប្រើតែទម្រង់ WOFF2 ជាចម្បង:** WOFF2 ត្រូវបានបង្ហាប់ (Compression) តូចជាង TTF/OTF រហូតដល់ 30-50% ដែលជួយឱ្យគេហទំព័រ Load លឿនបំផុត។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. សរសេរ `@font-face` rule មួយសម្រាប់ Font ឈ្មោះ `BrandFont` ដោយប្រើទម្រង់ `.woff2` និងមាន `font-display: swap;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `@font-face` rule allows custom fonts to be downloaded and used on a website.
* `WOFF2` is the modern, highly compressed font format recommended for web use.
* `font-display: swap` prevents FOIT (Flash of Invisible Text) by rendering fallback fonts until custom fonts load.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>51</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៥១</strong> នៃ <strong>៦០</strong></p>

| [← Prev](50-text-effects.md) | [01](01-introduction.md) | ... | [49](49-shadows-and-rounded.md) | [50](50-text-effects.md) | **[ 51 ]** | [52](52-2d-transforms.md) | [53](53-3d-transforms.md) | ... | [60](60-modern-features.md) | [Next →](52-2d-transforms.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
