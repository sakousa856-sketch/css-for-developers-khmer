# មេរៀនទី ២៤៖ ធាតុប្លង់ Inline-Block (CSS Inline-Block Layout)

> **`display: inline-block` អនុញ្ញាតឱ្យ Elements តម្រៀបគ្នាជាជួរដេកផ្ដេក ដោយនៅតែអាចកំណត់ `width` និង `height` បានយ៉ាងពេញលេញ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីរបៀបប្រើ `inline-block` សម្រាប់បង្កើត Navigation Menus និង Grid Cards
* យល់ពីបញ្ហាគម្លាតចន្លោះ **"Whitespace Gap Issue"** នៃ `inline-block`
* ចេះវិធីដោះស្រាយបញ្ហាគម្លាតអក្សរដោយប្រើ `font-size: 0` ឬបំបាត់ space ក្នុង HTML

---

## 🏗️ ការបង្កើត Navigation Bar ដោយប្រើ Inline-Block

```css
.nav-menu {
  list-style: none;
  background-color: #0f172a;
  padding: 0;
}

.nav-menu li {
  display: inline-block; /* តម្រៀបជាជួរដេក */
}

.nav-menu li a {
  display: block;
  color: white;
  text-decoration: none;
  padding: 14px 20px;
}

.nav-menu li a:hover {
  background-color: #334155;
}
```

---

## 💥 បញ្ហាគម្លាតអក្សរ 4px (The Whitespace Gap Issue)

ដោយសារ `inline-block` ត្រូវបានចាត់ទុកដូចជាតួអក្សរ (Text) ដូច្នេះនៅពេលដែលអ្នកចុច **Enter ចុះបន្ទាត់** ក្នុងកូដ HTML នោះ Browser នឹងចាត់ទុកវាជា Space (ប្រហែល 4px) ដែលធ្វើឱ្យ Card ទាំង ៣ មិនអាចដាក់ `width: 33.33%` ពេញ ១០០% បានឡើយ (វានឹងធ្លាក់បន្ទាត់)។

### 🛠️ វិធីដោះស្រាយ៖
1. **ដំណោះស្រាយ CSS:** ដាក់ `font-size: 0;` លើ Parent Container រួចកំណត់ `font-size: 16px;` ឡើងវិញលើកូនៗ។
2. **ដំណោះស្រាយទំនើប:** ប្រើ **Flexbox (`display: flex; gap: ...`)** ជំនួសវិញ។

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Inline-Block Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
      padding: 30px;
    }

    .card-row {
      font-size: 0; /* ដោះស្រាយ Whitespace Gap */
    }

    .card-box {
      display: inline-block;
      width: 31%;
      margin: 0 1.15%;
      background: white;
      padding: 20px;
      box-sizing: border-box;
      border-radius: 8px;
      font-size: 16px; /* កំណត់ Font-size ធម្មតាឡើងវិញលើកូន */
      vertical-align: top; /* តម្រឹមកំពូលឱ្យស្មើគ្នា */
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }
  </style>
</head>
<body>

  <h2>ជួរ Cards តម្រៀបដោយ Inline-Block</h2>

  <div class="card-row">
    <div class="card-box">
      <h3>Card 1</h3>
      <p>មាតិកាកាតទីមួយ</p>
    </div>
    <div class="card-box">
      <h3>Card 2</h3>
      <p>មាតិកាកាតទីពីរមានអក្សរវែងជាងគេបន្តិចដើម្បីតេស្ត vertical-align។</p>
    </div>
    <div class="card-box">
      <h3>Card 3</h3>
      <p>មាតិកាកាតទីបី</p>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ដាក់ `vertical-align: top` ជានិច្ច:** នៅពេលកាតមួយមានអត្ថបទច្រើនជាងកាតមួយទៀត កាតដែលនៅក្បែរវានឹងធ្លាក់ចុះក្រោមខុសទម្រង់ ប្រសិនបើអ្នកមិនដាក់ `vertical-align: top;`។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប្រអប់ `<div>` ចំនួន ៣ ដោយប្រើ `display: inline-block; width: 100px; height: 100px;`។
2. ដាក់ `vertical-align: top;` និងកំណត់ពណ៌ Background ផ្សេងៗគ្នា។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `display: inline-block` allows setting width and height while keeping elements inline.
* HTML whitespace between `inline-block` elements adds an unintended ~4px gap.
* Use `vertical-align: top` to ensure adjacent `inline-block` boxes align at the top edge.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>24</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>២៤</strong> នៃ <strong>៦០</strong></p>

| [← Prev](23-float-and-clear.md) | [01](01-introduction.md) | ... | [22](22-overflow.md) | [23](23-float-and-clear.md) | **[ 24 ]** | [25](25-align.md) | [26](26-combinators.md) | ... | [60](60-modern-features.md) | [Next →](25-align.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
