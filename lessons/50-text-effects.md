# មេរៀនទី ៥០៖ ផលប៉ះពាល់អក្សរ (CSS Text Effects)

> **CSS Text Effects ប្រើសម្រាប់កាត់អត្ថបទច្រើនជួរ (`-webkit-line-clamp`) បំបែកពាក្យវែងៗ (`word-break`) និងបង្កើតស្រមោលអក្សរ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបំបែកពាក្យវែងៗកុំឱ្យធ្លាយប្រអប់ (`word-wrap`, `word-break`)
* ចេះកាត់អត្ថបទវែង **ច្រើនបន្ទាត់ (Multi-line Truncation)** ដោយប្រើ `-webkit-line-clamp`
* ចេះបង្កើតស្រមោលអក្សរ 3D / Neon Glow តាម `text-shadow`

---

## ✂️ Multi-Line Text Truncation (`-webkit-line-clamp` ⭐⭐⭐)

នៅពេលអ្នកចង់កាត់កថាខណ្ឌវែងៗឱ្យបង្ហាញត្រឹមតែ **២ ឬ ៣ បន្ទាត់គត់** រួចចេញសញ្ញាចុចបី `...`៖

```css
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;        /* កំណត់ត្រឹម ២ បន្ទាត់ */
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

---

## 🧱 `word-break` និង `overflow-wrap`

នៅពេលមានតំណភ្ជាប់ URL វែងអន្លាយ ឬពាក្យវែងដែលគ្មាន Space វានឹងហៀរចេញក្រៅ Card៖

```css
.force-wrap {
  overflow-wrap: break-word; /* បង្ខំបំបែកពាក្យឱ្យចុះបន្ទាត់ថ្មី */
  word-break: break-all;
}
```

---

## 🌟 Neon Text Glow Effect (`text-shadow`)

```css
.neon-text {
  color: #ffffff;
  text-shadow:
    0 0 5px #00ffff,
    0 0 10px #00ffff,
    0 0 20px #00ffff,
    0 0 40px #0088ff;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Text Effects Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #0f172a;
      color: white;
    }

    .card {
      background-color: #1e293b;
      padding: 20px;
      border-radius: 8px;
      max-width: 320px;
      margin-bottom: 25px;
    }

    /* 2 Lines Clamp */
    .clamp-desc {
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
      color: #94a3b8;
      line-height: 1.5;
    }

    /* Neon Heading */
    .neon-title {
      font-size: 28px;
      color: #fff;
      text-shadow: 0 0 7px #38bdf8, 0 0 15px #38bdf8, 0 0 30px #0284c7;
      text-align: center;
    }
  </style>
</head>
<body>

  <h1 class="neon-title">NEON CYBER TITLE</h1>

  <div class="card">
    <h3>ចំណងជើងកាត</h3>
    <p class="clamp-desc">
      នេះគឺជាអត្ថបទពិពណ៌នាដ៏វែងអន្លាយដែលរៀបរាប់អំពីព័ត៌មានលម្អិតផ្សេងៗ។ ដោយសារយើងបានកំណត់ line-clamp ត្រឹម ២ បន្ទាត់ ដូច្នេះអត្ថបទដែលសល់នឹងត្រូវកាត់ចេញជាសញ្ញាចុចបីដោយស្វ័យប្រវត្តិ។
    </p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Modern Standard:** `-webkit-line-clamp` ត្រូវបានគាំទ្រដោយគ្រប់ Modern Browsers ទាំងអស់ (Chrome, Firefox, Safari, Edge) និងជាស្តង់ដារដែលគេប្រើប្រាស់លើ Blog Cards គ្រប់ទីកន្លែង។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class `.clamp-3` ដើម្បីកាត់អត្ថបទកថាខណ្ឌឱ្យនៅត្រឹម ៣ បន្ទាត់។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `-webkit-line-clamp: 2` truncates text to a specified number of lines.
* `overflow-wrap: break-word` prevents long words and URLs from overflowing their container.
* Multiple `text-shadow` values create striking neon glow or 3D text effects.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>50</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៥០</strong> នៃ <strong>៦០</strong></p>

| [← Prev](49-shadows-and-rounded.md) | [01](01-introduction.md) | ... | [48](48-rwd-mobile-first.md) | [49](49-shadows-and-rounded.md) | **[ 50 ]** | [51](51-web-fonts.md) | [52](52-2d-transforms.md) | ... | [60](60-modern-features.md) | [Next →](51-web-fonts.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
