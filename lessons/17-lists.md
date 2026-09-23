# មេរៀនទី ១៧៖ ការកំណត់ Style លើបញ្ជី (CSS Lists)

> **CSS List Properties ប្រើសម្រាប់កំណត់ទម្រង់គ្រាប់ចំណាំ (Bullets) លេខរៀង និងគម្លាតនៃបញ្ជី `<ul>` និង `<ol>`។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្តូរគ្រាប់ Bullets និងលេខរៀង (`list-style-type`)
* ចេះលុប Bullets ចោល (`list-style-type: none`) សម្រាប់បង្កើត Navbar
* ចេះគ្រប់គ្រងទីតាំងគ្រាប់ចំណាំ (`list-style-position: inside | outside`)
* ចេះបង្កើត Custom Emoji/Icon Bullets ដោយប្រើ CSS Pseudo-elements

---

## 📋 List Properties សំខាន់ៗ

### ១. `list-style-type`
* សម្រាប់ **Unordered Lists (`<ul>`):** `disc` (Default), `circle`, `square`, `none`
* សម្រាប់ **Ordered Lists (`<ol>`):** `decimal` (`1, 2, 3`), `lower-alpha` (`a, b, c`), `upper-roman` (`I, II, III`)

```css
ul.custom-square { list-style-type: square; }
ol.roman         { list-style-type: upper-roman; }
```

---

### ២. លុប Bullet និង Default Margin/Padding (List Reset)
ដើម្បីយក `<ul>` ទៅធ្វើជា Navigation Bar ឬ List ផ្ទាល់ខ្លួន យើងត្រូវ Reset វាជាមុនសិន៖

```css
ul.clean-list {
  list-style-type: none; /* លុបគ្រាប់ Bullet */
  margin: 0;
  padding: 0;
}
```

---

### ៣. `list-style-position`
* `outside` (Default): គ្រាប់ Bullet ស្ថិតនៅក្រៅគែមបន្ទាត់អត្ថបទ
* `inside`: គ្រាប់ Bullet ស្ថិតនៅខាងក្នុងលំហអត្ថបទតែម្តង

```css
ul {
  list-style-position: inside;
}
```

---

### ៤. Custom Icon/Emoji Bullets (ទំនើប)
យើងអាចប្រើ `::before` pseudo-element ដើម្បីដាក់ Emoji ឬ SVG Icon ជំនួសឱ្យ Bullet ធម្មតា៖

```css
ul.feature-list {
  list-style: none;
  padding-left: 0;
}

ul.feature-list li {
  position: relative;
  padding-left: 28px;
  margin-bottom: 10px;
}

ul.feature-list li::before {
  content: "✅";
  position: absolute;
  left: 0;
  top: 0;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Lists Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .checklist {
      list-style: none;
      padding: 0;
      max-width: 400px;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }

    .checklist li {
      padding: 10px 0;
      border-bottom: 1px solid #f1f5f9;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .checklist li:last-child {
      border-bottom: none;
    }

    .badge {
      background-color: #dcfce7;
      color: #166534;
      font-size: 12px;
      padding: 2px 8px;
      border-radius: 12px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>បញ្ជីមុខងារពិសេស (Features Checklist)</h2>
  <ul class="checklist">
    <li>🚀 ដំណើរការលឿនរហ័ស</li>
    <li>🔒 សុវត្ថិភាពខ្ពស់ <span class="badge">Pro</span></li>
    <li>📱 គាំទ្រ Responsive 100%</li>
  </ul>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ភ្លេចលុប `padding-left` របស់ Browser:** តាមលំនាំដើម Browser តែងបន្ថែម `padding-left: 40px;` លើ `<ul>` ទាំងអស់។ ដូច្នេះពេលដាក់ `list-style: none;` ត្រូវដាក់ `padding: 0;` ផងទើបអត្ថបទមិនរំកិលទៅស្តាំ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត `<ul>` មួយ រួចប្រើ `list-style: none; padding: 0;`។
2. ប្រើ `::before` ដើម្បីដាក់រូបសញ្ញាព្រួញ `➔` នៅពីមុខ List Item នីមួយៗ។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `list-style-type` property specifies the type of list item marker (`disc`, `circle`, `square`, `none`, `decimal`, etc.).
* Removing markers and padding: `list-style-type: none; margin: 0; padding: 0;` is common for navigation menus.
* `list-style-position` specifies whether the list-item markers should appear inside or outside the content flow.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>17</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១៧</strong> នៃ <strong>៦០</strong></p>

| [← Prev](16-links.md) | [01](01-introduction.md) | ... | [15](15-icons.md) | [16](16-links.md) | **[ 17 ]** | [18](18-tables.md) | [19](19-display.md) | ... | [60](60-modern-features.md) | [Next →](18-tables.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
