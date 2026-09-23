# មេរៀនទី ៥៤៖ ការផ្លាស់ប្តូរដោយរលូន (CSS Transitions)

> **CSS Transitions ប្រើសម្រាប់ធ្វើឱ្យការផ្លាស់ប្តូរតម្លៃ Properties (ដូចជា ពណ៌ ទំហំ ស្រមោល) ប្រព្រឹត្តទៅដោយរលូនតាមពេលវេលាជាក់លាក់មួយ ដោយមិនប្តូរភ្លាមៗឆ្គងៗឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពី ៤ Properties នៃ CSS Transition
* ស្គាល់ Timing Functions សំខាន់ៗ (`ease`, `linear`, `ease-in-out`, `cubic-bezier`)
* ចេះសរសេរ `transition` Shorthand Property

---

## ⏱️ Properties ទាំង ៤ នៃ CSS Transition

### ១. `transition-property`
ឈ្មោះ Property ដែលត្រូវធ្វើចលនារលូន (ឧ. `background-color`, `transform`, `opacity`, ឬ `all`)។

---

### ២. `transition-duration`
រយៈពេលដែលត្រូវដំណើរការចលនា (គិតជាវិនាទី `s` ឬមីលីវិនាទី `ms` ឧ. `0.3s`, `300ms`)។

---

### ៣. `transition-timing-function` (ល្បឿននៃចលនា)
* `ease` (Default): ចាប់ផ្តើមយឺត រួចលឿន រួចយឺតនៅចុងបញ្ចប់
* `linear`: ល្បឿនថេរស្មើគ្នាតាំងពីដើមដល់ចប់
* `ease-in`: ចាប់ផ្តើមយឺត រួចលឿន
* `ease-out`: ចាប់ផ្តើមលឿន រួចយឺតនៅចុងបញ្ចប់
* `ease-in-out`: យឺតទាំងក្បាល និងចុង

---

### ៤. `transition-delay`
រយៈពេលរង់ចាំមុននឹងចាប់ផ្តើមដំណើរការចលនា (ឧ. `0.1s`)។

---

### ៥. Transition Shorthand (និយមប្រើបំផុត ⭐)
រូបមន្ត៖ `transition: [property] [duration] [timing-function] [delay];`

```css
.button {
  background-color: #2563eb;
  transform: translateY(0);
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  /* Transition Shorthand */
  transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
}

.button:hover {
  background-color: #1d4ed8;
  transform: translateY(-3px);
  box-shadow: 0 8px 16px rgba(37, 99, 235, 0.25);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Transitions Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 40px;
      background-color: #f8fafc;
    }

    .btn-interactive {
      background-color: #0f172a;
      color: white;
      padding: 12px 28px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      /* Smooth transitions on hover */
      transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease;
    }

    .btn-interactive:hover {
      background-color: #2563eb;
      transform: translateY(-4px);
      box-shadow: 0 10px 20px rgba(37, 99, 235, 0.3);
    }

    .btn-interactive:active {
      transform: translateY(-1px);
    }
  </style>
</head>
<body>

  <h2>សាកល្បងយក Mouse ដាក់ពីលើប៊ូតុង៖</h2>
  <button class="btn-interactive">Hover លើខ្ញុំ (Smooth Transition)</button>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ដាក់ `transition` លើ Base Class ជានិច្ច:** កុំដាក់ `transition` ក្នុង `:hover` ព្រោះនៅពេល User ដក Mouse ចេញ វានឹងរលត់ភ្លាមៗឆ្គងៗ (Snap back) ដោយគ្មានចលនារលូនត្រឡប់ក្រោយឡើយ។
* ❌ **ចៀសវាង `transition: all` លើ Properties ធ្ងន់ៗ:** បើអាច គួររាយឈ្មោះជាក់លាក់ដូចជា `transition: transform 0.2s, opacity 0.2s;` ដើម្បីកុំឱ្យប៉ះពាល់ដល់ Rendering Performance។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Card មួយមាន `transition: transform 0.3s ease, box-shadow 0.3s ease;`។
2. ពេល Hover ឱ្យរំកិលឡើងលើ `transform: translateY(-5px);` និងបញ្ចេញស្រមោលស្អាត។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS transitions provide a way to control animation speed when changing CSS properties.
* Shorthand: `transition: property duration timing-function delay;`.
* Always place the `transition` rule on the default element state, not on the `:hover` pseudo-class.
* Transitioning `transform` and `opacity` is GPU-accelerated and provides the smoothest performance.
</details>
