# មេរៀនទី ០៤៖ ការដាក់ចំណាំក្នុង CSS (CSS Comments)

> **CSS Comments ប្រើសម្រាប់ពន្យល់កូដ និងរៀបចំ Section ឱ្យងាយស្រួលអាន ដោយ Browser មិនដំណើរការឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះ Syntax នៃការសរសេរ CSS Comments
* ចេះវិធីបិទកូដបណ្តោះអាសន្ន (Commenting out code) ពេល Debug
* ចេះរៀបចំ Section Header ក្នុងឯកសារ CSS តាមស្តង់ដារ Developer

---

## ✍️ Syntax នៃ CSS Comments

CSS Comment ចាប់ផ្តើមដោយ `/*` ហើយបញ្ចប់ដោយ `*/`៖

```css
/* នេះគឺជា Single-line Comment */
p {
  color: #3b82f6; /* កំណត់ពណ៌អក្សរខៀវ */
}

/*
  នេះគឺជា Multi-line Comment
  អាចសរសេរបានច្រើនបន្ទាត់
  សម្រាប់ពន្យល់ Block កូដវែងៗ
*/
.card {
  background-color: #ffffff;
  padding: 20px;
}
```

---

## 🛠️ ការប្រើប្រាស់ជាក់ស្តែង (Practical Usage)

### ១. រៀបចំ Section ក្នុងឯកសារ CSS (Structuring CSS)
នៅពេល file CSS ចាប់ផ្តើមវែង Developers តែងប្រើ Comments ដើម្បីបែងចែកតំបន់កូដ៖

```css
/* ==========================================================================
   # BASE & RESET STYLES
   ========================================================================== */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ==========================================================================
   # NAVIGATION BAR
   ========================================================================== */
.navbar {
  display: flex;
  justify-content: space-between;
  background-color: #0f172a;
}

/* ==========================================================================
   # HERO SECTION
   ========================================================================== */
.hero {
  padding: 60px 20px;
  text-align: center;
}
```

### ២. បិទកូដបណ្តោះអាសន្នពេល Debug (Debugging)
```css
.button {
  background-color: #10b981;
  color: white;
  /* border: 2px solid red; */ /* បិទ border នេះសិនដើម្បីតេស្ត */
}
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំប្រើ `//` ក្នុង CSS:** សញ្ញា `//` គឺសម្រាប់ JavaScript/C++ មិនមែនជា Valid Syntax ក្នុង Standard CSS ឡើយ។
* ❌ **ហាមដាក់ Comment ជាន់គ្នា (Nested comments):** `/* comment /* nested */ */` នឹងបង្កឱ្យមាន Syntax Error ព្រោះ Browser ចាត់ទុក `*/` ដំបូងជាការបិទ Comment។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត file `style.css` រួចសរសេរ Comment បែងចែក ២ ផ្នែកគឺ `/* 1. Header Styles */` និង `/* 2. Footer Styles */`។
2. សរសេរ CSS rule មួយ ហើយ Comment បិទ Property `font-size` របស់វា។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS comments are placed inside the `<style>` element, or in an external `.css` file.
* CSS comments start with `/*` and end with `*/`.
* Comments are ignored by browsers and do not affect the rendering.
* `//` is NOT a valid comment syntax in pure standard CSS.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ០៣៖ របៀបភ្ជាប់ CSS ទៅកាន់ HTML (How to Add CSS)](03-how-to-add-css.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ០៥៖ ការប្រើប្រាស់ពណ៌ក្នុង CSS (CSS Colors) ➡️](05-colors.md) |
