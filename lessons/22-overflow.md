# មេរៀនទី ២២៖ ការគ្រប់គ្រងមាតិកាហៀរចេញ (CSS Overflow)

> **CSS `overflow` ប្រើសម្រាប់គ្រប់គ្រងថាតើត្រូវធ្វើដូចម្តេចនៅពេលដែលមាតិកាខាងក្នុង (Content) មានទំហំធំលើសពីទំហំប្រអប់ Container របស់វា។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីតម្លៃទាំង ៤ នៃ `overflow`: `visible`, `hidden`, `scroll`, `auto`
* ចេះបំបែកការគ្រប់គ្រងតាមអ័ក្ស `overflow-x` (ផ្ដេក) និង `overflow-y` (បញ្ឈរ)
* ចេះកាត់អត្ថបទវែងឱ្យចេញសញ្ញាចុចបី `...` (`text-overflow: ellipsis`)

---

## 📦 តម្លៃទាំង ៤ នៃ CSS Overflow

### ១. `overflow: visible` (Default)
* មាតិកាដែលលើសនឹង **ហៀរធ្លាយចេញក្រៅប្រអប់** មកជាន់លើ Elements ផ្សេងទៀត (មិនស្អាតឡើយ)

---

### ២. `overflow: hidden`
* មាតិកាដែលលើសនឹងត្រូវបាន **កាត់ចោល (Clipped)** មិនឱ្យមើលឃើញឡើយ និងគ្មាន Scrollbar ទេ
* និយមប្រើសម្រាប់៖ កាត់ជ្រុងរូបភាពក្នុង Rounded Card (`border-radius`), Clearfix

---

### ៣. `overflow: scroll`
* បន្ថែម Scrollbar ទាំងបញ្ឈរ និងផ្ដេកជានិច្ច ទោះបីជាមាតិកាមិនទាន់លើសទំហំក៏ដោយ

---

### ៤. `overflow: auto` (និយមប្រើបំផុត)
* បង្ហាញ Scrollbar **តែនៅពេលណាដែលមាតិកាហៀរលើសទំហំប៉ុណ្ណោះ** (Smart Scroll)

```css
.scrollable-card {
  height: 200px;
  overflow-y: auto; /* បង្ហាញ Scrollbar បញ្ឈរតែពេលអត្ថបទវែង */
  overflow-x: hidden;
}
```

---

## ✂️ ការកាត់អត្ថបទវែងឱ្យចេញសញ្ញាចុចបី `...` (Single-line Text Truncation)

រូបមន្តវេទមន្ត ៣ បន្ទាត់ដើម្បីកាត់ចំណងជើងវែងៗកុំឱ្យធ្លាក់បន្ទាត់៖

```css
.truncate-text {
  white-space: nowrap;        /* ហាមមិនឱ្យចុះបន្ទាត់ថ្មី */
  overflow: hidden;           /* កាត់អក្សរដែលលើសចោល */
  text-overflow: ellipsis;    /* បង្ហាញសញ្ញា ... នៅចុងបញ្ចប់ */
  max-width: 250px;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Overflow Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f8fafc;
      padding: 30px;
    }

    .box {
      width: 260px;
      height: 120px;
      padding: 15px;
      border: 2px solid #cbd5e1;
      border-radius: 8px;
      background-color: white;
      margin-bottom: 20px;
    }

    .auto-scroll {
      overflow-y: auto;
    }

    .truncated {
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      width: 220px;
      background: #e2e8f0;
      padding: 8px;
      border-radius: 4px;
    }
  </style>
</head>
<body>

  <h3>1. Overflow Auto (Scroll ពេលអក្សរវែង)</h3>
  <div class="box auto-scroll">
    <p>កថាខណ្ឌនេះមានអត្ថបទច្រើនដែលវែងលើសពីកម្ពស់ 120px របស់ប្រអប់។ ដូច្នេះ Browser នឹងបង្ហាញ Scrollbar ដោយស្វ័យប្រវត្តិតាមរយៈ <code>overflow-y: auto</code>។ សាកល្បង Scroll មើលមាតិកាបន្ថែមនៅខាងក្រោមនេះបាន។</p>
  </div>

  <h3>2. Text Ellipsis (កាត់អក្សរចេញ ...)</h3>
  <div class="truncated">
    នេះជាចំណងជើងព័ត៌មានវែងអន្លាយដែលត្រូវកាត់ចេញ
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ប្រយ័ត្ន `overflow: hidden` បាំង Dropdown / Tooltip:** ប្រសិនបើអ្នកដាក់ `overflow: hidden` លើ Card Container នោះ Menu Dropdown ឬ Tooltip ដែលលៀនចេញពី Card នឹងត្រូវកាត់ដាច់បាត់មើលមិនឃើញឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប្រអប់មួយមាន `width: 300px; height: 100px;`។
2. ដាក់ `overflow-y: auto;` ហើយសរសេរអត្ថបទឱ្យច្រើនដើម្បីមើលរបៀបដែល Scrollbar បង្ហាញឡើង។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `overflow` property controls what happens to content that is too big to fit into an area.
* `visible`: Default, renders outside the element's box.
* `hidden`: The overflow is clipped and invisible.
* `scroll`: The overflow is clipped, but a scrollbar is added.
* `auto`: Similar to scroll, but adds scrollbars only when necessary.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>22</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>២២</strong> នៃ <strong>៦០</strong></p>

| [← Prev](21-position.md) | [01](01-introduction.md) | ... | [20](20-max-width.md) | [21](21-position.md) | **[ 22 ]** | [23](23-float-and-clear.md) | [24](24-inline-block.md) | ... | [60](60-modern-features.md) | [Next →](23-float-and-clear.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
