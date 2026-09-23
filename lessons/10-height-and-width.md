# មេរៀនទី ១០៖ កម្ពស់ និងទទឹង (CSS Height, Width & Max-Width)

> **CSS `height` និង `width` ប្រើសម្រាប់កំណត់ទំហំកម្ពស់ និងទទឹងរបស់ Element។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្រើប្រាស់ `height` និង `width`
* យល់ពីភាពខុសគ្នារវាង `width: 100%` និង `max-width` សម្រាប់ Responsive Design
* ចេះប្រើ `min-width`, `max-height` និង `min-height`

---

## 📐 Properties សម្រាប់កំណត់ទំហំ

### ១. `height` និង `width` មូលដ្ឋាន
តម្លៃអាចជា `px`, `cm`, `%`, `vh`, `vw`, ឬ `auto` (លំនាំដើម):
```css
.box {
  width: 300px;
  height: 150px;
  background-color: #bfdbfe;
}
```

---

### ២. ភាពខុសគ្នារវាង `width` និង `max-width` (សំខាន់ខ្លាំងសម្រាប់ Responsive)

* ប្រសិនបើអ្នកកំណត់ **`width: 800px;`**៖ នៅលើអេក្រង់ទូរស័ព្ទតូចជាង 800px នោះ Element នឹងលៀនហៀរចេញក្រៅអេក្រង់ បង្កឱ្យមាន **Horizontal Scrollbar** មិនស្អាតឡើយ។
* ប្រសិនបើអ្នកកំណត់ **`max-width: 800px; width: 100%;`**៖ នៅលើអេក្រង់កុំព្យូទ័រធំ វារីកដល់ត្រឹម 800px ហើយនៅលើអេក្រង់ទូរស័ព្ទតូច វានឹងរួញតូចទៅតាមទំហំអេក្រង់ទូរស័ព្ទដោយស្វ័យប្រវត្តិ (Fluid & Responsive)។

```css
.responsive-container {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto; /* ចំកណ្តាល */
}
```

---

### ៣. `min-height` និង `max-height`
* `min-height: 100vh;`: កំណត់ឱ្យកម្ពស់យ៉ាងហោចណាស់ស្មើនឹងកម្ពស់ពេញមួយអេក្រង់ Viewport (និយមប្រើសម្រាប់ Main Page Container)
* `max-height: 400px; overflow-y: auto;`: កំណត់កម្ពស់អតិបរមា បើអត្ថបទច្រើនហួស នោះនឹងមាន Scrollbar បញ្ឈរ

```css
.app-layout {
  min-height: 100vh; /* ពេញអេក្រង់ជានិច្ច */
  display: flex;
  flex-direction: column;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Height & Width Demo</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background-color: #f8fafc;
      padding: 20px;
    }

    /* Fixed Width Box (Non-responsive) */
    .fixed-box {
      width: 600px;
      background-color: #fecaca;
      padding: 20px;
      margin-bottom: 20px;
      border: 1px solid #ef4444;
    }

    /* Max-Width Responsive Box */
    .responsive-box {
      max-width: 600px;
      width: 100%;
      background-color: #bbf7d0;
      padding: 20px;
      border: 1px solid #22c55e;
    }
  </style>
</head>
<body>

  <h2>សាកល្បងបង្រួញទំហំបង្អួច Browser ដើម្បីមើលភាពខុសគ្នា៖</h2>
  
  <div class="fixed-box">
    <strong>Fixed width: 600px</strong> (នឹងហៀរចេញក្រៅនៅលើទូរស័ព្ទ)
  </div>

  <div class="responsive-box">
    <strong>max-width: 600px + width: 100%</strong> (បត់បែនតាមអេក្រង់យ៉ាងល្អឥតខ្ចោះ)
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំដាក់ `height` ជាប់គាំង (Hardcoded height) លើប្រអប់ផ្ទុកអត្ថបទ:** ការដាក់ `height: 200px;` លើប្រអប់អត្ថបទ អាចធ្វើឱ្យអត្ថបទហៀរធ្លាយចេញក្រៅ (Overflow) ពេលមានអក្សរច្រើន។ គួរប្រើ `min-height` ឬទុកឱ្យកម្ពស់រីកតាមធម្មជាតិ (`height: auto`)។
* ❌ **Inline Elements មិនទទួល `width` និង `height` ឡើយ:** ដូចជា `<span>`, `<a>` មិនអាចដាក់ width/height បានទេ លុះត្រាតែប្តូរ `display: inline-block` ឬ `display: block`។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class `.main-card` មាន `max-width: 800px; width: 90%; margin: 30px auto;`។
2. សាកល្បងបើកលើ Mobile View ក្នុង Browser DevTools។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `height` and `width` properties are used to set the height and width of an element.
* The `max-width` property is used to set the maximum width of an element.
* Using `max-width` instead of `width` will improve the browser's handling of small windows and mobile viewports.
* `min-height: 100vh` ensures the container is at least as tall as the viewport.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>10</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១០</strong> នៃ <strong>៦០</strong></p>

| [← Prev](09-padding.md) | [01](01-introduction.md) | ... | [08](08-margins.md) | [09](09-padding.md) | **[ 10 ]** | [11](11-box-model.md) | [12](12-outline.md) | ... | [60](60-modern-features.md) | [Next →](11-box-model.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
