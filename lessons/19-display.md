# មេរៀនទី ១៩៖ លក្ខណៈបង្ហាញ Display (CSS Display Property)

> **`display` គឺជា Property ដ៏សំខាន់បំផុតមួយក្នុង CSS សម្រាប់គ្រប់គ្រងឥរិយាបថនៃការបង្ហាញប្លង់នៃ Element។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីភាពខុសគ្នារវាង `block`, `inline`, `inline-block` និង `none`
* យល់ពីភាពខុសគ្នារវាង `display: none` និង `visibility: hidden`
* ចេះប្តូរឥរិយាបថបង្ហាញរបស់ Element តាមតម្រូវការ

---

## 🧱 តម្លៃនៃ `display` ទាំង ៤ សំខាន់ៗ

![CSS Display Modes Comparison](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-display-comparison.svg)

### ១. `display: block`
* ចាប់ផ្តើមបន្ទាត់ថ្មីជានិច្ច (New line)
* ពង្រីកទទឹងពេញ ១០០% នៃទំហំ Parent Container
* **អាចទទួល** `width`, `height`, `margin`, `padding` បានពេញលេញគ្រប់ជ្រុង
* *ឧទាហរណ៍ Default elements:* `<div>`, `<p>`, `<h1>` ដល់ `<h6>`, `<section>`, `<header>`

---

### ២. `display: inline`
* ស្ថិតក្នុងបន្ទាត់តែមួយជាមួយអត្ថបទ (មិនចុះបន្ទាត់ថ្មីឡើយ)
* យកទទឹងល្មមតែទំហំមាតិកាខាងក្នុងរបស់វាប៉ុណ្ណោះ
* **មិនអាចកំណត់ `width` និង `height` បានឡើយ**
* `margin-top`, `margin-bottom` មិនដំណើរការឡើយ (ដំណើរការតែ Left/Right)
* *ឧទាហរណ៍ Default elements:* `<span>`, `<a>`, `<strong>`, `<em>`

---

### ៣. `display: inline-block` (កូនកាត់)
* ស្ថិតក្នុងជួរដេកតែមួយដូច `inline` (មិនចុះបន្ទាត់ថ្មី)
* ប៉ុន្តែ **អាចកំណត់ `width`, `height`, `margin`, `padding`** បានគ្រប់ជ្រុងដូច `block`
* *ស័ក្តិសមបំផុតសម្រាប់៖* ប៊ូតុង Navigation Tabs ឬ Card Boxes តម្រៀបផ្ដេក

```css
.nav-item {
  display: inline-block;
  width: 120px;
  height: 40px;
  text-align: center;
}
```

---

### ៤. `display: none` ទល់នឹង `visibility: hidden`

| Property | អត្ថន័យ | លំហក្នុងទំព័រ (Layout Space) |
| :--- | :--- | :--- |
| **`display: none;`** | លាក់ Element បាត់ទាំងស្រុង | **លុបចោលលំហ** ហាក់ដូចជាគ្មាន Element នោះក្នុងទំព័រអញ្ចឹង |
| **`visibility: hidden;`** | ធ្វើឱ្យមើលមិនឃើញ (ថ្លា) | **នៅរក្សាទំហំលំហដដែល** (នៅសល់ប្រហោងទទេ) |

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Display Demo</title>
  <style>
    .inline-item {
      display: inline;
      background-color: #fef08a;
      padding: 5px;
    }

    .block-item {
      display: block;
      background-color: #bfdbfe;
      margin: 10px 0;
      padding: 10px;
    }

    .inline-block-item {
      display: inline-block;
      width: 140px;
      height: 80px;
      background-color: #bbf7d0;
      margin: 5px;
      padding: 10px;
      text-align: center;
      border-radius: 6px;
    }
  </style>
</head>
<body>

  <h3>1. Inline Elements (រត់តគ្នាក្នុងបន្ទាត់តែមួយ)</h3>
  <span class="inline-item">Item 1</span>
  <span class="inline-item">Item 2</span>
  <span class="inline-item">Item 3</span>

  <h3>2. Block Elements (ចុះបន្ទាត់ និងពេញទទឹង)</h3>
  <div class="block-item">Block Item 1</div>
  <div class="block-item">Block Item 2</div>

  <h3>3. Inline-Block Elements (រត់តគ្នា តែអាចដាក់ Width/Height បាន)</h3>
  <div class="inline-block-item">Box 1 (140x80)</div>
  <div class="inline-block-item">Box 2 (140x80)</div>
  <div class="inline-block-item">Box 3 (140x80)</div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ព្យាយាមដាក់ `width` លើ `<span>` ដោយមិនប្តូរ `display`:** វានឹងគ្មានប្រសិទ្ធភាពឡើយ។ ត្រូវដាក់ `display: inline-block;` ឬ `display: block;` ជាមុនសិន។
* 💡 **បិទបើកមាតិកា (Toggle Dropdowns/Modals):** JavaScript តែងប្រើ `display: none` ដើម្បីលាក់ Menu និង `display: block` / `display: flex` ដើម្បីបង្ហាញមកវិញ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតតំណភ្ជាប់ `<a>` ចំនួន ៣ ដោយដាក់ `display: inline-block; width: 100px; padding: 10px; background-color: #0284c7; color: white; text-align: center;`។
2. សង្កេតមើលរបៀបដែលពួកវាតម្រៀបគ្នាជាជួរដេក។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `display` property specifies how an element is shown.
* `block`: Starts on a new line and takes up the full width available.
* `inline`: Does not start on a new line and only takes up as much width as necessary; does not accept width and height.
* `inline-block`: Formatted like an inline element, but accepts width and height properties.
* `display: none`: Hides the element and removes its space from the layout.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>19</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១៩</strong> នៃ <strong>៦០</strong></p>

| [← Prev](18-tables.md) | [01](01-introduction.md) | ... | [17](17-lists.md) | [18](18-tables.md) | **[ 19 ]** | [20](20-max-width.md) | [21](21-position.md) | ... | [60](60-modern-features.md) | [Next →](20-max-width.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
