# មេរៀនទី ៣៧៖ ទម្ងន់ និងលំដាប់អានុភាព (CSS Specificity & The Cascade)

> **CSS Specificity គឺជាក្បួនដោះស្រាយ (Algorithm) ដែល Browser ប្រើដើម្បីសម្រេចថាតើត្រូវយក CSS Rule ណាទៅបង្ហាញនៅពេលដែលមាន Rules ច្រើនជាន់គ្នាលើ Element តែមួយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពីប្រព័ន្ធពិន្ទុ Specificity Score `(a, b, c, d)`
* ចេះគណនាទម្ងន់នៃ Selectors
* យល់ដឹងពីគ្រោះថ្នាក់នៃការប្រើ `!important` និងរបៀបដោះស្រាយ Specificity War

---

## ⚖️ ឋានានុក្រមពិន្ទុ Specificity Score (The Specificity Hierarchy)

![CSS Specificity Weight](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-specificity-weight.svg)

ពិន្ទុ Specificity ត្រូវបានគណនាជា ៤ ខ្ទង់ `(a, b, c, d)`៖

| ខ្ទង់ | ប្រភេទ Selector | ពិន្ទុ | ឧទាហរណ៍ |
| :---: | :--- | :---: | :--- |
| **a** | **Inline Style** | `1, 0, 0, 0` | `style="color: red;"` |
| **b** | **ID Selector** | `0, 1, 0, 0` | `#main-header`, `#nav` |
| **c** | **Class, Attribute, Pseudo-class** | `0, 0, 1, 0` | `.btn`, `[type="text"]`, `:hover` |
| **d** | **Element & Pseudo-element** | `0, 0, 0, 1` | `h1`, `p`, `div`, `::before` |

*(ចំណាំ៖ Universal Selector `*` និង Combinators `+`, `>`, `~` មានពិន្ទុ `0, 0, 0, 0`)*

---

## 🧮 ឧទាហរណ៍នៃការគណនាពិន្ទុ

1. `p` ➔ `(0, 0, 0, 1)` (ពិន្ទុ = 1)
2. `.intro` ➔ `(0, 0, 1, 0)` (ពិន្ទុ = 10)
3. `p.intro` ➔ `(0, 0, 1, 1)` (ពិន្ទុ = 11) ➔ **ឈ្នះ `.intro`**
4. `#header .menu a:hover` ➔ `(0, 1, 2, 1)` (1 ID + 1 Class + 1 Pseudo + 1 Element = 121)

---

## 🚨 ច្បាប់ `!important` (The Nuclear Option)

ប្រសិនបើអ្នកបន្ថែម `!important` នៅចុងបញ្ចប់នៃ Property ណាមួយ វានឹង **Override ឈ្នះ Specificity ទាំងអស់** (សូម្បីតែ Inline Style ក៏ចាញ់វាដែរ)៖

```css
p {
  color: red !important; /* ឈ្នះទាំងអស់ */
}

#intro {
  color: blue; /* ចាញ់ red !important ទោះបីជាមាន ID ក៏ដោយ */
}
```

### ⚠️ ហេតុអ្វីបានជាត្រូវចៀសវាង `!important`?
* វាបំផ្លាញលំហូរធម្មជាតិនៃ Cascading Flow
* ធ្វើឱ្យកូដពិបាកកែសម្រួលនៅពេលក្រោយ (បង្កើត "Specificity War")
* ប្រើ `!important` តែក្នុងករណី Utility Helper Classes (ដូចជា `.hidden { display: none !important; }`) ប៉ុណ្ណោះ។

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Specificity Demo</title>
  <style>
    /* Specificity: 0, 0, 0, 1 (Score: 1) */
    p {
      color: gray;
    }

    /* Specificity: 0, 0, 1, 0 (Score: 10) */
    .highlight {
      color: blue;
    }

    /* Specificity: 0, 1, 0, 0 (Score: 100) -> ឈ្នះ! */
    #special-text {
      color: green;
    }
  </style>
</head>
<body>

  <!-- Element នេះនឹងចេញពណ៌បៃតង (green) ព្រោះ ID មានពិន្ទុ 100 ខ្ពស់ជាងគេ -->
  <p id="special-text" class="highlight">
    អត្ថបទនេះត្រូវបានអនុវត្ត Rules ទាំង ៣ ប៉ុន្តែពណ៌បៃតងនឹងឈ្នះដោយសារ Specificity ID ខ្ពស់ជាងគេ!
  </p>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **សរសេរ Selector ឱ្យខ្លីល្មម:** កុំសរសេរ Selector វែងអន្លាយដូចជា `body div.wrapper main#content article.post p.lead`។ ប្រើត្រឹម `.post-lead` គឺគ្រប់គ្រាន់ និងមានពិន្ទុ Specificity ទាប ងាយស្រួលគ្រប់គ្រង។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. គណនាពិន្ទុ Specificity នៃ Selectors ខាងក្រោម៖
   * `ul li a`
   * `ul.nav li a:hover`
   * `#sidebar .widget h3`

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Specificity determines which CSS rule is applied by the browser when multiple rules match the same element.
* Specificity hierarchy: `Inline styles` > `IDs` > `Classes/Attributes/Pseudo-classes` > `Elements/Pseudo-elements`.
* When specificity is equal, the LAST rule written in the CSS wins (Source Order).
* `!important` overrides normal specificity and should be used with extreme caution.
</details>
