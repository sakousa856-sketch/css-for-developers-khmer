# មេរៀនទី ០២៖ ទម្រង់កូដ និង Selectors មូលដ្ឋាន (CSS Syntax & Selectors)

> **CSS Rule-Set ផ្សំឡើងពី Selector និង Declaration Block។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីរចនាសម្ព័ន្ធនៃ **CSS Rule-Set**
* ស្គាល់ភាពខុសគ្នារវាង **Property** និង **Value**
* ចេះប្រើប្រាស់ Simple Selectors មូលដ្ឋាន៖ **Element, ID, Class, Universal, Grouping**

---

## 📐 រចនាសម្ព័ន្ធនៃ CSS Syntax (CSS Syntax Breakdown)

CSS Rule-Set មានទម្រង់ស្តង់ដារដូចខាងក្រោម៖

```css
selector {
  property: value;
  property: value;
}
```

![CSS Syntax Anatomy](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-syntax-anatomy.svg)

* **Selector:** ចង្អុលទៅកាន់ HTML element ណាដែលអ្នកចង់ដាក់ Style (ឧ. `h1`, `.card`, `#logo`)
* **Declaration Block:** ស្ថិតនៅក្នុងសញ្ញាវង់ក្រចកទំពក់ `{ ... }`
* **Declaration:** បន្ទាត់កំណត់ Style នីមួយៗ ដែលផ្សំឡើងពី **Property** និង **Value**
* **Property:** លក្ខណៈដែលត្រូវកែប្រែ (ឧ. `color`, `font-size`, `background-color`)
* **Value:** តម្លៃដែលត្រូវប្រគល់ឱ្យ Property (ឧ. `blue`, `18px`, `#ffffff`)
* **Semicolon (`;`):** ត្រូវតែដាក់នៅចុងបញ្ចប់នៃ Declaration នីមួយៗដើម្បីកុំឱ្យ Error

---

## 🔍 ប្រភេទ Simple Selectors ក្នុង CSS

### ១. Element Selector (Tag Name)
រើសយក HTML elements ទាំងអស់តាមឈ្មោះ Tag៖
```css
p {
  color: #4b5563;
  line-height: 1.5;
}
```
*(អនុវត្តលើរាល់ `<p>` ទាំងអស់ក្នុងទំព័រ)*

---

### ២. ID Selector (`#id`)
រើសយក element តែមួយគត់ដែលមាន attribute `id` ត្រូវគ្នា។ ក្នុងមួយទំព័រ `id` ត្រូវតែជា Unique៖
```css
#main-header {
  background-color: #1e293b;
  color: #ffffff;
}
```
```html
<header id="main-header">Welcome to my site</header>
```

---

### ៣. Class Selector (`.class`)
រើសយក elements ណាដែលមាន attribute `class` ត្រូវគ្នា។ Class អាចប្រើដដែលៗលើ elements ច្រើន៖
```css
.highlight {
  background-color: #fef08a;
  font-weight: bold;
}
```
```html
<p class="highlight">អត្ថបទនេះត្រូវបាន highlight ពណ៌លឿង។</p>
<span class="highlight">ពាក្យនេះក៏ highlight ដែរ។</span>
```

---

### ៤. Universal Selector (`*`)
រើសយក elements ទាំងអស់ដែលមាននៅក្នុងទំព័រ (ប្រើសម្រាប់ Reset margin/padding):
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

---

### ៥. Grouping Selector (`,`)
ប្រសិនបើ elements ច្រើនមាន Style ដូចគ្នា យើងអាចដាក់ Selector ផ្គុំគ្នាដោយប្រើសញ្ញាក្បៀស (`,`) ដើម្បីកាត់បន្ថយកូដដដែលៗ៖
```css
h1, h2, h3 {
  font-family: 'Helvetica Neue', sans-serif;
  color: #0f172a;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Selectors Demo</title>
  <style>
    /* Element Selector */
    h1 {
      color: #2563eb;
    }

    /* Class Selector */
    .intro-text {
      font-size: 18px;
      color: #475569;
    }

    /* ID Selector */
    #cta-button {
      background-color: #16a34a;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>ស្វែងយល់ពី CSS Selectors</h1>
  <p class="intro-text">Class selector អាចប្រើឡើងវិញលើកថាខណ្ឌច្រើនបាន។</p>
  <button id="cta-button">ចុចទីនេះ</button>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំចាប់ផ្តើមឈ្មោះ Class ឬ ID ដោយលេខ:** ឧទាហរណ៍ `.1box` គឺខុស Syntax ក្នុង CSS (ត្រូវដាក់ `.box-1` វិញ)។
* ❌ **កុំប្រើ ID Selector សម្រាប់ Styling ច្រើនពេក:** ID មាន Specificity ខ្ពស់ ដែលពិបាកក្នុងការ Override នៅពេលក្រោយ។ គួរប្រើ **Class Selector** សម្រាប់ Styling ទូទៅ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class មួយឈ្មោះ `.alert-box` កំណត់ `background-color: #fee2e2;` និង `color: #991b1b;`។
2. បង្កើត ID មួយឈ្មោះ `#navbar` កំណត់ `background-color: #0f172a;` និង `color: white;`។
3. ប្រើ Grouping Selector ដើម្បីកំណត់ឱ្យ `h1` និង `p` ប្រើ `font-family: Arial, sans-serif;` រួមគ្នា។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* A CSS rule consists of a selector and a declaration block.
* The selector points to the HTML element you want to style.
* The declaration block contains one or more declarations separated by semicolons.
* Element Selector selects elements based on the tag name (`p`, `h1`).
* ID Selector uses `#` and targets a unique element on the page (`#header`).
* Class Selector uses `.` and targets elements with a specific class attribute (`.center`).
* Universal Selector `*` selects all HTML elements on the page.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>2</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>០២</strong> នៃ <strong>៦០</strong></p>

| [← Prev](01-introduction.md) | [01](01-introduction.md) | **[ 02 ]** | [03](03-how-to-add-css.md) | [04](04-comments.md) | [05](05-colors.md) | ... | [60](60-modern-features.md) | [Next →](03-how-to-add-css.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
