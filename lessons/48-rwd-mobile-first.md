# មេរៀនទី ៤៨៖ RWD: Mobile-First Strategy & Best Practices

> **Mobile-First Design គឺជាទស្សនវិជ្ជារចនាគេហទំព័រដោយផ្តោតលើការកសាង UI សម្រាប់ទូរស័ព្ទដៃជាមុនសិន រួចទើបពង្រីក Layout ទៅកាន់ Desktop ជាបន្តបន្ទាប់។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពីភាពខុសគ្នារវាង **Mobile-First (`min-width`)** និង **Desktop-First (`max-width`)**
* យល់ពីអត្ថប្រយោជន៍លើល្បឿន Performance និង SEO
* ចេះរៀបចំ Folder & CSS Architecture តាមទម្រង់ Mobile-First

---

## 📱 Mobile-First vs 💻 Desktop-First

| លក្ខណៈ | Mobile-First (ស្តង់ដារទំនើប ⭐) | Desktop-First (វិធីសាស្ត្រចាស់) |
| :--- | :--- | :--- |
| **Media Query** | ប្រើ **`min-width`** (ឧ. `@media (min-width: 768px)`) | ប្រើ **`max-width`** (ឧ. `@media (max-width: 768px)`) |
| **លំដាប់គិត** | រចនាអេក្រង់តូច ➔ ពង្រីកធំ | រចនាអេក្រង់ធំ ➔ រួញតូច |
| **ទម្ងន់កូដលើទូរស័ព្ទ** | ស្រាល លឿន គ្មានកូដ Override ស្មុគស្មាញ | ធ្ងន់ ត្រូវ Override ដោះ Properties ចោលច្រើន |
| **Google SEO** | ត្រូវតាម **Mobile-First Indexing** របស់ Google | ពិបាក Optimize SEO |

---

## 🏗️ គំរូកូដ Mobile-First Workflow

```css
/* ==========================================================================
   1. BASE STYLES (សម្រាប់ Mobile Screens ទាំងអស់ < 640px)
   ========================================================================== */
.site-nav {
  display: flex;
  flex-direction: column; /* តម្រៀបបញ្ឈរលើ Mobile */
  gap: 10px;
}

.hero-title {
  font-size: 1.75rem;
}

.gallery-grid {
  display: grid;
  grid-template-columns: 1fr; /* 1 Column Stack លើ Mobile */
  gap: 15px;
}

/* ==========================================================================
   2. TABLET STYLES (អេក្រង់ចាប់ពី 640px ឡើងទៅ)
   ========================================================================== */
@media (min-width: 640px) {
  .gallery-grid {
    grid-template-columns: repeat(2, 1fr); /* 2 Columns */
  }

  .hero-title {
    font-size: 2.25rem;
  }
}

/* ==========================================================================
   3. DESKTOP STYLES (អេក្រង់ចាប់ពី 1024px ឡើងទៅ)
   ========================================================================== */
@media (min-width: 1024px) {
  .site-nav {
    flex-direction: row; /* ប្តូរជាជួរដេកវិញលើ Desktop */
    justify-content: space-between;
  }

  .gallery-grid {
    grid-template-columns: repeat(3, 1fr); /* 3 Columns */
  }

  .hero-title {
    font-size: 3rem;
  }
}
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **សរសេរ `min-width` តាមលំដាប់ឡើងលើជានិច្ច:** ពីតូចទៅធំ (`640px` ➔ `768px` ➔ `1024px` ➔ `1280px`)។ កុំសរសេរច្របូកច្របល់ព្រោះ Cascading Rule នឹងគណនាមិនត្រឹមត្រូវ។
* ✅ **Touch Targets (A11y):** ប៊ូតុងលើទូរស័ព្ទដៃគួរមានទំហំយ៉ាងហោចណាស់ **`44px x 44px`** ឬ `48px x 48px` ដើម្បីឱ្យម្រាមដៃ User ងាយស្រួលចុចមិនខុស។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. រៀបចំ CSS file មួយតាមទម្រង់ Mobile-First៖ Base Mobile Styles ➔ `@media (min-width: 768px)` ➔ `@media (min-width: 1024px)`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Mobile-first design is an approach where we design for the smallest screen first and progressively enhance the layout for larger viewports.
* Always use `min-width` media queries in ascending order for mobile-first CSS architecture.
* Mobile-first leads to cleaner code, faster mobile loading times, and better SEO rankings.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ៤៧៖ RWD: Responsive Images & Media](47-rwd-images-and-media.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ៤៩៖ ស្រមោល និងជ្រុងមូល (Rounded Corners & Box Shadows) ➡️](49-shadows-and-rounded.md) |
