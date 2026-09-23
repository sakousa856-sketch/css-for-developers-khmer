# មេរៀនទី ០៩៖ គម្លាតខាងក្នុង (CSS Padding)

> **CSS Padding ប្រើសម្រាប់បង្កើតគម្លាតទទេនៅចន្លោះរវាងមាតិកា (Content) និងបន្ទាត់ព្រំដែន (Border) របស់ Element។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីភាពខុសគ្នារវាង **Margin (ខាងក្រៅ)** និង **Padding (ខាងក្នុង)**
* ចេះកំណត់ Padding តាមជ្រុងនីមួយៗ និងតាម Shorthand
* យល់ដឹងពីផលប៉ះពាល់នៃ Padding ទៅលើទំហំទទឹងសរុបនៃ Element

---

## 📐 របៀបកំណត់ Padding

### ១. កំណត់តាមជ្រុងនីមួយៗ
```css
.card {
  padding-top: 20px;
  padding-right: 15px;
  padding-bottom: 20px;
  padding-left: 15px;
}
```

---

### ២. Padding Shorthand (តាមទ្រនិចនាឡិកា Clockwise)

```css
/* ៤ តម្លៃ: Top, Right, Bottom, Left */
.box-1 { padding: 10px 20px 15px 25px; }

/* ៣ តម្លៃ: Top, (Left & Right), Bottom */
.box-2 { padding: 10px 20px 15px; }

/* ២ តម្លៃ: (Top & Bottom), (Left & Right) -> និយមប្រើបំផុតសម្រាប់ Buttons */
.btn   { padding: 12px 24px; }

/* ១ តម្លៃ: គ្រប់ជ្រុងទាំង ៤ ស្មើគ្នា */
.card  { padding: 20px; }
```

---

## ⚠️ ផលប៉ះពាល់នៃ Padding ទៅលើទំហំ Element (Padding and Element Width)

តាមលំនាំដើមរបស់ CSS (`box-sizing: content-box`):
នៅពេលអ្នកកំណត់ `width: 300px;` ហើយបន្ថែម `padding: 25px;` នោះ **ទទឹងសរុបដែលបង្ហាញនៅលើអេក្រង់នឹងឡើងដល់ 350px!**

$$\text{Total Width} = 300\text{px} + 25\text{px (left)} + 25\text{px (right)} = 350\text{px}$$

👉 បញ្ហានេះតែងធ្វើឱ្យប្លង់គេហទំព័រធ្លាក់ ឬរីកធំខុសគម្រោង។

### 💡 ដំណោះស្រាយ៖ ប្រើប្រាស់ `box-sizing: border-box`
នៅពេលកំណត់ `box-sizing: border-box` នោះ Browser នឹងបញ្ចូល Padding និង Border ទៅក្នុងទំហំ 300px ស្រាប់ ធ្វើឱ្យទទឹងសរុបនៅថេរ 300px ដដែល៖

```css
.box {
  width: 300px;
  padding: 25px;
  box-sizing: border-box; /* រក្សាទទឹង 300px ដដែល */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Padding Demo</title>
  <style>
    .btn {
      display: inline-block;
      background-color: #2563eb;
      color: white;
      text-decoration: none;
      font-weight: bold;
      /* Top/Bottom = 12px, Left/Right = 24px */
      padding: 12px 24px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
    }

    .card {
      background-color: #f8fafc;
      border: 1px solid #cbd5e1;
      padding: 30px; /* គម្លាតខាងក្នុង 30px ជុំវិញអត្ថបទ */
      border-radius: 8px;
      max-width: 400px;
      margin: 20px 0;
    }
  </style>
</head>
<body>

  <div class="card">
    <h2>កាតព័ត៌មាន</h2>
    <p>Padding ជួយកុំឱ្យអក្សរនៅជាប់ទល់នឹងបន្ទាត់ Border ពេក ដែលធ្វើឱ្យមានខ្យល់អាកាសស្រួលអាន។</p>
    <button class="btn">ស្វែងយល់បន្ថែម</button>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Padding ទទួលពណ៌ផ្ទៃ Background:** Margin គឺជាលំហទទេថ្លា (Transparent) ជានិច្ច ចំណែក Padding នឹងមានពណ៌ដូច `background-color` របស់ Element នោះដែរ។
* ✅ **Reset Box Sizing:** គួរដាក់ `* { box-sizing: border-box; }` នៅដើមឯកសារ CSS ជានិច្ច ដើម្បីកុំឱ្យ Padding បង្កើនទំហំទទឹង Element ដោយមិនដឹងខ្លួន។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប៊ូតុង `<button>` មួយដោយប្រើ `padding: 10px 20px;` និង `background-color: #059669;`។
2. បង្កើត `<div>` មួយមាន `width: 300px; padding: 20px; box-sizing: border-box;` ហើយពិនិត្យមើលទទឹងជាក់ស្តែងក្នុង Chrome DevTools។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `padding` properties are used to generate space around an element's content, inside of any defined borders.
* Padding background matches the element's `background-color`.
* By default, padding increases the total calculated width of an element.
* Use `box-sizing: border-box` to include padding in the element's width calculation.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ០៨៖ គម្លាតខាងក្រៅ (CSS Margins)](08-margins.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ១០៖ កម្ពស់ និងទទឹង (CSS Height, Width & Max-Width) ➡️](10-height-and-width.md) |
