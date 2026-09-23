# មេរៀនទី ២៩៖ កម្រិតថ្លា និងភាពស្រអាប់ (CSS Opacity & Transparency)

> **CSS `opacity` ប្រើសម្រាប់កំណត់កម្រិតថ្លា ឬស្រអាប់នៃ Element ទាំងមូល (រាប់ទាំងកូនៗរបស់វា)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីរបៀបប្រើ `opacity` (ពី `0.0` ដល់ `1.0`)
* យល់ច្បាស់ពីភាពខុសគ្នារវាង `opacity` និង `background-color: rgba(...)`
* ចេះបង្កើត Hover Opacity Effect លើរូបភាព និងប៊ូតុង

---

## 🔍 `opacity` ទល់នឹង `rgba()` (ចំណុចសំខាន់ដែល Developer តែងច្រឡំ)

### ១. `opacity: 0.5` (ប៉ះពាល់ទាំងកូនៗ)
នៅពេលអ្នកដាក់ `opacity` លើ Parent Container នោះ **មាតិកាកូនៗទាំងអស់ (ដូចជា អក្សរ រូបភាព ប៊ូតុង)** នឹងក្លាយជាស្រអាប់ថ្លាទៅតាមនោះទាំងអស់គ្នា ដោយមិនអាចដោះចេញបានឡើយ (Inherited visual transparency)។

```css
.card {
  opacity: 0.6; /* ទាំង Card និងអក្សរខាងក្នុង សុទ្ធតែស្រអាប់ទាំងអស់ */
}
```

---

### ២. `background-color: rgba(0, 0, 0, 0.6)` (ថ្លាតែផ្ទៃ Background)
ប្រសិនបើអ្នកចង់ឱ្យថ្លា **តែផ្ទៃខាងក្រោយប៉ុណ្ណោះ** ដោយរក្សាទុក **អក្សរ និងប៊ូតុងខាងក្នុងឱ្យនៅដិតច្បាស់ ១០០%** នោះអ្នកត្រូវប្រើ `rgba()` ជំនួសវិញ៖

```css
.card-overlay {
  background-color: rgba(15, 23, 42, 0.7); /* ថ្លាតែផ្ទៃ អក្សរនៅដិតច្បាស់ */
  color: #ffffff;
}
```

---

## 🖼️ Image Hover Opacity Effect

```css
.img-hover {
  opacity: 0.75;
  transition: opacity 0.3s ease;
  cursor: pointer;
}

.img-hover:hover {
  opacity: 1.0; /* ភ្លឺដិតច្បាស់ពេល Hover */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Opacity Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-image: url("../assets/images/hero-bg-nature.jpg");
      background-size: cover;
    }

    .container {
      display: flex;
      gap: 20px;
    }

    /* Box using opacity */
    .box-opacity {
      background-color: #000000;
      opacity: 0.6;
      color: white;
      padding: 25px;
      border-radius: 8px;
      flex: 1;
    }

    /* Box using RGBA */
    .box-rgba {
      background-color: rgba(0, 0, 0, 0.6);
      color: white;
      padding: 25px;
      border-radius: 8px;
      flex: 1;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="box-opacity">
      <h3>1. Opacity: 0.6</h3>
      <p>អក្សរនេះក៏ថ្លាស្រអាប់តាម Parent ដែរ (ពិបាកអានបន្តិច)។</p>
    </div>

    <div class="box-rgba">
      <h3>2. RGBA Background</h3>
      <p>ផ្ទៃក្រោយថ្លា តែអក្សរនេះនៅតែដិតច្បាស់ ១០០% (ងាយស្រួលអាន)!</p>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ច្បាប់មាស:** បើចង់ធ្វើ Modal Backdrop ឬ Semi-transparent Box ត្រូវប្រើ `background: rgba(...)` ជានិច្ច កុំប្រើ `opacity`។ ប្រើ `opacity` សម្រាប់តែ Image Hover ឬ Disabled Button State ប៉ុណ្ណោះ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class `.gallery-img` មាន `opacity: 0.8; transition: opacity 0.3s;`។
2. ពេល `:hover` ឱ្យឡើងដល់ `opacity: 1;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `opacity` property sets the opacity level for an element and all its children.
* The opacity-level value is in the range from `0.0` (fully transparent) to `1.0` (fully opaque).
* To make ONLY the background transparent without affecting text, use `background-color: rgba(...)` instead of `opacity`.
</details>
