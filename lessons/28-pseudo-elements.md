# មេរៀនទី ២៨៖ ធាតុក្លែងក្លាយ (CSS Pseudo-elements)

> **Pseudo-element ប្រើសម្រាប់កំណត់ Style លើផ្នែកជាក់លាក់ណាមួយនៃ Element ឬបង្កើតធាតុក្លែងក្លាយថ្មីដោយមិនបាច់បន្ថែម HTML Tag ឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីរបៀបប្រើ `::before` និង `::after` រួមជាមួយ `content: ""`
* ចេះកំណត់ Style លើអក្សរដំបូង (`::first-letter`) និងបន្ទាត់ដំបូង (`::first-line`)
* ចេះប្តូរពណ៌ពេល Highlight អត្ថបទ (`::selection`) និង Placeholder (`::placeholder`)

---

## 🪄 `::before` និង `::after` (មានឥទ្ធិពលខ្លាំងបំផុត)

`::before` និង `::after` ប្រើសម្រាប់បង្កើតធាតុក្លែងក្លាយ (Virtual elements) នៅ **ខាងមុខ** ឬនៅ **ខាងក្រោយ** មាតិកាដើមរបស់ Element៖
* **ច្បាប់ចាំបាច់:** ត្រូវតែមាន Property `content: "";` ជានិច្ច ទើបវាបង្ហាញចេញមក។

```css
/* បន្ថែម Icon នៅពីមុខចំណងជើង */
h2::before {
  content: "🔥 ";
}

/* បង្កើតបន្ទាត់តុបតែងក្រោមចំណងជើង */
.section-title {
  position: relative;
  display: inline-block;
}

.section-title::after {
  content: "";
  position: absolute;
  bottom: -6px;
  left: 0;
  width: 50%;
  height: 3px;
  background-color: #2563eb;
  border-radius: 2px;
}
```

---

## 🔤 Pseudo-elements សម្រាប់អត្ថបទ

### ១. `::first-letter` (អក្សរធំដើមកថាខណ្ឌ - Drop Cap)
```css
p.intro::first-letter {
  font-size: 200%;
  font-weight: bold;
  color: #2563eb;
  float: left;
  margin-right: 8px;
}
```

---

### ២. `::selection` (ពណ៌ពេល User Highlight អក្សរ)
```css
::selection {
  background-color: #2563eb;
  color: #ffffff;
}
```

---

### ៣. `::placeholder` (ពណ៌អក្សរជំនួយក្នុង Input)
```css
input::placeholder {
  color: #94a3b8;
  font-style: italic;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Pseudo-elements Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    /* Custom Selection Highlight */
    ::selection {
      background-color: #fde047;
      color: #0f172a;
    }

    /* Animated Underline on Title */
    .title-styled {
      position: relative;
      display: inline-block;
      color: #0f172a;
      margin-bottom: 20px;
    }

    .title-styled::after {
      content: "";
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 60px;
      height: 4px;
      background-color: #3b82f6;
      border-radius: 2px;
    }

    /* Drop Cap Paragraph */
    .story-paragraph::first-letter {
      font-size: 32px;
      font-weight: bold;
      color: #3b82f6;
      float: left;
      line-height: 1;
      margin-right: 6px;
    }
  </style>
</head>
<body>

  <h2 class="title-styled">លក្ខណៈពិសេសនៃ CSS</h2>

  <p class="story-paragraph">
    កាលពីដើមឡើយ ការបង្កើតបន្ទាត់ ឬ Icon តុបតែងទាមទារឱ្យមានការបន្ថែម HTML tag បន្ថែម។ សព្វថ្ងៃនេះ Pseudo-elements ជួយឱ្យកូដ HTML ស្អាត និងផ្ទេរការតុបតែងទាំងអស់មក CSS។
  </p>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ភ្លេចដាក់ `content: ""`:** បើគ្មាន Property `content` ទេ នោះ `::before` និង `::after` នឹងមិនបង្ហាញខ្លួនដាច់ខាត។
* ❌ **`::before` និង `::after` មិនដំណើរការលើ Void elements:** ដូចជា `<img>`, `<input>`, `<br>` មិនអាចដាក់ `::before/::after` បានទេ ព្រោះពួកវាមិនមាន Content បើកបិទ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. ប្រើ `::selection` ដើម្បីប្តូរពណ៌ Highlight អត្ថបទក្នុងទំព័រឱ្យចេញពណ៌បៃតង (`#10b981`) និងអក្សរស។
2. បង្កើតបន្ទាត់ក្រោមចំណងជើងដោយប្រើ `.heading::after`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Pseudo-elements are used to style specified parts of an element.
* Syntax uses a double colon `::` (e.g. `::before`, `::after`, `::first-letter`, `::selection`).
* `::before` and `::after` insert virtual content before or after the element's content; they REQUIRE the `content` property.
* Replaced/void elements like `<img>` or `<input>` cannot have `::before` or `::after`.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>28</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>២៨</strong> នៃ <strong>៦០</strong></p>

| [← Prev](27-pseudo-classes.md) | [01](01-introduction.md) | ... | [26](26-combinators.md) | [27](27-pseudo-classes.md) | **[ 28 ]** | [29](29-opacity.md) | [30](30-navigation-bars.md) | ... | [60](60-modern-features.md) | [Next →](29-opacity.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
