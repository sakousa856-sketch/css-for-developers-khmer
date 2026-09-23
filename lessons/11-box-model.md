# មេរៀនទី ១១៖ គំរូប្រអប់ (CSS Box Model)

> **នៅក្នុង HTML/CSS គ្រប់ Element ទាំងអស់ត្រូវបានចាត់ទុកជា «ប្រអប់រាងចតុកោណកែង» (Rectangular Box)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីស្រទាប់ទាំង ៤ នៃ **CSS Box Model**
* ចេះគណនាទំហំទទឹង និងកម្ពស់សរុបនៃ Element ជាក់ស្តែង
* យល់ច្បាស់ពី `box-sizing: content-box` ទល់នឹង `box-sizing: border-box`

---

## 📦 ស្រទាប់ទាំង ៤ នៃ CSS Box Model

![CSS Box Model Architecture](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-box-model.svg)

1. **Content (មាតិកា):** ផ្ទៃស្នូលកណ្តាលដែលផ្ទុកអត្ថបទ (Text) ឬរូបភាព (Image) ដែលមានទំហំ `width` $\times$ `height`។
2. **Padding (គម្លាតខាងក្នុង):** ផ្ទៃលំហទទេថ្លា ឬមានពណ៌ព័ទ្ធជុំវិញមាតិកា (នៅខាងក្នុងបន្ទាត់ Border)។
3. **Border (បន្ទាត់ព្រំដែន):** បន្ទាត់ដែលគូសព័ទ្ធជុំវិញ Padding និង Content។
4. **Margin (គម្លាតខាងក្រៅ):** ផ្ទៃលំហទទេថ្លាដែលរុញ Element ឱ្យឃ្លាតឆ្ងាយពី Elements ដទៃទៀត (នៅខាងក្រៅបន្ទាត់ Border)។

---

## 🧮 ការគណនាទំហំទទឹងសរុប (Total Element Width)

### ១. Default Behavior (`box-sizing: content-box`)
តាមលំនាំដើម `width` សំដៅលើតែ **Content** ប៉ុណ្ណោះ។ ដូច្នេះទំហំទទឹងពិតប្រាកដដែលបង្ហាញលើអេក្រង់ត្រូវគណនាដូចតទៅ៖

$$\text{Total Width} = \text{width} + \text{padding-left} + \text{padding-right} + \text{border-left} + \text{border-right}$$

**ឧទាហរណ៍៖**
```css
div {
  width: 320px;
  padding: 10px;
  border: 5px solid gray;
  margin: 0;
}
```
👉 ទទឹងសរុប $= 320\text{px} + 10\text{px} + 10\text{px} + 5\text{px} + 5\text{px} = \mathbf{350\text{px}}$។

---

### ២. ដំណោះស្រាយទំនើប (`box-sizing: border-box`)
នៅពេលប្រើ `border-box` នោះទំហំ `width` នឹងរាប់បញ្ចូលទាំង Content, Padding និង Border ស្រាប់៖

```css
* {
  box-sizing: border-box;
}
```
ប្រសិនបើ `width: 320px;` ទោះបីជាអ្នកបន្ថែម `padding: 10px;` និង `border: 5px solid gray;` ក៏ទទឹងសរុបនៅតែ **320px** ដដែល (Content ខាងក្នុងនឹងរួញដោយស្វ័យប្រវត្តិតាមសមាមាត្រ)។

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Box Model Demo</title>
  <style>
    /* CSS Universal Reset */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      padding: 30px;
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
    }

    .box-model-demo {
      width: 350px;
      background-color: #93c5fd; /* Content Area */
      padding: 25px;             /* Padding Area */
      border: 8px solid #1d4ed8; /* Border Area */
      margin: 30px auto;         /* Margin Area (Centered) */
      text-align: center;
      border-radius: 8px;
    }
  </style>
</head>
<body>

  <div class="box-model-demo">
    <h3>Content Box</h3>
    <p>ពិនិត្យមើលក្នុង DevTools: Content (ខៀវស្រាល), Padding (បៃតង), Border (លឿង), Margin (ទឹកក្រូច)។</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Modern CSS Reset Rule:** តែងតែដាក់ `* { box-sizing: border-box; }` នៅលើគេបង្អស់នៃ file CSS របស់អ្នកជានិច្ច ដើម្បីកុំឱ្យមានការភ័ន្តច្រឡំក្នុងការគណនាទំហំប្លង់។
* 💡 **Inspect Element ក្នុង Browser:** ចុចកណ្ដុរស្ដាំ ➔ **Inspect** ➔ មើលផ្ទាំង **Computed** ដើម្បីឃើញដ្យាក្រាម Box Model ពិតប្រាកដជាមួយតម្លៃលេខនៃ Element នីមួយៗ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បើក Browser DevTools (F12) លើគេហទំព័រណាមួយ រួចស្វែងរកផ្ទាំង **Computed Box Model**។
2. បង្កើតប្រអប់មួយមាន `width: 250px; padding: 20px; border: 4px solid black;` ដោយប្រើ `box-sizing: border-box` រួចផ្ទៀងផ្ទាត់ទទឹងសរុប។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* All HTML elements can be considered as boxes.
* The CSS box model consists of: margins, borders, padding, and the actual content.
* `box-sizing: content-box` (default) adds padding and border on top of the specified width.
* `box-sizing: border-box` includes padding and border within the specified width.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>11</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១១</strong> នៃ <strong>៦០</strong></p>

| [← Prev](10-height-and-width.md) | [01](01-introduction.md) | ... | [09](09-padding.md) | [10](10-height-and-width.md) | **[ 11 ]** | [12](12-outline.md) | [13](13-text.md) | ... | [60](60-modern-features.md) | [Next →](12-outline.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
