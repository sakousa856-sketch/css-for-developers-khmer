# មេរៀនទី ៤៩៖ ស្រមោល និងជ្រុងមូល (Rounded Corners & Box Shadows)

> **CSS `box-shadow` ជួយបង្កើតជម្រៅ (Elevation & Depth) ធ្វើឱ្យ Elements មើលទៅអណ្តែតលើទំព័រប្រៀបដូចជាស្រទាប់ក្រដាសពិតប្រាកដ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពី ៥ តម្លៃនៃ `box-shadow`: X-offset, Y-offset, Blur, Spread, Color
* ចេះបង្កើតស្រមោលខាងក្នុង (`inset`)
* ចេះបង្កើត **Modern Layered Soft Shadows** ដែលក្រុមហ៊ុនធំៗដូចជា Stripe / Apple ប្រើប្រាស់

---

## 🌑 Syntax នៃ `box-shadow`

```css
box-shadow: [offset-x] [offset-y] [blur-radius] [spread-radius] [color] [inset];
```

* **offset-x:** រំកិលស្រមោលទៅស្តាំ (+) ឬឆ្វេង (-)
* **offset-y:** រំកិលស្រមោលចុះក្រោម (+) ឬឡើងលើ (-)
* **blur-radius:** កម្រិតព្រាលបែកផ្សែង (លេខកាន់តែធំ កាន់តែព្រាល)
* **spread-radius:** កម្រិតរីកធំ ឬរួញតូចនៃស្រមោល
* **color:** ពណ៌ស្រមោល (និយមប្រើ `rgba(0,0,0,0.08)` ឱ្យទន់ភ្នែក)
* **inset:** បង្កើតស្រមោលចូលខាងក្នុងប្រអប់ (Inner Shadow)

---

## 🎨 Modern Layered Soft Shadow (ស្រមោលកម្រិត Premium)

ជំនួសឱ្យការប្រើស្រមោលខ្មៅក្រាស់មួយជាន់ Developers តែងប្រើស្រមោល **ពីរជាន់ស្រាលៗ (Multi-layer shadows)**៖

```css
/* Card Elevation ធម្មតា */
.modern-card {
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.05),
    0 10px 15px -3px rgba(0, 0, 0, 0.08);
  transition: box-shadow 0.3s ease, transform 0.3s ease;
}

/* Card Elevation ពេល Hover */
.modern-card:hover {
  transform: translateY(-4px);
  box-shadow: 
    0 4px 6px rgba(0, 0, 0, 0.05),
    0 20px 25px -5px rgba(0, 0, 0, 0.12);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Shadows Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 40px;
      background-color: #f1f5f9;
      display: flex;
      gap: 30px;
      justify-content: center;
    }

    .card {
      width: 260px;
      padding: 24px;
      background: white;
      border-radius: 16px;
      text-align: center;
    }

    /* Standard Shadow */
    .shadow-soft {
      box-shadow: 0 10px 25px -5px rgba(15, 23, 42, 0.1);
    }

    /* Inset Inner Shadow */
    .shadow-inset {
      box-shadow: inset 0 2px 6px rgba(0, 0, 0, 0.15);
      background-color: #f8fafc;
    }

    /* Colored Glow Shadow */
    .shadow-glow {
      box-shadow: 0 8px 20px rgba(37, 99, 235, 0.35);
      background: linear-gradient(135deg, #2563eb, #1d4ed8);
      color: white;
    }
  </style>
</head>
<body>

  <div class="card shadow-soft">
    <h3>Soft Elevation</h3>
    <p>ស្រមោលទន់ភ្នែកបែបទំនើប</p>
  </div>

  <div class="card shadow-inset">
    <h3>Inset Shadow</h3>
    <p>ស្រមោលលិចចូលខាងក្នុង</p>
  </div>

  <div class="card shadow-glow">
    <h3>Glow Shadow</h3>
    <p>ស្រមោលបញ្ចេញពន្លឺពណ៌ខៀវ</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **កុំប្រើ `box-shadow: 5px 5px 5px #000;` ខ្មៅដិត:** ស្រមោលខ្មៅសុទ្ធ 100% មើលទៅហួសសម័យ។ ត្រូវប្រើ `rgba(0, 0, 0, 0.05)` ដល់ `rgba(0, 0, 0, 0.15)` ជានិច្ចដើម្បីឱ្យ UI មើលទៅស្រាលទន់ និងស៊ីវិល័យ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Button មួយដែលមាន Colored Glow Shadow (`box-shadow: 0 4px 14px rgba(16, 185, 129, 0.4);`)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `box-shadow` property attaches one or more shadows to an element.
* Syntax: `offset-x offset-y blur-radius spread-radius color inset`.
* Use semi-transparent colors (`rgba()`) for modern, subtle, and realistic shadows.
* Multiple shadows can be combined using comma separation.
</details>
