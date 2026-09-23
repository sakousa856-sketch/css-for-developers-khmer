# មេរៀនទី ៤៥៖ RWD: Viewport Meta Tag & Fluid Layouts

> **Responsive Web Design (RWD) គឺជាការរចនាគេហទំព័រដែលធ្វើឱ្យ Layout និង Content អាចបត់បែន និងបង្ហាញរូបរាងស្អាតឥតខ្ចោះនៅលើគ្រប់ទំហំឧបករណ៍ (Smart Phone, Tablet, Laptop, Desktop)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពីសារៈសំខាន់នៃ `<meta name="viewport">`
* យល់ពីគ្រោះថ្នាក់នៃការបាត់បង់ Viewport Meta Tag
* ចេះបង្កើត **Fluid Grids** និងការប្រើប្រាស់ភាគរយ (%) ជំនួស Pixel (px) ថេរ

---

## 📱 សារៈសំខាន់នៃ Viewport Meta Tag (ជំហានទី ១ ចាំបាច់បំផុត)

បើគ្មានបន្ទាត់កូដនេះទេ Mobile Browsers (ដូចជា Safari លើ iPhone ឬ Chrome លើ Android) នឹងគិតថាគេហទំព័ររបស់អ្នកជា Desktop Site ហើយធ្វើការ **Zoom Out អក្សរតូចល្អិត** ធ្វើឱ្យពិបាកអានជាទីបំផុត។

```html
<!-- ត្រូវតែដាក់ក្នុង <head> នៃគ្រប់ HTML file ជានិច្ច -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### ការពន្យល់អំពី Attributes:
* `width=device-width`: កំណត់ឱ្យទទឹងទំព័រស្មើនឹងទទឹងអេក្រង់ឧបករណ៍ពិតប្រាកដ (Screen width)
* `initial-scale=1.0`: កំណត់កម្រិត Zoom ដំបូងស្មើ 100% នៅពេលទំព័រទើប Load ចប់

---

## 🌊 គំនិត Fluid Grids (ប្លង់រាវបត់បែន)

ជំនួសឱ្យការប្រើប្រាស់ទំហំ Pixel ជាប់គាំង (`width: 960px;`) យើងត្រូវប្រើ **ខ្នាតភាគរយ Relative Units** (`width: 100%;`, `max-width: 1200px;`) ដើម្បីឱ្យប្លង់អាចរួញ ឬពង្រីកតាមទំហំអេក្រង់បានដោយរលូន៖

```css
.column-left {
  width: 70%;
  float: left;
}

.column-right {
  width: 30%;
  float: right;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <!-- Viewport Meta Tag ចាំបាច់ -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Viewport Demo</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: #f8fafc;
    }

    .responsive-card {
      width: 100%;
      max-width: 800px;
      margin: 0 auto;
      background: white;
      padding: 24px;
      border-radius: 8px;
      border: 1px solid #cbd5e1;
    }
  </style>
</head>
<body>

  <div class="responsive-card">
    <h2>គេហទំព័រ Responsive</h2>
    <p>សូមបើកមើលលើទូរស័ព្ទដៃ ឬប្រើ Chrome DevTools ដើម្បីឃើញពីរបៀបដែលទំព័រនេះបត់បែនតាមទំហំអេក្រង់យ៉ាងរលូន។</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំប្រើ `user-scalable=no` ឬ `maximum-scale=1` ក្នុង Viewport:** ការហាមឃាត់អ្នកប្រើប្រាស់មិនឱ្យ Zoom អេក្រង់ គឺជាការបំពានស្តង់ដារ Accessibility (A11y) សម្រាប់អ្នកដែលមានបញ្ហាគំហើញភ្នែក។
* ❌ **កុំប្រើ Element ណាដែលមាន `width` ធំជាងទទឹង Viewport:** ឧទាហរណ៍ រូបភាពទំហំ `width: 1200px` នឹងបណ្តាលឱ្យទូរស័ព្ទមាន Horizontal Scrollbar។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតឯកសារ HTML ថ្មីមួយដោយភ្លេចដាក់ `<meta name="viewport">` រួចបើកមើលលើទូរស័ព្ទ។
2. បន្ទាប់មកបន្ថែម `<meta name="viewport" content="width=device-width, initial-scale=1.0">` ចូលវិញ ហើយសង្កេតមើលភាពខុសគ្នាដ៏អស្ចារ្យ។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Responsive Web Design makes web pages look good on all devices.
* The viewport is the user's visible area of a web page.
* Always include `<meta name="viewport" content="width=device-width, initial-scale=1.0">` in all web pages.
* Do not use large fixed-width elements; use relative width values like percentages.
</details>
