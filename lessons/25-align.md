# មេរៀនទី ២៥៖ ការតម្រឹមធាតុចំកណ្តាល (CSS Alignment)

> **ការតម្រឹម Element ឱ្យនៅចំកណ្តាលទាំងផ្ដេក និងបញ្ឈរ (Centering Elements) គឺជាជំនាញស្នូលដែល Web Developers ត្រូវតែស្ទាត់ជំនាញ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះតម្រឹមអត្ថបទ និង Inline Elements (`text-align: center`)
* ចេះតម្រឹម Block Elements ផ្ដេក (`margin: 0 auto`)
* ចេះតម្រឹមចំកណ្តាលពេញលេញ (Horizontally & Vertically Center) តាម ៣ វិធីសាស្ត្រ

---

## 🧭 វិធីសាស្ត្រតម្រឹមផ្ដេក (Horizontal Alignment)

### ១. តម្រឹមអត្ថបទ ឬរូបភាព (Inline / Inline-Block)
ដាក់ `text-align: center;` លើ **Parent Container**៖
```css
.parent {
  text-align: center;
}
```

### ២. តម្រឹមប្រអប់ Block Element
ដាក់ `margin: 0 auto;` លើ **Element ផ្ទាល់** (ត្រូវតែមាន `width` ឬ `max-width`):
```css
.card {
  width: 400px;
  margin: 0 auto;
}
```

---

## 🎯 វិធីសាស្ត្រតម្រឹមចំកណ្តាលពេញលេញ (Both Horizontal & Vertical Centering)

### វិធីទី ១៖ ប្រើប្រាស់ Flexbox (ងាយស្រួល និងពេញនិយមបំផុត ⭐)
```css
.parent {
  display: flex;
  justify-content: center; /* ផ្ដេក */
  align-items: center;     /* បញ្ឈរ */
  height: 300px;
}
```

---

### វិធីទី ២៖ ប្រើប្រាស់ CSS Grid (ខ្លីបំផុត ត្រឹម ២ បន្ទាត់ ⭐)
```css
.parent {
  display: grid;
  place-items: center; /* កណ្តាលទាំងសងខាងស្វ័យប្រវត្តិ */
  height: 300px;
}
```

---

### វិធីទី ៣៖ ប្រើប្រាស់ Absolute Positioning + Transform (វិធីបុរាណ)
```css
.parent {
  position: relative;
  height: 300px;
}

.child {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Centering Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
      padding: 30px;
    }

    /* Grid Centering Box */
    .grid-center-container {
      display: grid;
      place-items: center;
      height: 220px;
      background-color: #0f172a;
      border-radius: 10px;
      margin-bottom: 20px;
    }

    .centered-box {
      background-color: #ffffff;
      padding: 20px 40px;
      border-radius: 8px;
      text-align: center;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>

  <div class="grid-center-container">
    <div class="centered-box">
      <h3>ចំកណ្តាលទាំងស្រុង!</h3>
      <p>បង្កើតដោយ <code>display: grid; place-items: center;</code></p>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ជ្រើសរើស Flexbox ឬ Grid ជានិច្ច:** ឈប់ប្រើវិធីស្មុគស្មាញដូចជា Table-cell ឬ Float សម្រាប់ Centering ទៀតហើយ។ Flexbox (`justify-content: center; align-items: center;`) និង Grid (`place-items: center;`) គឺស្អាត និងទាន់សម័យបំផុត។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Container មួយមាន `height: 100vh;`។
2. ប្រើ `display: grid; place-items: center;` ដើម្បីតម្រឹមកាត Login Form មួយឱ្យនៅចំកណ្តាលអេក្រង់កុំព្យូទ័រ។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* To center text horizontally: `text-align: center;` on parent.
* To center a block element horizontally: `margin: 0 auto;` with a defined width.
* To center horizontally and vertically:
  * Method 1 (Flexbox): `display: flex; justify-content: center; align-items: center;`
  * Method 2 (Grid): `display: grid; place-items: center;`
  * Method 3 (Absolute): `position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);`
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ២៤៖ ធាតុប្លង់ Inline-Block (CSS Inline-Block Layout)](24-inline-block.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ២៦៖ ការផ្គុំ Selectors (CSS Combinators) ➡️](26-combinators.md) |
