# មេរៀនទី ៣៨៖ មុខងារគណនាក្នុង CSS (CSS Math Functions)

> **CSS Math Functions ដូចជា `calc()`, `min()`, `max()` និង `clamp()` ជួយឱ្យយើងអាចគណនាតម្លៃ និងបង្កើត Fluid Responsive Typography ដោយមិនបាច់ប្រើ Media Queries ច្រើនឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្រើ `calc()` សម្រាប់លាយខ្នាតគណនា (ឧ. `100% - 40px`)
* ចេះប្រើ `min()` និង `max()` សម្រាប់កំណត់ដែនកំណត់
* ចេះប្រើ `clamp()` សម្រាប់បង្កើត **Fluid Responsive Typography** ដ៏អស្ចារ្យ

---

## 🧮 មុខងារគណនាទាំង ៤ ក្នុង Modern CSS

### ១. `calc()` (គណនាលាយខ្នាត)
អនុញ្ញាតឱ្យធ្វើប្រមាណវិធីបូក (`+`), ដក (`-`), គុណ (`*`), ចែក (`/`) រវាងខ្នាតខុសៗគ្នា (`%`, `px`, `rem`, `vw`):

```css
.sidebar-layout {
  /* ទទឹង 100% ដក Sidebar 280px ចេញ */
  width: calc(100% - 280px);
}
```

* ⚠️ **ច្បាប់ចាំបាច់:** ត្រូវតែ **ដកឃ្លា (Space)** នៅសងខាងសញ្ញា `+` និង `-` ជានិច្ច ឧ. `calc(100% - 20px)` (បើដាក់ `calc(100%-20px)` នឹង Error)។

---

### ២. `min()` និង `max()`
* **`min(val1, val2)`:** ជ្រើសរើសយកតម្លៃណាដែល **តូចជាងគេ**:
  ```css
  .container {
    width: min(90%, 1200px); /* រីកដល់ 1200px ពេលអេក្រង់ធំ ហើយយក 90% ពេលអេក្រង់តូច */
  }
  ```
* **`max(val1, val2)`:** ជ្រើសរើសយកតម្លៃណាដែល **ធំជាងគេ**:
  ```css
  .box {
    width: max(50vw, 300px); /* ទទឹងយ៉ាងហោចណាស់ 300px ជានិច្ច */
  }
  ```

---

### ៣. `clamp()` (Fluid Responsive Magic ⭐⭐⭐)
ទម្រង់៖ `clamp([អប្បបរមា MIN], [តម្លៃបត់បែន PREFERRED], [អតិបរមា MAX]);`

វាធានាថាតម្លៃនឹងប្រែប្រួលរលូនតាមទំហំអេក្រង់ ប៉ុន្តែ **មិនដែលតូចជាង MIN** ហើយ **មិនដែលធំជាង MAX** ឡើយ!

```css
/* Fluid Typography: អក្សររីកស្វ័យប្រវត្តិតាមអេក្រង់ពី 1.5rem (Mobile) ដល់ 3rem (Desktop) */
h1 {
  font-size: clamp(1.5rem, 4vw + 1rem, 3rem);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Math Functions Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #f1f5f9;
      padding: 20px;
    }

    /* Responsive Container using min() */
    .smart-container {
      width: min(92%, 1000px);
      margin: 0 auto;
      background: white;
      padding: clamp(1rem, 3vw, 2.5rem);
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.05);
    }

    /* Fluid Heading using clamp() */
    .fluid-title {
      font-size: clamp(1.75rem, 4vw + 0.5rem, 3.25rem);
      color: #0f172a;
      line-height: 1.2;
      margin-top: 0;
    }
  </style>
</head>
<body>

  <div class="smart-container">
    <h1 class="fluid-title">Fluid Responsive Typography</h1>
    <p>សាកល្បងបង្រួញ និងពង្រីកបង្អួច Browser ដើម្បីមើលទំហំចំណងជើងខាងលើរីកតូចធំដោយរលូនដោយប្រើ <code>clamp()</code> ដោយមិនបាច់សរសេរ Media Queries សូម្បីតែមួយបន្ទាត់!</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ចៀសវាង Fixed Breakpoints:** ការប្រើប្រាស់ `clamp()` សម្រាប់ Font Size និង Spacing ជួយឱ្យ UI របស់អ្នករលូននៅលើគ្រប់ Device ទាំងអស់ មិនថាតែ Tablet ឬទូរស័ព្ទអេក្រង់បត់ឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតអក្សរ `<h1>` មួយដោយប្រើ `font-size: clamp(1.5rem, 5vw, 3rem);`។
2. បើកមើលលើទូរស័ព្ទ និងកុំព្យូទ័រដើម្បីពិនិត្យមើលភាពបត់បែន។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `calc()`: Performs calculations to determine CSS property values. Spaces around operators (`+`, `-`) are mandatory.
* `min()`: Uses the smallest value from a list of comma-separated expressions.
* `max()`: Uses the largest value from a list of comma-separated expressions.
* `clamp(min, preferred, max)`: Clamps a value between an upper and lower bound, perfect for fluid typography.
</details>
