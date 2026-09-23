# មេរៀនទី ២៦៖ ការផ្គុំ Selectors (CSS Combinators)

> **CSS Combinator គឺជាសញ្ញាដែលពន្យល់ពីទំនាក់ទំនងរវាង Selectors ពីរ ឬច្រើន (ដូចជា មេ-កូន, បងប្អូន)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ស្គាល់ ៤ ប្រភេទនៃ CSS Combinators
* យល់ច្បាស់ពីភាពខុសគ្នារវាង **Descendant (` `)** និង **Direct Child (`>`)**
* ចេះប្រើប្រាស់ **Adjacent Sibling (`+`)** និង **General Sibling (`~`)**

---

## 🔗 Combinators ទាំង ៤ ប្រភេទក្នុង CSS

| Combinator | ឈ្មោះ (Name) | ឧទាហរណ៍ | ការពន្យល់ |
| :---: | :--- | :--- | :--- |
| *(ដកឃ្លា)* | **Descendant Selector** | `div p` | រើសរាល់ `<p>` ទាំងអស់ដែលនៅ **ខាងក្នុង** `<div>` (ទោះជាកូន ឬចៅជ្រៅប៉ុណ្ណាក៏ដោយ) |
| `>` | **Child Selector** | `div > p` | រើសយកតែ `<p>` ណាដែលជា **កូនផ្ទាល់ (Direct Child)** របស់ `<div>` ប៉ុណ្ណោះ |
| `+` | **Adjacent Sibling** | `h2 + p` | រើសយកតែ `<p>` ណាដែលនៅ **បន្ទាប់ភ្លាមៗជាប់** ពីក្រោយ `<h2>` តែមួយគត់ |
| `~` | **General Sibling** | `h2 ~ p` | រើសយក `<p>` ទាំងអស់ដែលជា **បងប្អូនស្ថិតនៅក្រោយ** `<h2>` |

---

## 🔍 ការប្រៀបធៀបជាក់ស្តែង

### ១. `div p` (Descendant) ទល់នឹង `div > p` (Child)

```html
<div>
  <p>កថាខណ្ឌទី 1 (Direct Child)</p>
  <section>
    <p>កថាខណ្ឌទី 2 (Grandchild - កូនរបស់ section)</p>
  </section>
</div>
```

* `div p { color: red; }` ➔ ទាំងកថាខណ្ឌទី 1 និងទី 2 ចេញពណ៌ក្រហមទាំងអស់។
* `div > p { color: blue; }` ➔ **មានតែកថាខណ្ឌទី 1 មួយគត់** ដែលចេញពណ៌ខៀវ (ព្រោះកថាខណ្ឌទី 2 គឺជាកូនរបស់ `<section>` មិនមែនជាកូនផ្ទាល់របស់ `<div>` ឡើយ)។

---

### ២. `h2 + p` (Adjacent Sibling)
រើសតែ element បន្ទាប់ជាប់បង្កើយ៖
```css
/* កំណត់ទំហំអក្សរធំលើកថាខណ្ឌដំបូងបង្អស់ក្រោមចំណងជើង */
h2 + p {
  font-size: 18px;
  font-weight: 500;
  color: #1e293b;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Combinators Demo</title>
  <style>
    /* Direct Child: Only direct li inside .menu */
    .menu > li {
      display: inline-block;
      margin-right: 15px;
      font-weight: bold;
    }

    /* Adjacent Sibling: The first paragraph right after h2 */
    h2 + p {
      color: #2563eb;
      font-style: italic;
    }
  </style>
</head>
<body>

  <h2>ចំណងជើងអត្ថបទ</h2>
  <p>កថាខណ្ឌនេះនៅជាប់ភ្លាមក្រោម h2 ដូច្នេះវានឹងចេញពណ៌ខៀវទ្រេត (h2 + p)។</p>
  <p>កថាខណ្ឌធម្មតាទីពីរ។</p>

  <ul class="menu">
    <li>ទំព័រដើម</li>
    <li>
      សេវាកម្ម
      <ul>
        <li>Web Design (មិនមែន direct child នៃ .menu ឡើយ)</li>
      </ul>
    </li>
  </ul>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ប្រើ `>` ដើម្បីកុំឱ្យ Style ធ្លាយចូលកូនៗជ្រៅពេក:** ពេលធ្វើ Nested Menus ឬ Cards គួរប្រើ `.card > .title` ជំនួសឱ្យ `.card .title` ដើម្បីការពារកុំឱ្យប៉ះពាល់ដល់ Nested Sub-components។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. សរសេរ CSS Rule ដោយប្រើ `h1 + p` ដើម្បីកំណត់អក្សរធំ (`font-size: 1.2rem;`) លើកថាខណ្ឌសេចក្តីផ្តើម (Lead Paragraph) ក្រោម `<h1>`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Descendant selector (`space`): matches all elements that are descendants of a specified element.
* Child selector (`>`): matches all elements that are direct children of a specified element.
* Adjacent sibling selector (`+`): matches the element directly after a specific element.
* General sibling selector (`~`): matches all elements that are siblings of a specified element.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ២៥៖ ការតម្រឹមធាតុចំកណ្តាល (CSS Alignment)](25-align.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ២៧៖ ស្លាកក្លែងក្លាយ (CSS Pseudo-classes) ➡️](27-pseudo-classes.md) |
