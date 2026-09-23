# មេរៀនទី ១៣៖ ការកំណត់ទម្រង់អត្ថបទ (CSS Text Formatting)

> **CSS Text Properties ប្រើសម្រាប់គ្រប់គ្រងពណ៌ ការតម្រឹម គម្លាតបន្ទាត់ និងផលប៉ះពាល់ផ្សេងៗនៃអត្ថបទ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះតម្រឹមអត្ថបទ (`text-align`, `vertical-align`)
* ចេះកំណត់បន្ទាត់ក្រោមអត្ថបទ និងលុបបន្ទាត់ Link (`text-decoration`)
* ចេះបម្លែងអក្សរតូចធំស្វ័យប្រវត្តិ (`text-transform`)
* ចេះគ្រប់គ្រងគម្លាតអក្សរ និងបន្ទាត់ (`letter-spacing`, `line-height`, `word-spacing`)
* ចេះដាក់ស្រមោលលើអក្សរ (`text-shadow`)

---

## 📝 Text Properties សំខាន់ៗ

### ១. `text-align` (ការតម្រឹមផ្ដេក)
* `left`: តម្រឹមទៅឆ្វេង (Default សម្រាប់ភាសាអក្សរឡាតាំង/ខ្មែរ)
* `right`: តម្រឹមទៅស្តាំ
* `center`: តម្រឹមចំកណ្តាល
* `justify`: ពង្រីកឃ្លាឱ្យស្មើសងខាងសងឆ្វេងស្តាំដូចក្នុងកាសែត

```css
h1 { text-align: center; }
p  { text-align: justify; }
```

---

### ២. `text-decoration` (បន្ទាត់លម្អអត្ថបទ)
* `none`: គ្មានបន្ទាត់ (និយមប្រើលុបបន្ទាត់ក្រោម `<a>` Link)
* `underline`: គូសបន្ទាត់ពីក្រោម
* `line-through`: គូសបន្ទាត់ឆូតកាត់កណ្តាល (បង្ហាញតម្លៃបញ្ចុះតម្លៃ)

```css
a { text-decoration: none; }
.old-price { text-decoration: line-through; color: #94a3b8; }
```

---

### ③. `text-transform` (ការបម្លែងអក្សរតូចធំ)
* `uppercase`: បម្លែងជាអក្សរធំទាំងអស់ (ឧ. `HELLO WORLD`)
* `lowercase`: បម្លែងជាអក្សរតូចទាំងអស់ (ឧ. `hello world`)
* `capitalize`: ធ្វើឱ្យអក្សរដើមនៃពាក្យនីមួយៗជាអក្សរធំ (ឧ. `Hello World`)

```css
.nav-link { text-transform: uppercase; }
```

---

### ៤. `line-height` & `letter-spacing` (គម្លាតបន្ទាត់ និងអក្សរ)
* `line-height`: គម្លាតរវាងបន្ទាត់មួយទៅបន្ទាត់មួយ (គិតជាលេខគុណ ឧ. `1.6` ឬ `24px`)។ ជួយឱ្យអត្ថបទស្រួលអាន មិនណែនតឹងពេក។
* `letter-spacing`: គម្លាតរវាងតួអក្សរមួយទៅតួអក្សរមួយ (ឧ. `1px`, `0.05em`)។

```css
p {
  line-height: 1.7;        /* គម្លាតបន្ទាត់ស្តង់ដារអានស្រួល */
  letter-spacing: 0.5px;
}
```

---

### ៥. `text-shadow` (ស្រមោលអក្សរ)
ទម្រង់៖ `text-shadow: [offset-x] [offset-y] [blur-radius] [color];`

```css
h1 {
  color: #1e3a8a;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.25);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Text Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f8fafc;
      padding: 30px;
    }

    .hero-title {
      color: #0f172a;
      text-transform: uppercase;
      letter-spacing: 2px;
      text-shadow: 2px 3px 6px rgba(0,0,0,0.15);
      text-align: center;
    }

    .article-body {
      max-width: 600px;
      margin: 20px auto;
      line-height: 1.8;
      color: #334155;
      font-size: 16px;
    }

    .btn-link {
      display: inline-block;
      text-decoration: none;
      background-color: #2563eb;
      color: white;
      padding: 10px 20px;
      border-radius: 6px;
      text-transform: capitalize;
    }
  </style>
</head>
<body>

  <h1 class="hero-title">ស្វាគមន៍មកកាន់គេហទំព័រ</h1>
  <p class="article-body">
    ការកំណត់ <code>line-height</code> និង <code>letter-spacing</code> ត្រឹមត្រូវ គឺជាគន្លឹះចម្បងដែលធ្វើឱ្យ UI របស់អ្នកមានកម្រិត Professional និងងាយស្រួលអានសម្រាប់អ្នកប្រើប្រាស់។
  </p>
  <div style="text-align: center;">
    <a href="#" class="btn-link">អានអត្ថបទបន្ត</a>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Best Practice សម្រាប់ Line-Height:** គួរប្រើលេខគ្មានខ្នាត (Unitless number) ដូចជា `line-height: 1.5;` ឬ `1.6;` ព្រោះវាធ្វើការ Scaling តាមទំហំ `font-size` របស់កូនៗបានត្រឹមត្រូវ។
* ❌ **កុំប្រើ `text-shadow` ក្រាស់ពេក:** ស្រមោលក្រាស់ពេកធ្វើឱ្យពិបាកអានអក្សរ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតចំណងជើង `<h1>` មាន `text-transform: uppercase; letter-spacing: 3px;`។
2. បង្កើត `<p>` មាន `line-height: 1.75; color: #475569;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `text-align` specifies the horizontal alignment of text (`left`, `right`, `center`, `justify`).
* `text-decoration` adds or removes decorations from text (`none`, `underline`, `line-through`).
* `text-transform` controls the capitalization of text (`uppercase`, `lowercase`, `capitalize`).
* `line-height` sets the distance between lines of text (recommended: unitless `1.5` to `1.7`).
* `letter-spacing` controls the space between characters.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>13</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១៣</strong> នៃ <strong>៦០</strong></p>

| [← Prev](12-outline.md) | [01](01-introduction.md) | ... | [11](11-box-model.md) | [12](12-outline.md) | **[ 13 ]** | [14](14-fonts.md) | [15](15-icons.md) | ... | [60](60-modern-features.md) | [Next →](14-fonts.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
