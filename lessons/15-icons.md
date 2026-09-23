# មេរៀនទី ១៥៖ ការប្រើប្រាស់ Icons (CSS Icons)

> **Icon ជួយបង្កើនភាពទាក់ទាញ និងភាពងាយយល់នៃ Navigation និង Buttons លើគេហទំព័រ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះភ្ជាប់ និងប្រើប្រាស់ Icon Libraries ពេញនិយម (Google Icons, Font Awesome)
* ចេះកំណត់ទំហំ ពណ៌ និងផលប៉ះពាល់លើ Icons តាមរយៈ CSS
* យល់ពីការប្រើប្រាស់ SVG Icons ផ្ទាល់ក្នុង CSS

---

## 🌟 Icon Libraries ពេញនិយម

### ១. Google Material Symbols & Icons
ងាយស្រួលប្រើប្រាស់បំផុត គ្រាន់តែភ្ជាប់ CDN Link៖

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />
```

```html
<span class="material-symbols-outlined icon-blue">home</span>
<span class="material-symbols-outlined icon-green">shopping_cart</span>
<span class="material-symbols-outlined icon-red">favorite</span>
```

---

### ២. Font Awesome Icons
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
```

```html
<i class="fa-solid fa-user"></i>
<i class="fa-brands fa-github"></i>
<i class="fa-solid fa-heart"></i>
```

---

## 🎨 ការកំណត់ Style លើ Icons តាមរយៈ CSS

ដោយសារ Icons ទាំងនេះត្រូវបានបង្កើតឡើងជា **Icon Fonts** ដូច្នេះយើងអាចគ្រប់គ្រងវាដូចជាអក្សរធម្មតាបានដោយប្រើ `color`, `font-size`, `transition`, `hover`:

```css
.material-symbols-outlined {
  font-size: 24px;
  vertical-align: middle;
  transition: transform 0.2s ease, color 0.2s ease;
}

.icon-button:hover .material-symbols-outlined {
  color: #2563eb;
  transform: scale(1.15); /* ពង្រីកធំបន្តិចពេល Hover */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Icons Demo</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .btn-icon {
      display: inline-flex;
      align-items: center;
      gap: 8px; /* គម្លាតរវាង Icon និង Text */
      background-color: #2563eb;
      color: white;
      padding: 10px 18px;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.2s ease;
    }

    .btn-icon:hover {
      background-color: #1d4ed8;
    }

    .icon-large {
      font-size: 36px;
      color: #ea580c;
    }
  </style>
</head>
<body>

  <h2>ប៊ូតុងមាន Icon</h2>
  <button class="btn-icon">
    <span class="material-symbols-outlined">download</span>
    ទាញយកឯកសារ
  </button>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ប្រើ `align-items: center` ឬ `vertical-align: middle`:** Icon និង Text ជារឿយៗមិនរត់ស្មើបន្ទាត់គ្នាឡើយ។ ប្រើ `display: flex; align-items: center; gap: 8px;` លើប៊ូតុងដើម្បីឱ្យ Icon និង Text រត់ស្មើគ្នាស្អាតជានិច្ច។
* ✅ **Accessibility (A11y):** ប្រសិនបើប៊ូតុងមានតែ Icon សុទ្ធ (គ្មាន Text) ត្រូវបន្ថែម `aria-label="Search"` ដើម្បីឱ្យ Screen Readers អាចអានបាន។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. ភ្ជាប់ Google Material Symbols ចូលក្នុងទំព័រ HTML។
2. បង្កើតប៊ូតុងរាងមូល (Circle Icon Button) មួយដែលមាន Icon រូបកន្ត្រកទិញទំនិញ (`shopping_cart`)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Icons can easily be added to HTML pages with icon libraries (Font Awesome, Google Material Symbols).
* Icon fonts can be styled with CSS `color`, `font-size`, `transform`, and `text-shadow`.
* Use `display: flex; align-items: center; gap: 8px;` to properly align icons with accompanying text.
</details>
