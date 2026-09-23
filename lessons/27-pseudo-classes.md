# មេរៀនទី ២៧៖ ស្លាកក្លែងក្លាយ (CSS Pseudo-classes)

> **Pseudo-class ប្រើសម្រាប់កំណត់ Style លើ Element ក្នុងស្ថានភាពពិសេស (Special State ដូចជា ពេល Hover, ពេល Focus, ឬតាមលំដាប់កូន)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីរបៀបប្រើ User Action Pseudo-classes (`:hover`, `:focus`, `:active`)
* ចេះជ្រើសរើស Element តាមលំដាប់ Structural (`:first-child`, `:last-child`, `:nth-child()`)
* ចេះប្រើ Functional Pseudo-classes ទំនើបៗ (`:not()`, `:checked`, `:disabled`)

---

## ⚡ ស្លាកក្លែងក្លាយសកម្មភាពអ្នកប្រើប្រាស់ (User Action)

```css
/* ពេលយក Mouse ដាក់ពីលើ */
.btn:hover {
  background-color: #1d4ed8;
}

/* ពេលចុច Focus លើ Input */
input:focus {
  border-color: #3b82f6;
  outline: 2px solid #93c5fd;
}

/* ពេលកំពុងចុចសង្កត់ Mouse */
.btn:active {
  transform: scale(0.98);
}
```

---

## 🔢 ស្លាកក្លែងក្លាយតាមលំដាប់រចនាសម្ព័ន្ធ (Structural)

### ១. `:first-child` & `:last-child`
* `li:first-child`: កូនដំបូងគេបង្អស់
* `li:last-child`: កូនចុងក្រោយគេបង្អស់

```css
ul li:last-child {
  border-bottom: none; /* លុបបន្ទាត់បាតក្រោមនៃ List Item ចុងក្រោយ */
}
```

---

### ២. `:nth-child(n)` (មានឥទ្ធិពលខ្លាំងបំផុត)
* `:nth-child(2)`: កូនទី ២ ជាក់លាក់
* `:nth-child(even)`: គ្រប់កូនជួរគូ (2, 4, 6, 8...) ➔ Zebra Stripes
* `:nth-child(odd)`: គ្រប់កូនជួរសេស (1, 3, 5, 7...)
* `:nth-child(3n)`: គ្រប់កូនពហុគុណនៃ 3 (3, 6, 9, 12...)

```css
/* រាល់ក្រឡាតារាងជួរគូ */
tr:nth-child(even) {
  background-color: #f8fafc;
}
```

---

## 🚫 ស្លាកក្លែងក្លាយបដិសេធ `:not()` និង Form States

```css
/* អនុវត្តលើប៊ូតុងទាំងអស់ លើកលែងតែប៊ូតុងដែលមាន class .disabled */
button:not(.disabled) {
  cursor: pointer;
}

/* នៅពេល Checkbox ត្រូវបានគូសធីក (Checked) */
input[type="checkbox"]:checked + label {
  font-weight: bold;
  color: #16a34a;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Pseudo-classes Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .pricing-grid {
      display: flex;
      gap: 20px;
      max-width: 600px;
    }

    .card {
      flex: 1;
      padding: 20px;
      background: white;
      border: 2px solid #e2e8f0;
      border-radius: 8px;
      transition: all 0.2s ease;
    }

    /* Highlight the 2nd card (Popular) */
    .card:nth-child(2) {
      border-color: #3b82f6;
      background-color: #eff6ff;
      transform: scale(1.05);
    }

    .card:hover {
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    }
  </style>
</head>
<body>

  <h2>កញ្ចប់តម្លៃ (Pricing Cards)</h2>
  <div class="pricing-grid">
    <div class="card">Basic Plan</div>
    <div class="card">Pro Plan (nth-child(2))</div>
    <div class="card">Enterprise Plan</div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* 💡 **Syntax Note:** Pseudo-class ប្រើសញ្ញា **Colon មួយ (`:`)** ដូចជា `:hover`, `:focus` ចំណែក Pseudo-element ប្រើសញ្ញា **Colon ពីរ (`::`)** ដូចជា `::before`, `::after`។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត `<ul>` មាន `<li>` ចំនួន ៥។
2. ប្រើ `:nth-child(odd)` ដើម្បីប្តូរពណ៌ Background នៃ Items ជួរសេសឱ្យចេញពណ៌ខៀវស្រាល (`#eff6ff`)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* A pseudo-class is used to define a special state of an element (`:hover`, `:focus`, `:active`).
* `:first-child`, `:last-child`, and `:nth-child(n)` match elements based on their position among siblings.
* `:not(selector)` matches elements that do not match the specified selector.
* Pseudo-classes use a single colon `:` syntax.
</details>
