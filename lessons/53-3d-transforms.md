# មេរៀនទី ៥៣៖ ការបំប្លែងរូបរាង 3D (CSS 3D Transforms)

> **CSS 3D Transforms អនុញ្ញាតឱ្យយើងបង្វិល និងរំកិល Elements ក្នុងលំហ ៣ វិមាត្រ (X, Y, Z) រួមជាមួយជម្រៅ Perspective។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីសារៈសំខាន់នៃ `perspective` ក្នុងការបង្កើតជម្រៅ 3D
* ចេះប្រើ `rotateX()`, `rotateY()`, `rotateZ()`
* ចេះបង្កើតចលនាត្រឡប់កាត 3D (3D Card Flip on Hover)

---

## 🕶️ សារៈសំខាន់នៃ `perspective`

![CSS 3D Coordinate Space & Transforms](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-3d-coordinates.svg)

បើគ្មាន `perspective` ទេ ការបង្វិល 3D នឹងមើលទៅរាបស្មើដូច 2D អញ្ចឹង។ `perspective: 1000px;` កំណត់ចម្ងាយពីភ្នែករបស់អ្នកមើលទៅកាន់ផ្ទាំង 3D (លេខកាន់តែតូច ជម្រៅ 3D កាន់តែខ្លាំង):

```css
.scene-3d {
  perspective: 1000px; /* ដាក់លើ Parent Container */
}
```

---

## 🎴 របៀបបង្កើត 3D Card Flip Effect (មុខ-ក្រោយ)

```css
/* 1. Parent Container */
.flip-card {
  background-color: transparent;
  width: 280px;
  height: 200px;
  perspective: 1000px;
}

/* 2. Inner Wrapper ដែលត្រូវបង្វិល 180deg */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
  transform-style: preserve-3d; /* រក្សាស្ថានភាព 3D សម្រាប់កូនៗ */
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* 3. ផ្ទាំងមុខ និងផ្ទាំងក្រោយ */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* លាក់ខ្នងពេលបែរចេញ */
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.flip-card-front {
  background: #2563eb;
  color: white;
}

.flip-card-back {
  background: #0f172a;
  color: white;
  transform: rotateY(180deg); /* បង្វិលខ្នងទុកជាមុន 180deg */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>3D Card Flip Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 50px;
      background-color: #f1f5f9;
      display: flex;
      justify-content: center;
    }

    .flip-card {
      width: 300px;
      height: 200px;
      perspective: 1000px;
      cursor: pointer;
    }

    .flip-card-inner {
      position: relative;
      width: 100%;
      height: 100%;
      text-align: center;
      transition: transform 0.6s;
      transform-style: preserve-3d;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    .flip-card:hover .flip-card-inner {
      transform: rotateY(180deg);
    }

    .flip-front, .flip-back {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
      box-sizing: border-box;
    }

    .flip-front {
      background: linear-gradient(135deg, #3b82f6, #1d4ed8);
      color: white;
    }

    .flip-back {
      background: linear-gradient(135deg, #0f172a, #1e293b);
      color: white;
      transform: rotateY(180deg);
    }
  </style>
</head>
<body>

  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-front">
        <h2>ផ្ទាំងខាងមុខ (Front)</h2>
        <p>ដាក់ Mouse លើកាតដើម្បីត្រឡប់</p>
      </div>
      <div class="flip-back">
        <h2>ផ្ទាំងខាងក្រោយ (Back)</h2>
        <p>ព័ត៌មានលម្អិតលាក់ទុក!</p>
      </div>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ភ្លេចដាក់ `backface-visibility: hidden`:** បើគ្មាន Property នេះទេ ពេលកាតបង្វិលទៅក្រោយ អ្នកនឹងនៅតែមើលឃើញអក្សរនៃផ្ទាំងមុខបញ្ច្រាសមកជាន់លើផ្ទាំងក្រោយដដែល។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត 3D Flip Card ផ្ទាល់ខ្លួនរបស់អ្នកសម្រាប់បង្ហាញ Profile Card (រូបថតនៅខាងមុខ, ជីវប្រវត្តិនៅខាងក្រោយ)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `perspective` defines how far the 3D element is placed from the viewer.
* `transform-style: preserve-3d` ensures child elements preserve their 3D positions.
* `backface-visibility: hidden` hides the back of an element when turned away from the user.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>53</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៥៣</strong> នៃ <strong>៦០</strong></p>

| [← Prev](52-2d-transforms.md) | [01](01-introduction.md) | ... | [51](51-web-fonts.md) | [52](52-2d-transforms.md) | **[ 53 ]** | [54](54-transitions.md) | [55](55-animations.md) | ... | [60](60-modern-features.md) | [Next →](54-transitions.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
