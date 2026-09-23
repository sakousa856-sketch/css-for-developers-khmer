# មេរៀនទី ០៦៖ ផ្ទៃខាងក្រោយ (CSS Backgrounds)

> **CSS Background Properties ប្រើសម្រាប់គ្រប់គ្រងពណ៌ រូបភាព ទីតាំង និងទំហំនៃផ្ទៃខាងក្រោយរបស់ Element។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះកំណត់ពណ៌ផ្ទៃខាងក្រោយ (`background-color`)
* ចេះដាក់រូបភាព Background (`background-image`)
* យល់ពី Properties សំខាន់ៗ៖ `repeat`, `position`, `size`, `attachment`
* ចេះប្រើ `background` Shorthand Property

---

## 🖼️ បណ្តា Background Properties សំខាន់ៗ

### ១. `background-color` (ពណ៌ផ្ទៃ)
កំណត់ពណ៌ផ្ទៃខាងក្រោយ៖
```css
body {
  background-color: #f1f5f9;
}
```

---

### ២. `background-image` (រូបភាពផ្ទៃ)
កំណត់រូបភាពជាផ្ទៃខាងក្រោយដោយប្រើអនុគមន៍ `url()`៖
```css
.hero {
  background-image: url("hero-banner.jpg");
}
```

---

### ៣. `background-repeat` (ការផ្ទួនរូបភាព)
តាមលំនាំដើម រូបភាព Background នឹងត្រូវ Repeat (ចម្លងតម្រៀបគ្នាទាំងបញ្ឈរ និងផ្ដេក)។ យើងអាចគ្រប់គ្រងវាបាន៖
* `no-repeat`: បង្ហាញរូបភាពតែម្តងគត់ (មិនផ្ទួនឡើយ)
* `repeat-x`: ផ្ទួនតែតាមជួរដេក (ផ្ដេក)
* `repeat-y`: ផ្ទួនតែតាមជួរឈរ (បញ្ឈរ)

```css
.card {
  background-image: url("pattern.png");
  background-repeat: no-repeat;
}
```

---

### ៤. `background-position` (ទីតាំងរូបភាព)
កំណត់ទីតាំងដែលត្រូវបង្ហាញរូបភាពក្នុង Container៖
* តម្លៃទូទៅ៖ `top left`, `top center`, `center`, `bottom right`, `50% 50%`

```css
.hero {
  background-position: center center;
}
```

---

### ៥. `background-size` (ទំហំរូបភាព)
គ្រប់គ្រងទំហំនៃរូបភាពផ្ទៃខាងក្រោយ៖
* `cover`: ពង្រីករូបភាពឱ្យពេញក្របដណ្តប់ Container ទាំងមូល (កាត់គែមរូបខ្លះដើម្បីកុំឱ្យខូចសមាមាត្រ)
* `contain`: បង្ហាញរូបភាពទាំងមូលឱ្យឃើញគ្រប់ជ្រុងជ្រោយក្នុង Container
* ឬកំណត់ទំហំជាក់លាក់ដូចជា `100% auto`, `300px 200px`

```css
.hero-section {
  background-image: url("mountain.jpg");
  background-size: cover;
}
```

---

### ៦. `background-attachment` (ការជាប់នឹងកន្លែង)
* `scroll` (Default): រូបភាពរំកិលតាមការ Scroll ទំព័រ
* `fixed`: រូបភាពជាប់នឹងកន្លែង (Parallax Effect) ទោះបីជាអ្នក Scroll ចុះក្រោមក៏ដោយ

```css
.parallax {
  background-attachment: fixed;
}
```

---

### ៧. `background` Shorthand Property
យើងអាចសរសេរ Properties ទាំងអស់រួមគ្នាក្នុងបន្ទាត់តែមួយតាមលំដាប់លំដោយ៖
`color` ➔ `image` ➔ `repeat` ➔ `attachment` ➔ `position` / `size`

```css
/* Shorthand Form */
.banner {
  background: #0f172a url("stars.png") no-repeat fixed center / cover;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Backgrounds Demo</title>
  <style>
    .hero-banner {
      height: 350px;
      background-color: #1e293b;
      /* អាចប្រើ Local path: ../assets/images/hero-bg-tech.jpg ឬ Online URL */
      background-image: url("../assets/images/hero-bg-tech.jpg");
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      border-radius: 12px;
    }

    .hero-banner h1 {
      font-size: 36px;
      background-color: rgba(0, 0, 0, 0.6);
      padding: 15px 30px;
      border-radius: 8px;
    }
  </style>
</head>
<body>

  <div class="hero-banner">
    <h1>ស្វាគមន៍មកកាន់គេហទំព័ររបស់យើង</h1>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ត្រូវដាក់ `background-color` ទុកជាមុនជានិច្ច:** ក្នុងករណីដែលរូបភាព `background-image` ផ្ទុកមិនទាន់ ឬខូច Link នោះពណ៌ `background-color` នឹងជួយរក្សាភាពងាយស្រួលអាននៃអក្សរ។
* ❌ **ប្រយ័ត្នបញ្ហាផ្លូវ File (Path Issue):** ក្នុង `url("../images/bg.jpg")` ផ្លូវរូបភាពគឺធៀបនឹងទីតាំងរបស់ **CSS File** មិនមែនធៀបនឹង HTML File ឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត class `.hero` កំណត់ `height: 300px;`។
2. ដាក់រូបភាព Background ដោយប្រើ `background-size: cover;`, `background-position: center;` និង `background-repeat: no-repeat;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `background-color` property specifies the background color of an element.
* The `background-image` property specifies an image to use as the background.
* By default, the image is repeated so it covers the entire element.
* Use `background-repeat: no-repeat` to show the image only once.
* `background-size: cover` scales the image so that the entire container is covered.
* `background-attachment: fixed` creates a fixed position background during scroll.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ០៥៖ ការប្រើប្រាស់ពណ៌ក្នុង CSS (CSS Colors)](05-colors.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ០៧៖ បន្ទាត់ព្រំដែន (CSS Borders) ➡️](07-borders.md) |
