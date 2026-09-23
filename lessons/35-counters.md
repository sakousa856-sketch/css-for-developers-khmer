# មេរៀនទី ៣៥៖ ការរាប់លេខស្វ័យប្រវត្តិ (CSS Counters)

> **CSS Counters គឺជាអថេររាប់លេខស្វ័យប្រវត្តិកំណត់ដោយ CSS ដើម្បីបង្កើតលេខរៀងជំពូក ផ្នែក ឬបញ្ជីស្មុគស្មាញ (Nested Numbering)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពី Properties ទាំង ៣ នៃ CSS Counters៖ `counter-reset`, `counter-increment`, `content: counter()`
* ចេះបង្កើតលេខរៀងជំពូកស្វ័យប្រវត្តិ (ឧ. "ជំពូកទី ១:", "ជំពូកទី ២:")
* ចេះបង្កើត Nested Multi-level Numbering (ឧ. 1.1, 1.2, 1.2.1)

---

## 🔢 ជំហានទាំង ៣ ក្នុងការបង្កើត CSS Counter

1. **`counter-reset`:** បង្កើត ឬកំណត់អថេររាប់ឡើងវិញទៅ `0` (ដាក់លើ Parent Element)
2. **`counter-increment`:** បង្កើនតម្លៃលេខរាប់ +1 (ដាក់លើ Child Element)
3. **`content: counter(...)`:** បង្ហាញលេខរាប់ចេញមកក្រៅ (ប្រើក្នុង `::before`)

```css
/* 1. បង្កើត Counter ឈ្មោះ section-count */
body {
  counter-reset: section-count;
}

/* 2. បង្កើនលេខរាប់រាល់ពេលជួប <h2> */
h2 {
  counter-increment: section-count;
}

/* 3. បង្ហាញលេខរាប់នៅពីមុខ <h2> */
h2::before {
  content: "ជំពូកទី " counter(section-count) "៖ ";
  color: #2563eb;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <title>CSS Counters Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
      counter-reset: chapter; /* Reset counter */
    }

    .chapter-heading {
      counter-increment: chapter; /* Increment by 1 */
      color: #0f172a;
      margin-top: 25px;
    }

    .chapter-heading::before {
      content: "មេរៀនទី " counter(chapter, decimal-leading-zero) "៖ ";
      color: #0284c7;
      font-weight: bold;
    }

    .step-list {
      list-style: none;
      counter-reset: step-counter;
      padding-left: 0;
    }

    .step-list li {
      counter-increment: step-counter;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .step-list li::before {
      content: counter(step-counter);
      background-color: #2563eb;
      color: white;
      width: 28px;
      height: 28px;
      border-radius: 50%;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 14px;
    }
  </style>
</head>
<body>

  <h2 class="chapter-heading">សេចក្តីណែនាំអំពី CSS</h2>
  <p>ខ្លឹមសារនៃមេរៀន...</p>

  <h2 class="chapter-heading">CSS Box Model</h2>
  <p>ខ្លឹមសារនៃមេរៀន...</p>

  <h3>ជំហានអនុវត្ត (Steps):</h3>
  <ul class="step-list">
    <li>បង្កើតឯកសារ HTML</li>
    <li>ភ្ជាប់ឯកសារ CSS ខាងក្រៅ</li>
    <li>បើកមើលលទ្ធផលលើ Browser</li>
  </ul>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ដាក់ `counter-reset` ខុសកន្លែង:** បើអ្នកដាក់ `counter-reset` លើ `h2` ផ្ទាល់ នោះលេខរាប់នឹង Reset ទៅ `0` វិញរហូត (ចេញលេខ 1 រហូត)។ ត្រូវដាក់ `counter-reset` លើ **Parent Container** (ដូចជា `body` ឬ `ul`) ជានិច្ច។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតបញ្ជីជំហាន `<ol>` ដោយលុប bullet ដើមចោល ហើយប្រើ CSS Counter បង្កើតរង្វង់មូលលេខរៀងស្អាត (Numbered Circle Badges)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS counters are "variables" maintained by CSS whose values can be incremented by CSS rules.
* `counter-reset`: Creates or resets a counter on the parent.
* `counter-increment`: Increments a counter value on child elements.
* `content: counter(name)`: Inserts the generated counter value into a pseudo-element (`::before`).
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ៣៤៖ ការកំណត់ Style លើ Forms & Inputs (CSS Forms)](34-forms-styling.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ៣៦៖ ខ្នាតរង្វាស់ក្នុង CSS (CSS Units) ➡️](36-units.md) |
