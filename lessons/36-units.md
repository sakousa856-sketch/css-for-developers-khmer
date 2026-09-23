# មេរៀនទី ៣៦៖ ខ្នាតរង្វាស់ក្នុង CSS (CSS Units)

> **CSS Units ប្រើសម្រាប់កំណត់ទំហំប្រវែង កម្ពស់ ទទឹង គម្លាត និង Font Size ដោយបែងចែកជា Absolute Units និង Relative Units។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីភាពខុសគ្នារវាង **Absolute Units** និង **Relative Units**
* យល់ដឹងស៊ីជម្រៅពី **`rem` ទល់នឹង `em`**
* ចេះប្រើ Viewport Units (`vw`, `vh`, `vmin`, `vmax`) សម្រាប់ប្លង់ពេញអេក្រង់

---

## 📏 ១. Absolute Units (ខ្នាតប្រវែងជាប់ថេរ)

![CSS Units Master Guide](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-units-guide.svg)

ខ្នាតទាំងនេះមានទំហំថេរ មិនប្រែប្រួលតាមទំហំអេក្រង់ ឬ Parent ឡើយ៖
* **`px` (Pixels):** 1px = 1 ចុច Pixel លើអេក្រង់កុំព្យូទ័រ (ខ្នាតគ្រឹះបំផុត)
* `pt` (Points): 1pt = 1/72 inch (និយមប្រើសម្រាប់ Print Stylesheet)
* `cm`, `mm`, `in`: សង់ទីម៉ែត្រ មីលីម៉ែត្រ អ៊ីញ

---

## 🔄 ២. Relative Units (ខ្នាតរង្វាស់បត់បែនតាមបរិបទ - ពេញនិយមបំផុត)

ខ្នាតទាំងនេះគណនាទំហំធៀបទៅនឹងទំហំអក្សរ ឬទំហំអេក្រង់របស់ Browser៖

| ខ្នាត | ធៀបទៅនឹង (Relative To) | ការប្រើប្រាស់សមស្រប |
| :---: | :--- | :--- |
| **`rem`** | ធៀបនឹង Font-size នៃ **Root (`<html>`)** (Default 1rem = 16px) | **Typography, Padding, Spacing, Margins** ⭐ |
| **`em`** | ធៀបនឹង Font-size នៃ **Parent Element ផ្ទាល់** | Component-scoped scaling (ឧ. Icon ជាប់អក្សរ) |
| **`%`** | ធៀបនឹងទទឹង ឬកម្ពស់របស់ **Parent Element** | Responsive Grid Widths (ឧ. `width: 50%`) |
| **`vw`** | 1vw = 1% នៃទទឹង **Viewport Width** របស់អេក្រង់ | Full-width banners |
| **`vh`** | 1vh = 1% នៃកម្ពស់ **Viewport Height** របស់អេក្រង់ | Full-screen hero section (`min-height: 100vh`) |
| **`ch`** | ទទឹងនៃតួអក្សរលេខ `"0"` នៃ Font បច្ចុប្បន្ន | កំណត់ប្រវែងអានអត្ថបទសមស្រប (`max-width: 65ch`) |

---

## 🥊 ការប្រៀបធៀបស៊ីជម្រៅ៖ `rem` ទល់នឹង `em`

* **`rem` (Root EM):** ព្យួរទៅលើតែ `<html>` មួយគត់។ បើ `html { font-size: 16px; }` នោះ `1.5rem = 24px` ជានិច្ចនៅគ្រប់ទីកន្លែងក្នុងគេហទំព័រ (Predictable & Safe)។
* **`em` (Element EM):** គុណបន្តគ្នាតាម Parent (Compounding Effect)៖
  * បើ Parent មាន `font-size: 20px;` នោះកូន `1.5em = 30px`។
  * បើមាន Nested List ជ្រៅៗ `em` អាចធ្វើឱ្យអក្សរកាន់តែរីកធំឡើងៗ ឬតូចទៅៗពិបាកគ្រប់គ្រង។

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Units Demo</title>
  <style>
    /* Root 16px */
    html {
      font-size: 16px;
    }

    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #f8fafc;
    }

    /* Full screen hero section */
    .hero-fullscreen {
      min-height: 80vh; /* 80% នៃកម្ពស់អេក្រង់ */
      background: linear-gradient(135deg, #1e293b, #0f172a);
      color: white;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 2rem; /* 32px */
    }

    .hero-title {
      font-size: 2.5rem; /* 40px */
      margin-bottom: 1rem; /* 16px */
    }

    .readable-text {
      max-width: 65ch; /* ប្រវែងអានល្អបំផុតមិនលើសពី 65 តួអក្សរ */
      line-height: 1.6;
      font-size: 1.125rem; /* 18px */
      color: #94a3b8;
      text-align: center;
    }
  </style>
</head>
<body>

  <section class="hero-fullscreen">
    <h1 class="hero-title">រៀនប្រើប្រាស់ CSS Units</h1>
    <p class="readable-text">
      ការប្រើប្រាស់ខ្នាត <code>rem</code> និង <code>vh/vw</code> ជួយឱ្យគេហទំព័ររបស់អ្នកមានសមាមាត្រល្អឥតខ្ចោះនៅលើគ្រប់ទំហំអេក្រង់ និងគាំទ្រ Accessibility ពេល User ពង្រីកអក្សរក្នុង Browser Settings។
    </p>
  </section>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Best Practice សម្រាប់ Typography & Spacing:** ប្រើ **`rem`** សម្រាប់ Font Size, Margin, និង Padding ទាំងអស់ ដើម្បីឱ្យគេហទំព័រ Scale តាមការកំណត់ Browser Font Size របស់អ្នកប្រើប្រាស់ (Accessibility A11y)។
* ✅ **Best Practice សម្រាប់ Layout:** ប្រើ **`%`** ឬ **`fr` (Grid)** សម្រាប់ទទឹង Grid Columns និងប្រើ **`vh`** សម្រាប់កម្ពស់ Banner ពេញអេក្រង់។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. កំណត់ `h1 { font-size: 2rem; }` និង `p { font-size: 1rem; margin-bottom: 1.5rem; }`។
2. បង្កើត Hero Banner ដែលមាន `height: 100vh;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS has absolute units (`px`, `pt`, `cm`) and relative units (`%`, `em`, `rem`, `vw`, `vh`, `ch`).
* `rem` is relative to the root font-size (`<html>`), making it consistent and predictable.
* `em` is relative to the font-size of the current element's parent.
* `vw` / `vh` are relative to 1% of the viewport width / height.
* `max-width: 65ch` creates an optimal reading line length for text blocks.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ៣៥៖ ការរាប់លេខស្វ័យប្រវត្តិ (CSS Counters)](35-counters.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ៣៧៖ ទម្ងន់ និងលំដាប់អានុភាព (CSS Specificity & The Cascade) ➡️](37-specificity-and-cascade.md) |
