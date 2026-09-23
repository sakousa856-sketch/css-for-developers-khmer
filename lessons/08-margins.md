# មេរៀនទី ០៨៖ គម្លាតខាងក្រៅ (CSS Margins)

> **CSS Margin ប្រើសម្រាប់បង្កើតគម្លាតទទេនៅជុំវិញខាងក្រៅបន្ទាត់ Border នៃ Element។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីតួនាទីរបស់ **margin** ក្នុង CSS Box Model
* ចេះកំណត់ Margin តាមជ្រុងនីមួយៗ និងតាម Shorthand
* ចេះប្រើ `margin: auto` សម្រាប់តម្រឹម Container ឱ្យនៅចំកណ្តាល (Horizontal Centering)
* យល់ដឹងពីបាតុភូត **Margin Collapse**

---

## 📐 របៀបកំណត់ Margin (Individual Sides & Shorthand)

### ១. កំណត់តាមជ្រុងនីមួយៗ
```css
p {
  margin-top: 20px;
  margin-right: 15px;
  margin-bottom: 20px;
  margin-left: 15px;
}
```

---

### ២. Margin Shorthand (សរសេរកាត់តាមទ្រនិចនាឡិកា Clockwise)

| ចំនួនតម្លៃ | ឧទាហរណ៍ | អត្ថន័យ |
| :---: | :--- | :--- |
| **៤ តម្លៃ** | `margin: 10px 20px 30px 40px;` | Top (10px), Right (20px), Bottom (30px), Left (40px) |
| **៣ តម្លៃ** | `margin: 10px 20px 30px;` | Top (10px), Left & Right (20px), Bottom (30px) |
| **២ តម្លៃ** | `margin: 20px 40px;` | Top & Bottom (20px), Left & Right (40px) |
| **១ តម្លៃ** | `margin: 20px;` | គ្រប់ជ្រុងទាំង ៤ មានទំហំ 20px ទាំងអស់ |

---

## 🎯 ការប្រើប្រាស់ `margin: auto` សម្រាប់តម្រឹមចំកណ្តាល

ដើម្បីឱ្យ Element (ប្រភេទ Block ដូចជា `<div>`) រំកិលទៅនៅចំកណ្តាលផ្ដេកនៃអេក្រង់ (Horizontally Center) យើងត្រូវកំណត់៖
1. `width` ឬ `max-width` ជាក់លាក់
2. `margin: 0 auto;`

```css
.container {
  max-width: 900px;
  margin: 0 auto; /* Top/Bottom = 0, Left/Right = auto (Centered) */
  background-color: #ffffff;
  padding: 20px;
}
```

---

## 💥 បាតុភូត Margin Collapse (Vertical Margin Collapse)

![CSS Margin Collapse Mechanism](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-margin-collapse.svg)

នៅពេល Element ប្រភេទ Block ពីរស្ថិតនៅពីលើ និងពីក្រោមគ្នា (Top and Bottom margins) គម្លាតរវាងពួកវានឹង **មិនបូកបញ្ចូលគ្នាឡើយ**។ ផ្ទុយទៅវិញ Browser នឹងយកតែ **Margin ណាដែលធំជាងគេតែមួយគត់** មកអនុវត្ត៖

```css
h1 {
  margin-bottom: 30px; /* បាតក្រោម = 30px */
}

p {
  margin-top: 20px;    /* ក្បាលលើ = 20px */
}
```
👉 **លទ្ធផលជាក់ស្តែង:** គម្លាតរវាង `h1` និង `p` គឺ **30px** (មិនមែន 50px ឡើយ) ព្រោះ `30px` ធំជាង `20px`។

*(ចំណាំ៖ Margin ខាងឆ្វេង និងស្តាំ មិនមានបញ្ហា Margin Collapse ឡើយ)*

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Margins Demo</title>
  <style>
    body {
      background-color: #f1f5f9;
      font-family: Arial, sans-serif;
    }

    .main-wrapper {
      max-width: 600px;
      margin: 40px auto; /* Centered with 40px top/bottom */
      background-color: white;
      padding: 25px;
      border-radius: 8px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    }

    .box-1 {
      background-color: #bfdbfe;
      margin-bottom: 25px;
      padding: 15px;
    }

    .box-2 {
      background-color: #bbf7d0;
      margin-top: 15px;
      padding: 15px;
    }
  </style>
</head>
<body>

  <div class="main-wrapper">
    <div class="box-1">Box 1 (margin-bottom: 25px)</div>
    <div class="box-2">Box 2 (margin-top: 15px) ➔ គម្លាតរួមគឺ 25px (Collapsed)</div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **`margin: auto` មិនដំណើរការលើ Inline Elements:** កុំប្រើ `margin: auto` លើ `<span>` ឬ `<a>` លុះត្រាតែប្តូរ `display: block` ឬ `display: flex` សិន។
* ❌ **Negative Margins (`margin-top: -10px`):** អាចប្រើបានដើម្បីទាញ Element ឱ្យរំកិលត្រឡប់ក្រោយ ប៉ុន្តែគួរប្រយ័ត្នកុំឱ្យបាំង Element ផ្សេង។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត container មួយមាន `width: 500px;` ហើយប្រើ `margin: 50px auto;` ដើម្បីតម្រឹមឱ្យនៅចំកណ្តាលទំព័រ។
2. បង្កើតប្រអប់ពីរបន្តបន្ទាប់គ្នា និងសង្កេតមើលបាតុភូត Margin Collapse។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `margin` properties are used to create space around elements, outside of any defined borders.
* Margin shorthand follows clockwise order: `top`, `right`, `bottom`, `left`.
* `margin: 0 auto;` centers a block element horizontally within its container if it has a specified width.
* Top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margins (Margin Collapse).
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>8</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>០៨</strong> នៃ <strong>៦០</strong></p>

| [← Prev](07-borders.md) | [01](01-introduction.md) | ... | [06](06-backgrounds.md) | [07](07-borders.md) | **[ 08 ]** | [09](09-padding.md) | [10](10-height-and-width.md) | ... | [60](60-modern-features.md) | [Next →](09-padding.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
