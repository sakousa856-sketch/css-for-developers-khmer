# មេរៀនទី ៣១៖ មីនុយទម្លាក់ចុះ (CSS Dropdowns)

> **CSS Dropdown ប្រើសម្រាប់បង្កើត Menu ទម្លាក់ចុះនៅពេលដែលអ្នកប្រើប្រាស់ដាក់ Mouse Hover ឬចុចលើប៊ូតុង។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីរចនាសម្ព័ន្ធ HTML សម្រាប់បង្កើត Dropdown
* ចេះបង្កើត Pure CSS Dropdown ដោយប្រើ `:hover` និង `position: absolute`
* ចេះបន្ថែមស្រមោល និងរចនាបថទំនើបសម្រាប់ Dropdown Items

---

## 🏗️ រចនាសម្ព័ន្ធ និង Logic នៃ CSS Dropdown

1. **Container (`.dropdown`):** ត្រូវកំណត់ `position: relative;` ដើម្បីធ្វើជាបង្គោល Reference និង `display: inline-block;`។
2. **Dropdown Menu (`.dropdown-content`):** ត្រូវកំណត់ `position: absolute;`, `display: none;` (លាក់ទុកជាមុន), និង `z-index: 10;`។
3. **Trigger (`:hover`):** នៅពេល Hover លើ `.dropdown` ត្រូវកំណត់ `.dropdown-content { display: block; }` មកវិញ។

```css
/* 1. Container បង្គោល */
.dropdown {
  position: relative;
  display: inline-block;
}

/* 2. Menu ទម្លាក់ចុះ (លាក់ទុក) */
.dropdown-content {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  min-width: 180px;
  background-color: #ffffff;
  box-shadow: 0 8px 16px rgba(0,0,0,0.15);
  border-radius: 6px;
  overflow: hidden;
  z-index: 100;
}

/* 3. បង្ហាញ Menu ពេល Hover */
.dropdown:hover .dropdown-content {
  display: block;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Dropdowns Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 50px;
      background-color: #f8fafc;
    }

    .dropbtn {
      background-color: #2563eb;
      color: white;
      padding: 12px 20px;
      font-size: 16px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-weight: 500;
    }

    .dropdown {
      position: relative;
      display: inline-block;
    }

    .dropdown-content {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      background-color: #ffffff;
      min-width: 180px;
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
      border: 1px solid #e2e8f0;
      border-radius: 8px;
      z-index: 10;
      margin-top: 5px;
    }

    .dropdown-content a {
      color: #334155;
      padding: 12px 16px;
      text-decoration: none;
      display: block;
      transition: background-color 0.2s;
    }

    .dropdown-content a:hover {
      background-color: #f1f5f9;
      color: #2563eb;
    }

    /* Trigger Display */
    .dropdown:hover .dropdown-content {
      display: block;
    }

    .dropdown:hover .dropbtn {
      background-color: #1d4ed8;
    }
  </style>
</head>
<body>

  <div class="dropdown">
    <button class="dropbtn">ជ្រើសរើសវគ្គសិក្សា ▼</button>
    <div class="dropdown-content">
      <a href="#">HTML5 Master</a>
      <a href="#">CSS Modern Layouts</a>
      <a href="#">JavaScript Core</a>
      <a href="#">React & Next.js</a>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **បញ្ហាគម្លាតរវាងប៊ូតុង និង Menu (Hover Gap):** ប្រសិនបើអ្នកដាក់ `margin-top: 20px;` ធំពេក ពេល Mouse រំកិលចេញពីប៊ូតុងទៅរក Menu វានឹងរលត់បាត់ (Lost hover)។ គួរប្រើ `padding` ឬកំណត់ចម្ងាយល្មម។
* ✅ **ដាក់ `z-index` ខ្ពស់គួរសម:** ដើម្បីកុំឱ្យ Dropdown Menu លិចនៅពីក្រោម Cards ឬ Banner ខាងក្រោម។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Dropdown Navbar Item មួយដែលមានឈ្មោះថា "Services ▼"។
2. បង្ហាញ Sub-items ៣ ជម្រើសនៅពេល Hover។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Dropdowns can be created with pure CSS using `position: relative` on container and `position: absolute` on the dropdown content.
* The dropdown content is hidden by default (`display: none`) and shown on hover (`:hover .dropdown-content { display: block; }`).
* Use `z-index` to keep the dropdown menu on top of other content.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>31</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៣១</strong> នៃ <strong>៦០</strong></p>

| [← Prev](30-navigation-bars.md) | [01](01-introduction.md) | ... | [29](29-opacity.md) | [30](30-navigation-bars.md) | **[ 31 ]** | [32](32-image-gallery.md) | [33](33-attribute-selectors.md) | ... | [60](60-modern-features.md) | [Next →](32-image-gallery.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
