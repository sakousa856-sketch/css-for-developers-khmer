# មេរៀនទី ១២៖ បន្ទាត់ស៊ុមក្រៅ (CSS Outline)

> **CSS Outline គឺជាបន្ទាត់ដែលគូសព័ទ្ធជុំវិញខាងក្រៅបន្ទាត់ Border របស់ Element ដោយមិនយកទំហំក្នុង Box Model ឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីភាពខុសគ្នារវាង **Outline** និង **Border**
* ចេះប្រើ `outline-style`, `outline-width`, `outline-color`, `outline-offset`
* យល់ដឹងពីសារៈសំខាន់នៃ Focus Outline សម្រាប់ **Accessibility (A11y)**

---

## 🔍 ភាពខុសគ្នារវាង Outline និង Border

| លក្ខណៈ | Border | Outline |
| :--- | :--- | :--- |
| **ទីតាំង** | នៅខាងក្នុង Margin | នៅខាងក្រៅ Border |
| **ទំហំក្នុង Box Model** | យកទំហំ (ប៉ះពាល់ Width/Height) | **មិនយកទំហំឡើយ** (មិនរុញច្រាន Element ដទៃ) |
| **ជ្រុងនីមួយៗ** | កំណត់ `top/left/right/bottom` ដាច់ដោយឡែកបាន | ត្រូវតែព័ទ្ធជុំវិញគ្រប់ជ្រុងទាំងអស់ |
| **គម្លាត (Offset)** | គ្មាន `border-offset` ទេ | មាន `outline-offset` (អាចរំកិលចេញពី Border បាន) |

---

## 📐 Properties នៃ CSS Outline

### ១. Outline Shorthand
ទម្រង់៖ `outline: [width] [style] [color];`
```css
input:focus {
  outline: 2px solid #2563eb;
}
```

---

### ២. `outline-offset`
បង្កើតគម្លាតចន្លោះរវាងបន្ទាត់ Border និងបន្ទាត់ Outline៖
```css
.card {
  border: 2px solid #0f172a;
  outline: 2px dashed #dc2626;
  outline-offset: 6px; /* គម្លាតចេញក្រៅ Border 6px */
}
```

---

## ♿ សារៈសំខាន់នៃ Outline សម្រាប់ Accessibility (A11y)

នៅពេលអ្នកប្រើប្រាស់ចុចគ្រាប់ចុច **Tab** លើ Keyboard ដើម្បីរំកិលតាម Links ឬ Inputs Browser នឹងបង្ហាញបន្ទាត់ Focus Outline។ នេះជួយឱ្យជនពិការភ្នែក ឬអ្នកប្រើប្រាស់ Keyboard អាចដឹងថា Cursor កំពុងស្ថិតនៅកន្លែងណា។

```css
/* ✅ របៀប Styling Focus State ឱ្យស្អាត និងរក្សា A11y */
button:focus-visible {
  outline: 3px solid #3b82f6;
  outline-offset: 3px;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Outline Demo</title>
  <style>
    .input-field {
      padding: 10px 14px;
      font-size: 16px;
      border: 1px solid #cbd5e1;
      border-radius: 6px;
      transition: outline 0.2s ease;
    }

    .input-field:focus {
      outline: 3px solid #3b82f6;
      outline-offset: 2px;
      border-color: #3b82f6;
    }

    .badge-box {
      width: 200px;
      margin: 30px;
      padding: 15px;
      background-color: #f8fafc;
      border: 2px solid #334155;
      outline: 2px dashed #ea580c;
      outline-offset: 5px;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="badge-box">ប្រអប់មាន Outline Offset</div>

  <p>សាកល្បងចុច Focus លើ Input ខាងក្រោម៖</p>
  <input type="text" class="input-field" placeholder="បញ្ចូលឈ្មោះរបស់អ្នក...">

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំសរសេរ `outline: none;` ឬ `outline: 0;` ដោយគ្មាន Replacement:** ការលុប Outline ចោលទាំងស្រុងនឹងបំផ្លាញ Accessibility (A11y) ធ្វើឱ្យ Keyboard Users មិនអាចប្រើប្រាស់ Website បាន។
* ✅ **ប្រើ `:focus-visible`:** ដើម្បីបង្ហាញ Outline តែពេលអ្នកប្រើប្រាស់ចុច Keyboard Navigation ប៉ុណ្ណោះ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប៊ូតុង `<button>` មួយ។
2. ពេល `:focus` ឱ្យបង្ហាញ `outline: 2px solid #10b981; outline-offset: 4px;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* An outline is a line drawn around elements, outside the borders, to make the element "stand out".
* Unlike borders, outlines do not take up space in the document flow.
* `outline-offset` adds space between an outline and the edge or border of an element.
* Never remove outlines (`outline: none`) without providing an accessible alternative focus indicator.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>12</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១២</strong> នៃ <strong>៦០</strong></p>

| [← Prev](11-box-model.md) | [01](01-introduction.md) | ... | [10](10-height-and-width.md) | [11](11-box-model.md) | **[ 12 ]** | [13](13-text.md) | [14](14-fonts.md) | ... | [60](60-modern-features.md) | [Next →](13-text.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
