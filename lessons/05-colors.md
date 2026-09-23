# មេរៀនទី ០៥៖ ការប្រើប្រាស់ពណ៌ក្នុង CSS (CSS Colors)

> **CSS គាំទ្រការកំណត់ពណ៌តាមរយៈ Color Names, HEX, RGB, RGBA, HSL និង HSLA។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ស្គាល់ទម្រង់នៃការកំណត់ពណ៌ទាំងអស់ក្នុង CSS
* យល់ច្បាស់ពីរបៀបប្រើ **HEX Codes** និង **RGB / RGBA**
* ចេះកំណត់កម្រិតថ្លា (Transparency / Alpha Channel) តាមរយៈ **RGBA / HSLA**

---

## 🎨 ទម្រង់កំណត់ពណ៌ទាំង ៥ ប្រភេទក្នុង CSS

### ១. Color Names (ឈ្មោះពណ៌ស្តង់ដារ)
CSS មានឈ្មោះពណ៌ស្តង់ដារជាង ១៤០ ឈ្មោះដូចជា `red`, `blue`, `tomato`, `dodgerblue`, `mediumseagreen`៖
```css
h1 {
  color: dodgerblue;
}
```

---

### ២. HEX Color Codes (`#RRGGBB`)
HEX (Hexadecimal) គឺជាទម្រង់ពេញនិយមបំផុតក្នុងចំណោម Web Developers។ វាប្រើលេខមូលដ្ឋាន ១៦ (ពី `0-9` និង `A-F`):
* `RR` = Red (ក្រហម)
* `GG` = Green (បៃតង)
* `BB` = Blue (ខៀវ)

```css
p {
  color: #ff5733;         /* ពណ៌ទឹកក្រូចរាងក្រហម */
  background-color: #0f172a; /* ពណ៌ផ្ទៃងងឹត Slate */
}
```

---

### ៣. RGB (`rgb(red, green, blue)`)
កំណត់តម្លៃពន្លឺនៃពណ៌ក្រហម បៃតង និងខៀវ ចាប់ពី `0` ដល់ `255`៖
```css
.card {
  background-color: rgb(37, 99, 235); /* ពណ៌ខៀវ */
}
```

---

### ៤. RGBA (`rgba(red, green, blue, alpha)`)
ដូចគ្នានឹង RGB ដែរ ប៉ុន្តែបានបន្ថែម **Alpha Channel** (កម្រិតថ្លា) ចាប់ពី `0.0` (ថ្លាឆ្លុះមើលធ្លុះទាំងស្រុង) ដល់ `1.0` (ដិតច្បាស់ពេញលេញ)៖
```css
.overlay {
  /* ពណ៌ខ្មៅថ្លា ៥០% */
  background-color: rgba(0, 0, 0, 0.5);
}
```

---

### ៥. HSL & HSLA (`hsl(hue, saturation, lightness)`)
* **Hue (ពណ៌):** មុំរង្វង់ពណ៌ពី `0` ដល់ `360` (`0` = ក្រហម, `120` = បៃតង, `240` = ខៀវ)
* **Saturation (កម្រិតដិត):** ភាគរយពី `0%` (ពណ៌ប្រផេះ) ដល់ `100%` (ពណ៌ស្រស់ដិត)
* **Lightness (កម្រិតពន្លឺ):** ភាគរយពី `0%` (ខ្មៅសុទ្ធ) ដល់ `100%` (សសុទ្ធ), `50%` (ពណ៌លំនាំដើម)

```css
.badge {
  background-color: hsla(142, 76%, 36%, 0.8);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Colors Demo</title>
  <style>
    .box {
      width: 200px;
      padding: 15px;
      margin: 10px;
      border-radius: 8px;
      color: white;
      font-weight: bold;
      text-align: center;
    }

    .hex-box  { background-color: #3b82f6; } /* HEX */
    .rgb-box  { background-color: rgb(239, 68, 68); } /* RGB */
    .rgba-box { background-color: rgba(16, 185, 129, 0.6); } /* RGBA Transparent */
    .hsl-box  { background-color: hsl(271, 91%, 65%); } /* HSL */
  </style>
</head>
<body>

  <div class="box hex-box">HEX: #3b82f6</div>
  <div class="box rgb-box">RGB: rgb(239, 68, 68)</div>
  <div class="box rgba-box">RGBA: 60% Alpha</div>
  <div class="box hsl-box">HSL: Purple</div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* 💡 **Opacity vs RGBA:** ប្រសិនបើអ្នកប្រើ `opacity: 0.5` នោះ **អត្ថបទខាងក្នុងកូនៗទាំងអស់** នឹងថ្លាព្រាលតាមទាំងអស់។ ប្រសិនបើអ្នកចង់ឱ្យថ្លា **តែផ្ទៃ Background** នោះត្រូវប្រើ `background-color: rgba(...)` វិញ។
* ✅ **Color Contrast Ratio (A11y):** ត្រូវប្រាកដថាពណ៌អក្សរ និងពណ៌ Background មានកម្រិតកម្រិតពន្លឺខុសគ្នាគ្រប់គ្រាន់ (Contrast Ratio យ៉ាងហោច 4.5:1) ដើម្បីឱ្យអ្នកប្រើប្រាស់ងាយស្រួលអាន។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត `<div>` មួយមាន `background-color` ជាពណ៌ខ្មៅថ្លា ៧០% (`rgba(0,0,0,0.7)`).
2. កំណត់ពណ៌អក្សរឱ្យចេញពណ៌ស ដោយប្រើ HEX Code `#ffffff`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Colors in CSS can be specified using predefined color names, RGB, HEX, HSL, RGBA, and HSLA values.
* HEX is written as `#RRGGBB` where RR, GG, and BB are hex values between `00` and `FF`.
* RGBA allows adding transparency through an Alpha channel between `0.0` (fully transparent) and `1.0` (fully opaque).
* Use `rgba()` background instead of `opacity` if you only want the background to be translucent without affecting children elements.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ០៤៖ ការដាក់ចំណាំក្នុង CSS (CSS Comments)](04-comments.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ០៦៖ ផ្ទៃខាងក្រោយ (CSS Backgrounds) ➡️](06-backgrounds.md) |
