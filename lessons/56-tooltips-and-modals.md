# មេរៀនទី ៥៦៖ Tooltips & Modal Popup បែប Pure CSS

> **យើងអាចបង្កើត Tooltips និង Modal Popups ដោយប្រើប្រាស់តែ CSS សុទ្ធសាធ (Pure CSS) ដោយមិនចាំបាច់សរសេរ JavaScript សូម្បីតែមួយបន្ទាត់។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបង្កើត **Pure CSS Tooltip** ជាមួយ `::after` / `::before` និង `data-tooltip` attribute
* ចេះបង្កើត **Pure CSS Modal Popup** ដោយប្រើ `:target` pseudo-class
* ចេះបន្ថែមចលនា Smooth Fade & Scale លើ Modal

---

## 💬 ១. ការបង្កើត Pure CSS Tooltip

យើងប្រើ Custom Data Attribute `data-tooltip="អត្ថបទ"` ក្នុង HTML រួចទាញយកមកបង្ហាញក្នុង CSS តាមរយៈ `attr(data-tooltip)`៖

```css
.tooltip {
  position: relative;
  cursor: pointer;
}

/* ផ្ទាំងប្រអប់ Tooltip */
.tooltip::after {
  content: attr(data-tooltip); /* ទាញយកអត្ថបទពី HTML attribute */
  position: absolute;
  bottom: 125%;
  left: 50%;
  transform: translateX(-50%) translateY(6px);
  background-color: #0f172a;
  color: white;
  padding: 6px 10px;
  border-radius: 4px;
  font-size: 12px;
  white-space: nowrap;
  opacity: 0;
  visibility: hidden;
  transition: all 0.2s ease;
  z-index: 100;
}

/* បង្ហាញ Tooltip ពេល Hover */
.tooltip:hover::after {
  opacity: 1;
  visibility: visible;
  transform: translateX(-50%) translateY(0);
}
```

---

## 🪟 ២. ការបង្កើត Pure CSS Modal Popup (ប្រើ `:target`)

នៅពេលដែល User ចុច `<a href="#myModal">` នោះ URL Hash នឹងក្លាយជា `#myModal` ដែលធ្វើឱ្យ Selector `#myModal:target` ដំណើរការ៖

```css
/* ផ្ទៃ Backdrop ងងឹត (លាក់ទុកជាមុន) */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
  z-index: 1000;
}

/* បង្ហាញ Modal នៅពេល URL Hash ត្រូវគ្នា */
.modal-overlay:target {
  opacity: 1;
  visibility: visible;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Pure CSS Tooltips & Modal Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 40px;
      background-color: #f8fafc;
      text-align: center;
    }

    /* Tooltip */
    .has-tooltip {
      position: relative;
      display: inline-block;
      color: #2563eb;
      font-weight: bold;
      cursor: pointer;
    }

    .has-tooltip::after {
      content: attr(data-tooltip);
      position: absolute;
      bottom: 130%;
      left: 50%;
      transform: translateX(-50%);
      background-color: #0f172a;
      color: #fff;
      padding: 6px 12px;
      border-radius: 6px;
      font-size: 13px;
      white-space: nowrap;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.2s;
    }

    .has-tooltip:hover::after {
      opacity: 1;
    }

    /* Modal Styling */
    .btn-open {
      display: inline-block;
      margin-top: 20px;
      background-color: #0f172a;
      color: white;
      padding: 12px 24px;
      text-decoration: none;
      border-radius: 6px;
    }

    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.5);
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s ease;
    }

    .modal-overlay:target {
      opacity: 1;
      visibility: visible;
    }

    .modal-box {
      background: white;
      padding: 30px;
      border-radius: 12px;
      max-width: 400px;
      text-align: left;
      position: relative;
    }

    .btn-close {
      position: absolute;
      top: 15px;
      right: 15px;
      text-decoration: none;
      font-size: 20px;
      color: #64748b;
    }
  </style>
</head>
<body>

  <h2>Pure CSS Components</h2>

  <p>
    ដាក់ Mouse លើពាក្យ <span class="has-tooltip" data-tooltip="នេះជាសារជំនួយ Tooltip!">CSS Magic</span> ដើម្បីមើល Tooltip។
  </p>

  <a href="#demoModal" class="btn-open">បើកផ្ទាំង Modal Popup</a>

  <!-- Modal Target Structure -->
  <div id="demoModal" class="modal-overlay">
    <div class="modal-box">
      <a href="#" class="btn-close">&times;</a>
      <h3>ផ្ទាំង Modal ជោគជ័យ!</h3>
      <p>ផ្ទាំងនេះដំណើរការដោយប្រើប្រាស់តែ CSS <code>:target</code> សុទ្ធសាធ!</p>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **`pointer-events: none` លើ Tooltip:** ត្រូវដាក់ `pointer-events: none;` លើ `::after` ដើម្បីកុំឱ្យផ្ទាំង Tooltip ទៅរំខាន ឬបាំង Mouse Events ផ្សេងទៀត។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Tooltip ដោយប្រើ Attribute `data-tooltip="Save"` លើប៊ូតុងមួយ។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Pure CSS tooltips can be built using `::after` with `content: attr(data-tooltip)` and `:hover`.
* Pure CSS modal popups can be created with the `:target` pseudo-class.
* Use `pointer-events: none` on hidden tooltip elements to avoid interfering with user cursor events.
</details>
