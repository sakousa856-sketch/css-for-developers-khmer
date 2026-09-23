# មេរៀនទី ២០៖ ការប្រើប្រាស់ Max-Width សម្រាប់ Container (CSS Max-width)

> **ការប្រើប្រាស់ `max-width` ជំនួសឱ្យ `width` គឺជាគ្រឹះដំបូងបំផុតក្នុងការកសាងប្លង់គេហទំព័រ Responsive។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពីមូលហេតុដែល `width` បង្កឱ្យមានបញ្ហា Horizontal Scrollbar លើ Mobile
* ចេះបង្កើត Responsive Wrapper Container ដោយប្រើ `max-width: 1200px; width: 100%; margin: 0 auto;`
* ចេះអនុវត្ត `min-width` សម្រាប់ទប់ទល់កុំឱ្យ Element រួញតូចហួសប្រមាណ

---

## 🔍 បញ្ហាពិតជាក់ស្តែង (Real-World Problem)

ឧបមាថាយើងចង់បាន Container មួយដែលមានទទឹង 800px៖

### ❌ វិធីសាស្ត្រមិនល្អ (Using fixed `width: 800px;`)
* នៅលើអេក្រង់កុំព្យូទ័រ (1920px): មើលទៅល្អធម្មតា។
* នៅលើអេក្រង់ទូរស័ព្ទ (375px): Container នឹងនៅតែទាមទារយកទំហំ 800px ដដែល ដែលបណ្តាលឱ្យ **ហៀរធ្លាយចេញក្រៅអេក្រង់ (Page Overflow)** ហើយ Browser នឹងបង្ហាញ **Horizontal Scrollbar** មិនស្អាតឡើយ។

### ✅ វិធីសាស្ត្រត្រឹមត្រូវ (Using `max-width: 800px; width: 100%;`)
* នៅលើអេក្រង់កុំព្យូទ័រ (1920px): វារីកអតិបរមាត្រឹម 800px។
* នៅលើអេក្រង់ទូរស័ព្ទ (375px): វានឹងរួញតូចមកនៅត្រឹម 100% នៃអេក្រង់ (375px) ដោយស្វ័យប្រវត្តិ មិនបង្កឱ្យមាន Overflow ឡើយ។

---

## 🏗️ រូបមន្តស្តង់ដារ Standard Container Wrapper

គ្រប់គេហទំព័រអាជីព (ដូចជា Apple, Google, Facebook) តែងមាន Container Wrapper ដូចខាងក្រោម៖

```css
.container {
  width: 100%;
  max-width: 1200px; /* ឬ 1140px / 1280px */
  margin-left: auto;
  margin-right: auto;
  padding-left: 20px;  /* ការពារកុំឱ្យអក្សរប៉ះគែមអេក្រង់ទូរស័ព្ទ */
  padding-right: 20px;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Max-Width Demo</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
    }

    .navbar {
      background-color: #0f172a;
      color: white;
      padding: 15px 0;
    }

    .container {
      width: 100%;
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 20px;
    }

    .nav-content {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .hero-section {
      background: white;
      padding: 60px 0;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <header class="navbar">
    <div class="container nav-content">
      <h2>MyBrand</h2>
      <div>Menu Items</div>
    </div>
  </header>

  <main class="container">
    <section class="hero-section">
      <h1>ប្លង់ Responsive ជាមួយ Container</h1>
      <p>Container នេះនឹងនៅចំកណ្តាលអេក្រង់កុំព្យូទ័រ និងបត់បែនស្អាតលើអេក្រង់ទូរស័ព្ទ។</p>
    </section>
  </main>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **កុំភ្លេចដាក់ Side Padding:** លើអេក្រង់ទូរស័ព្ទតូច ប្រសិនបើគ្មាន `padding: 0 16px;` ទេនោះ អក្សរនឹងទៅប៉ះផ្ទាល់នឹងកញ្ចក់គែមទូរស័ព្ទដែលពិបាកមើល។
* ❌ **កុំកំណត់ `width` ជា Fix Pixel លើ Parent Containers:** ចៀសវាង `width: 1200px;` ត្រូវប្រើ `max-width: 1200px; width: 100%;` ជានិច្ច។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class `.site-container` ដោយប្រើរូបមន្ត Standard Container ខាងលើ។
2. បើក Browser DevTools ក្នុង Mobile Mode (iPhone/Android) ហើយសាកល្បង Scroll មើលថាតើមាន Horizontal Scrollbar ឬអត់។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Setting the `width` of a block-level element will prevent it from stretching out to the edges of its container.
* Using `max-width: 100%` along with a pixel value (e.g., `max-width: 1200px`) allows the container to adapt to smaller screens without horizontal scrolling.
* `margin: 0 auto;` horizontally centers the element inside its parent container.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ១៩៖ លក្ខណៈបង្ហាញ Display (CSS Display Property)](19-display.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ២១៖ ទីតាំងនៃ Element (CSS Position & Z-Index) ➡️](21-position.md) |
