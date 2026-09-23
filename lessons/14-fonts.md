# មេរៀនទី ១៤៖ ពុម្ពអក្សរ (CSS Fonts)

> **CSS Font Properties ប្រើសម្រាប់គ្រប់គ្រងប្រភេទពុម្ពអក្សរ ទំហំ កម្រាស់ និងទម្រង់អក្សរ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ស្គាល់ ៥ ក្រុមធំៗនៃ Generic Font Families (Serif, Sans-serif, Monospace, Cursive, Fantasy)
* ចេះកំណត់ **Font Fallback** តាមរយៈ `font-family`
* ចេះភ្ជាប់ **Google Fonts** (ដូចជា Inter, Roboto, Kantumruy Pro)
* ចេះប្រើ `font-size`, `font-weight`, `font-style`

---

## 🔤 ក្រុម Generic Font Families ទាំង ៥

1. **serif:** ពុម្ពអក្សរដែលមានជើងស្រួចៗ (ឧ. Times New Roman, Georgia)
2. **sans-serif:** ពុម្ពអក្សរគ្មានជើង រាបស្មើ ទំនើប ងាយស្រួលអានលើអេក្រង់ (ឧ. Arial, Inter, Helvetica, Kantumruy Pro)
3. **monospace:** តួអក្សរនីមួយៗមានទទឹងស្មើៗគ្នា ប្រើសម្រាប់បង្ហាញកូដ (ឧ. Courier New, Consolas, Fira Code)
4. **cursive:** ពុម្ពអក្សរមូលបែបដៃសរសេរ
5. **fantasy:** ពុម្ពអក្សរបែបសិល្បៈ ឬផ្ទាំងរូបភាព

---

## 🛡️ Font Fallback System (ប្រព័ន្ធការពារពេលខ្វះ Font)

យើងត្រូវរាយឈ្មោះ Fonts ច្រើនជាជួរ ពី Font ដែលយើងចង់បានបំផុត រហូតដល់ Generic Family នៅចុងក្រោយបង្អស់។ ប្រសិនបើកុំព្យូទ័រអ្នកប្រើមិនមាន Font ទី ១ ទេ Browser នឹងស្វែងរក Font ទី ២ បន្តបន្ទាប់៖

```css
body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}
```

---

## 🌐 ការភ្ជាប់ Google Fonts (Google Fonts Integration)

ចូលទៅកាន់ [fonts.google.com](https://fonts.google.com) រើសពុម្ពអក្សរដែលអ្នកពេញចិត្ត (ឧ. Kantumruy Pro សម្រាប់អក្សរខ្មែរ និង Inter សម្រាប់ឡាតាំង) រួចភ្ជាប់តាមរយៈ `<link>` tag ក្នុង `<head>`៖

```html
<!-- ភ្ជាប់ពី Google Fonts CDN -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Kantumruy+Pro:wght@400;600;700&display=swap" rel="stylesheet">
```

```css
body {
  font-family: 'Kantumruy Pro', sans-serif;
}
```

---

## 📏 Font Properties សំខាន់ៗ

* **`font-size`:** កំណត់ទំហំអក្សរ (`16px`, `1.125rem`, `120%`)
* **`font-weight`:** កម្រាស់អក្សរ (`normal` / `400`, `600` / Semi-bold, `bold` / `700`, `900` / Black)
* **`font-style`:** ទម្រង់អក្សរ (`normal`, `italic`, `oblique`)

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <title>CSS Fonts Demo</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Kantumruy+Pro:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Kantumruy Pro', sans-serif;
      background-color: #f8fafc;
      padding: 30px;
    }

    .title-bold {
      font-size: 28px;
      font-weight: 700;
      color: #0f172a;
    }

    .subtitle-medium {
      font-size: 18px;
      font-weight: 600;
      color: #2563eb;
    }

    .text-body {
      font-size: 16px;
      font-weight: 400;
      color: #334155;
      line-height: 1.7;
    }
  </style>
</head>
<body>

  <h1 class="title-bold">រៀនបង្កើតគេហទំព័រទំនើប</h1>
  <h3 class="subtitle-medium">ប្រើប្រាស់ Google Fonts ជាមួយ CSS</h3>
  <p class="text-body">
    ពុម្ពអក្សរស្អាតជួយលើកកម្ពស់សោភ័ណភាពនៃគេហទំព័រឱ្យកាន់តែទាក់ទាញ និងបង្កើនបទពិសោធន៍អ្នកប្រើប្រាស់ (User Experience)។
  </p>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ដាក់ឈ្មោះ Font ក្នុងសញ្ញា Quote `''` ប្រសិនបើមានដកឃ្លា:** ឧ. `'Kantumruy Pro'`, `'Times New Roman'`។
* ❌ **កុំ Load Font Weights ច្រើនពេក:** ជ្រើសរើសតែ Weights ដែលចាំបាច់ (ឧ. 400 និង 700) ដើម្បីកាត់បន្ថយទំហំ Download និងបង្កើនល្បឿន Page Load (Page Speed Optimization)។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. ភ្ជាប់ Google Font ឈ្មោះ `Inter` ចូលក្នុងទំព័រ HTML របស់អ្នក។
2. កំណត់ `body { font-family: 'Inter', sans-serif; }` និង `h1 { font-weight: 700; font-size: 32px; }`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `font-family` property defines the font for an element.
* Always specify a fallback system with a generic font family name at the end (e.g., `sans-serif`, `serif`).
* Web fonts can be included using Google Fonts or `@font-face`.
* `font-weight` sets the thickness of characters (e.g. `400` for normal, `700` for bold).
</details>
