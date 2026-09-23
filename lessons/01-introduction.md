# មេរៀនទី ០១៖ សេចក្តីណែនាំអំពី CSS (CSS Introduction)

> **CSS (Cascading Style Sheets) គឺជាភាសាសម្រាប់កំណត់ស្ទីល និងសោភ័ណភាពនៃឯកសារ HTML។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីនិយមន័យ និងតួនាទីរបស់ **CSS**
* យល់ពីទំនាក់ទំនងរវាង **HTML, CSS និង JavaScript**
* ដឹងពីអត្ថប្រយោជន៍ចម្បងៗក្នុងការប្រើប្រាស់ CSS សម្រាប់ Web Development

---

## 🎭 តួនាទីរវាង HTML, CSS និង JavaScript (The Web Trio Analogy)

ដើម្បីងាយយល់ពីតួនាទីរបស់ CSS យើងអាចប្រៀបធៀបការបង្កើតគេហទំព័រទៅនឹងការសាងសង់ផ្ទះ ឬរាងកាយមនុស្ស៖

* 🦴 **HTML (The Skeleton - គ្រោងឆ្អឹង):** បង្កើតរចនាសម្ព័ន្ធ និងមាតិកា (Headings, Paragraphs, Images, Buttons)។
* 👕 **CSS (The Skin & Clothes - ស្បែក និងសម្លៀកបំពាក់):** កំណត់ពណ៌ ផ្ទៃខាងក្រោយ ពុម្ពអក្សរ គម្លាត ប្លង់ (Layouts) និងចលនា (Animations) ឱ្យស្រស់ស្អាត។
* 🧠 **JavaScript (The Brain - ខួរក្បាល):** គ្រប់គ្រង Logic និងអន្តរកម្មឆ្លើយតបជាមួយអ្នកប្រើប្រាស់ (Interactivity & Events)។

---

## ១. CSS ជាអ្វី? (What is CSS?)

* **CSS** តំណាងឱ្យ **Cascading Style Sheets**
* **Style Sheets:** ឯកសារដែលផ្ទុកបញ្ជី Rules សម្រាប់កំណត់រូបរាងរបស់ HTML elements
* **Cascading:** សំដៅលើលំដាប់អានុភាព (Waterfall flow) នៃ Rules ដែលត្រូវយកមកអនុវត្តលើ element នីមួយៗតាមឋានានុក្រម Specificity និងលំដាប់កូដ

![CSS Syntax Anatomy](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-syntax-anatomy.svg)

---

## ២. ឧទាហរណ៍កូដដំបូង (First CSS Example)

ខាងក្រោមនេះជាកូដ HTML រួមជាមួយ CSS ដែលកំណត់ពណ៌ផ្ទៃខាងក្រោយ និងពណ៌អក្សរ៖

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS First Example</title>
  <style>
    body {
      background-color: #f0f4f8;
      font-family: Arial, sans-serif;
    }

    h1 {
      color: #1e3a8a;
      text-align: center;
    }

    p {
      color: #334155;
      font-size: 16px;
      line-height: 1.6;
    }
  </style>
</head>
<body>

  <h1>ស្វាគមន៍មកកាន់ការរៀន CSS</h1>
  <p>CSS ជួយឱ្យគេហទំព័ររបស់អ្នកមានភាពទាក់ទាញ និងស្រស់ស្អាត។</p>

</body>
</html>
```

### ការពន្យល់ដំណើរការកូដ (Code Breakdown):
* `body { ... }`: កំណត់ពណ៌ផ្ទៃខាងក្រោយ (`background-color`) នៃទំព័រទាំងមូលឱ្យមានពណ៌ប្រផេះស្រាល `#f0f4f8` និងពុម្ពអក្សរ `Arial`។
* `h1 { ... }`: កំណត់ពណ៌ចំណងជើងធំឱ្យចេញពណ៌ខៀវចាស់ `#1e3a8a` និងតម្រឹមឱ្យនៅចំកណ្តាល (`text-align: center`)។
* `p { ... }`: កំណត់ពណ៌កថាខណ្ឌ ព្រមទាំងទំហំអក្សរ `16px` និងគម្លាតបន្ទាត់ `1.6`។

---

## ៣. ហេតុអ្វីបានជាត្រូវប្រើប្រាស់ CSS? (Why Use CSS?)

1. **ដោះស្រាយបញ្ហាធំរបស់ HTML:** កាលពីជំនាន់ HTML 3.2 គេត្រូវប្រើ tag ដូចជា `<font>` ឬ `color` attribute នៅគ្រប់ element ដែលធ្វើឱ្យកូដស្មុគស្មាញ និងពិបាកកែសម្រួល។ CSS ជួយបំបែក **Structure (HTML)** ចេញពី **Presentation/Design (CSS)**។
2. **សន្សំសំចៃពេលវេលា (Saves Time):** យើងអាចបង្កើត External CSS file តែមួយ ហើយភ្ជាប់ទៅកាន់ទំព័រ HTML រាប់រយទំព័រ។ ពេលចង់ប្តូរ Design គ្រាន់តែកែ file CSS នោះមួយកន្លែងជាការស្រេច។
3. **គាំទ្រ Responsive Design:** CSS អនុញ្ញាតឱ្យគេហទំព័រអាចបត់បែនតាមទំហំអេក្រង់គ្រប់ប្រភេទដូចជា Smart Phone, Tablet, Laptop, និង Desktop Monitors។

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំសរសេរ Style លាយក្នុង HTML ផ្ទាល់ (Inline Styles):** ការប្រើ `style="..."` ច្រើនធ្វើឱ្យកូដពិបាក Maintain និងកែប្រែនៅពេលក្រោយ។
* ✅ **ប្រើ External Stylesheet:** គួររៀបចំ file `.css` ដាច់ដោយឡែកជានិច្ចសម្រាប់ Project ជាក់ស្តែង។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត file មួយឈ្មោះ `index.html`។
2. បន្ថែម `<style>` tag ក្នុងផ្នែក `<head>`។
3. កំណត់ឱ្យ `body` មាន `background-color: lightyellow;` និង `h1` មាន `color: darkgreen;` ព្រមទាំង `text-align: center;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS stands for Cascading Style Sheets.
* CSS describes how HTML elements are to be displayed on screen, paper, or in other media.
* CSS saves a lot of work. It can control the layout of multiple web pages all at once.
* External stylesheets are stored in CSS files.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| 🛑 *ចំណុចចាប់ផ្តើម* | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ០២៖ ទម្រង់កូដ និង Selectors មូលដ្ឋាន (CSS Syntax & Selectors) ➡️](02-syntax-and-selectors.md) |
