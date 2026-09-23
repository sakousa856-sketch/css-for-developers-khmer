# មេរៀនទី ៤២៖ Grid: Container Properties (CSS Grid Container)

> **CSS Grid គឺជាប្រព័ន្ធរៀបចំប្លង់ ២ វិមាត្រ (2-Dimensional Layout System) ដែលគ្រប់គ្រងទាំងជួរដេក (Rows) និងជួរឈរ (Columns) ក្នុងពេលតែមួយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីភាពខុសគ្នារវាង **Flexbox (1D)** និង **CSS Grid (2D)**
* ចេះបង្កើតជួរឈរ និងជួរដេកតាមរយៈ `grid-template-columns` និង `grid-template-rows`
* ស្គាល់ខ្នាតប្រភាគបត់បែន **Fraction Unit (`fr`)** និងអនុគមន៍ `repeat()`
* ចេះរៀបចំប្លង់គេហទំព័រទាំងមូលដោយប្រើ `grid-template-areas`

---

## 🪟 CSS Grid Anatomy

![CSS Grid Anatomy](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-grid-anatomy.svg)

---

## 🎛️ បណ្តា Grid Container Properties

### ១. `display: grid`
បើកដំណើរការ Grid Layout លើ Parent Container។

---

### ២. `grid-template-columns` & `grid-template-rows`
កំណត់ចំនួន និងទំហំនៃជួរឈរ (Columns) និងជួរដេក (Rows)៖
* **`fr` (Fraction):** ខ្នាតប្រភាគនៃលំហដែលនៅសល់ (ឧ. `1fr 2fr 1fr` ➔ បែងចែកលំហជា ៤ ភាគស្មើគ្នា)
* **`repeat(count, size)`:** សរសេរកាត់កុំឱ្យ Repeat កូដដដែលៗ (ឧ. `repeat(3, 1fr)` ស្មើនឹង `1fr 1fr 1fr`)

```css
.dashboard-grid {
  display: grid;
  grid-template-columns: 240px 1fr;       /* Sidebar 240px + Main Area */
  grid-template-rows: 60px 1fr 50px;      /* Header + Content + Footer */
  gap: 20px;
}
```

---

### ៣. `gap` (គម្លាតក្រឡា)
កំណត់គម្លាតចន្លោះក្រឡា Grid Columns និង Rows៖
```css
.grid {
  display: grid;
  gap: 20px;
}
```

---

### ៤. `grid-template-areas` (ការគូសប្លង់គេហទំព័រដូចគំនូរ ⭐)
អនុញ្ញាតឱ្យអ្នកសរសេរឈ្មោះតំបន់ដូចគំនូរប្លង់ជាក់ស្តែង៖

```css
.site-layout {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header  header"
    "sidebar main"
    "footer  footer";
  min-height: 100vh;
  gap: 15px;
}

header  { grid-area: header; }
aside   { grid-area: sidebar; }
main    { grid-area: main; }
footer  { grid-area: footer; }
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Grid Container Demo</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: #f1f5f9;
    }

    .grid-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* 3 Columns ស្មើគ្នា */
      gap: 20px;
      max-width: 900px;
      margin: 0 auto;
    }

    .grid-item {
      background: white;
      padding: 30px;
      text-align: center;
      border-radius: 8px;
      border: 1px solid #cbd5e1;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
      font-weight: bold;
      color: #1e293b;
    }
  </style>
</head>
<body>

  <div class="grid-container">
    <div class="grid-item">ក្រឡា ១</div>
    <div class="grid-item">ក្រឡា ២</div>
    <div class="grid-item">ក្រឡា ៣</div>
    <div class="grid-item">ក្រឡា ៤</div>
    <div class="grid-item">ក្រឡា ៥</div>
    <div class="grid-item">ក្រឡា ៦</div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* 💡 **ពេលណាគួរប្រើ Flexbox vs CSS Grid:**
  * ប្រើ **Flexbox:** នៅពេលរៀបចំ Elements តាម **ជួរដេកតែមួយ ឬជួរឈរតែមួយ (1D)** ដូចជា Navbar, Button Groups, Card Tags។
  * ប្រើ **CSS Grid:** នៅពេលរៀបចំប្លង់ **ទាំងជួរដេក និងជួរឈរ (2D)** ដូចជា Page Dashboard Layout, Photo Gallery, Complex Multi-column layout។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Grid Container មួយមាន ៤ ជួរឈរស្មើគ្នាដោយប្រើ `grid-template-columns: repeat(4, 1fr); gap: 15px;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS Grid is a 2-dimensional grid-based layout system with rows and columns.
* `grid-template-columns` and `grid-template-rows` define the tracks of the grid.
* The `fr` unit represents a fraction of the available space in the grid container.
* `grid-template-areas` provides a visual layout map using named grid areas.
</details>
