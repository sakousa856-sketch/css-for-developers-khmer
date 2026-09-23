# មេរៀនទី ៦០៖ មុខងារទំនើបៗនៃ Modern CSS (:has, Nesting, Container Queries)

> **Modern CSS បានវិវត្តយ៉ាងលឿនជាមួយនឹងមុខងារបដិវត្តន៍ជាច្រើនដូចជា `:has()` (The Parent Selector), Native CSS Nesting, និង Container Queries (`@container`)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្រើប្រាស់ `:has()` ដើម្បីជ្រើសរើស Parent Element
* ចេះប្រើប្រាស់ **Native CSS Nesting** ដោយមិនបាច់ពឹងផ្អែកលើ Sass/SCSS
* យល់ដឹងពី **Container Queries (`@container`)** ដែលទំនើបជាង Media Queries

---

## 👨‍👧 ១. `:has()` Selector (The Parent Selector ដ៏ល្បីល្បាញ ⭐⭐⭐)

កាលពីមុន CSS មិនអាច Select ត្រឡប់ទៅរក Parent បានឡើយ។ សព្វថ្ងៃនេះ `:has()` អនុញ្ញាតឱ្យយើងកំណត់ Style លើ Parent **អាស្រ័យលើកូនដែលនៅខាងក្នុងវា**៖

```css
/* កំណត់ Style លើ .card ណាដែលមានរូបភាព <img> នៅខាងក្នុង */
.card:has(img) {
  padding-top: 0;
}

/* ប្តូរពណ៌ Form ពេលមាន Input មិនត្រឹមត្រូវ (:invalid) */
form:has(input:invalid) {
  border-color: #ef4444;
}

/* ប្តូរ Dark Background លើទំព័រពេល Checkbox ត្រូវបានធីក */
body:has(#dark-mode-toggle:checked) {
  background-color: #0f172a;
  color: white;
}
```

---

## 🪆 ២. Native CSS Nesting (ការសរសេរកូដទ្រុឌគ្នាក្នុង Standard CSS)

សព្វថ្ងៃនេះ Browsers ទាំងអស់គាំទ្រ CSS Nesting ផ្ទាល់ដោយមិនបាច់ប្រើ Sass / Preprocessor ឡើយ៖

```css
.card {
  background: white;
  padding: 20px;
  border-radius: 8px;

  /* កូនខាងក្នុង (ដូចក្នុង Sass) */
  & h3 {
    color: #2563eb;
    margin-top: 0;
  }

  & p {
    color: #64748b;
  }

  /* Hover State */
  &:hover {
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  }
}
```

---

## 📦 ៣. Container Queries (`@container` - អនាគតនៃ Component Design)

* **Media Queries (`@media`):** ពិនិត្យមើលតែទំហំ **អេក្រង់ Browser ទាំងមូល (Viewport)**។
* **Container Queries (`@container`):** ពិនិត្យមើលទំហំ **Parent Container ផ្ទាល់របស់ Component**! ធ្វើឱ្យ Component មួយអាចប្រើបានទាំងក្នុង Sidebar ចង្អៀត (Stack 1 col) និងក្នុង Main Area ទូលាយ (3 cols) ដោយស្វ័យប្រវត្តិ។

```css
/* 1. ប្រកាស Container */
.sidebar, .main-content {
  container-type: inline-size;
}

/* 2. Responsive តាមទំហំ Container ផ្ទាល់ */
@container (min-width: 400px) {
  .user-card {
    display: flex;
    flex-direction: row;
  }
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Modern CSS Features Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    /* Native CSS Nesting */
    .feature-box {
      background: white;
      padding: 24px;
      border-radius: 12px;
      border: 2px solid #e2e8f0;
      max-width: 400px;
      margin-bottom: 20px;
      transition: all 0.3s;

      /* :has() Selector: បើមាន Checkbox checked ខាងក្នុង នោះប្រអប់ទាំងមូលប្តូរពណ៌ */
      &:has(input:checked) {
        border-color: #10b981;
        background-color: #ecfdf5;
      }

      & h3 {
        margin-top: 0;
        color: #0f172a;
      }
    }
  </style>
</head>
<body>

  <h2>Modern CSS: :has() &amp; Native Nesting</h2>

  <div class="feature-box">
    <h3>មុខងារចុះឈ្មោះចូលរួម</h3>
    <label>
      <input type="checkbox"> ខ្ញុំយល់ព្រមតាមលក្ខខណ្ឌទាំងអស់
    </label>
    <p>សាកល្បងចុចធីកលើ Checkbox ដើម្បីឃើញ Parent Box ប្តូរពណ៌តាមរយៈ <code>:has(input:checked)</code>!</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Modern Baseline:** `:has()` និង Native CSS Nesting ត្រូវបានគាំទ្រជាផ្លូវការលើ 100% នៃ Modern Browsers ចាប់តាំងពីចុងឆ្នាំ 2023 មកម្ល៉េះ ដូច្នេះអ្នកអាចយកមកប្រើប្រាស់ក្នុង Production Projects បានដោយទំនុកចិត្ត។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. សរសេរ CSS ដោយប្រើ `:has()` ដើម្បីប្តូរស៊ុម `border-color` នៃប្រអប់ Card នៅពេលដែលប៊ូតុងខាងក្នុងវាត្រូវបាន `:hover` (`.card:has(button:hover)`)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `:has()` relational pseudo-class represents an element if any of the relative selectors match when anchored against the element (the CSS "parent selector").
* Native CSS Nesting allows nesting rules inside each other using the `&` nesting selector without build tools.
* Container Queries (`@container`) enable responsive components based on the size of their parent container rather than the viewport.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>60</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៦០</strong> នៃ <strong>៦០</strong></p>

| [← Prev](59-css-variables.md) | [01](01-introduction.md) | ... | [56](56-tooltips-and-modals.md) | [57](57-filter-effects.md) | [58](58-glassmorphism.md) | [59](59-css-variables.md) | **[ 60 ]** | [Next 🏆](../projects/01-modern-personal-portfolio/index.html) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
