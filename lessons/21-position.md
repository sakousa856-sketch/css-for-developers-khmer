# មេរៀនទី ២១៖ ទីតាំងនៃ Element (CSS Position & Z-Index)

> **CSS `position` ប្រើសម្រាប់កំណត់ទីតាំង និងឥរិយាបថរំកិលនៃ Element លើទំព័រគេហទំព័រ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ច្បាស់ពីតម្លៃទាំង ៥ នៃ `position`: `static`, `relative`, `fixed`, `absolute`, `sticky`
* ចេះប្រើ Offset Properties: `top`, `right`, `bottom`, `left`
* យល់ពីច្បាប់មាស **"Relative Parent + Absolute Child"**
* ចេះប្រើ `z-index` ដើម្បីគ្រប់គ្រងស្រទាប់លើក្រោម (Stacking Order)

---

## 📍 ប្រភេទទាំង ៥ នៃ CSS Position

![CSS Positioning Types](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-positioning-types.svg)

### ១. `position: static` (Default)
* ទីតាំងលំនាំដើមរបស់ Element ទាំងអស់តាម **Normal Document Flow**
* **មិនទទួល** `top`, `right`, `bottom`, `left` ឬ `z-index` ឡើយ

---

### ២. `position: relative`
* រំកិលចេញពី **ទីតាំងដើមរបស់វាផ្ទាល់**
* **រក្សាទុកទំហំលំហដើមដដែល** (មិនធ្វើឱ្យ Element ជុំវិញរង្គើឡើយ)
* សំខាន់បំផុត៖ ប្រើធ្វើជា **បង្គោល Anchor (Relative Parent)** សម្រាប់ Absolute Child

```css
.box {
  position: relative;
  top: 10px;  /* រំកិលចុះក្រោម 10px ធៀបនឹងកន្លែងដើម */
  left: 20px; /* រំកិលទៅស្តាំ 20px */
}
```

---

### ៣. `position: absolute` (របូតចេញពី Normal Flow)
* របូតចេញពី Normal Document Flow ទាំងស្រុង (មិនយកទំហំក្នុងទំព័រឡើយ)
* រំកិលទីតាំងធៀបទៅនឹង **Parent Element ណាដែលនៅជិតបំផុតដែលមាន `position: relative`** (បើគ្មាន Parent ទេ វានឹងធៀបទៅនឹង `<body>` នៃ Viewport)

```css
/* បង្គោល Parent */
.card {
  position: relative;
  width: 300px;
  height: 200px;
}

/* កូន Badge Absolute */
.badge {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: #ef4444;
  color: white;
}
```

---

### ៤. `position: fixed` (ជាប់នឹងកញ្ចក់អេក្រង់)
* ធៀបនឹង **Browser Viewport** ផ្ទាល់
* **នៅជាប់នឹងកន្លែងដដែលជានិច្ច** ទោះបីជាអ្នក Scroll ចុះក្រោមយ៉ាងណាក៏ដោយ
* និយមប្រើសម្រាប់៖ Fixed Navigation Bar, Floating Action Buttons (Chat/WhatsApp icon)

```css
.floating-chat-btn {
  position: fixed;
  bottom: 25px;
  right: 25px;
  z-index: 1000;
}
```

---

### ៥. `position: sticky` (កូនកាត់ Relative + Fixed)
* ដើរតួជា `relative` រហូតដល់អ្នក Scroll ដល់ចំណុចកំណត់ (ដូចជា `top: 0`) នោះវានឹង **កកជាប់នឹងកន្លែងដូច `fixed`** ភ្លាមៗ
* និយមប្រើសម្រាប់៖ Sticky Header, Table Sticky Header

```css
.sticky-header {
  position: sticky;
  top: 0;
  background-color: white;
  z-index: 100;
}
```

---

## 🥞 `z-index` (ស្រទាប់លើក្រោម Stacking Order)

![CSS Z-Index & 3D Stacking Context](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-zindex-stack.svg)

នៅពេល Elements ជាន់ពីលើគ្នា `z-index` កំណត់ថាតើ Element ណាត្រូវនៅពីលើ Element ណា (លេខកាន់តែធំ នៅលើគេបង្អស់):
* **ចំណាំសំខាន់:** `z-index` ដំណើរការបានតែលើ Elements ណាដែលមាន `position` ក្រៅពី `static` ប៉ុណ្ណោះ (`relative`, `absolute`, `fixed`, `sticky`)។

```css
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 999;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Position Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      height: 1500px; /* បង្កើតកម្ពស់ដើម្បីតេស្ត Scroll */
    }

    /* Sticky Navbar */
    .navbar {
      position: sticky;
      top: 0;
      background-color: #0f172a;
      color: white;
      padding: 15px;
      border-radius: 6px;
      z-index: 100;
    }

    /* Product Card with Absolute Badge */
    .product-card {
      position: relative; /* បង្គោល Reference Parent */
      width: 260px;
      height: 160px;
      background-color: #f1f5f9;
      border: 1px solid #cbd5e1;
      border-radius: 8px;
      padding: 20px;
      margin: 40px 0;
    }

    .sale-badge {
      position: absolute;
      top: -10px;
      right: -10px;
      background-color: #dc2626;
      color: white;
      padding: 5px 12px;
      font-size: 12px;
      font-weight: bold;
      border-radius: 20px;
    }

    /* Fixed Floating Button */
    .floating-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: #2563eb;
      color: white;
      padding: 14px 20px;
      border-radius: 50px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>

  <header class="navbar">Sticky Header (សាកល្បង Scroll មើល)</header>

  <div class="product-card">
    <div class="sale-badge">SALE 50%</div>
    <h3>ស្បែកជើងកីឡា</h3>
    <p>តម្លៃពិសេសត្រឹមតែ $25</p>
  </div>

  <div class="floating-btn">💬 Chat ជាមួយយើង</div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ភ្លេចដាក់ `position: relative` លើ Parent:** នៅពេលអ្នកដាក់ `position: absolute; top: 0;` លើកូន ប្រសិនបើ Parent គ្មាន `position: relative` ទេ នោះកូននឹងហោះទៅនៅកំពូលក្បាលទំព័រ `<body>` ខាងលើបង្អស់។
* ❌ **ប្រើ `z-index: 999999` ច្រើនកន្លែង:** គួររៀបចំ Stacking System ច្បាស់លាស់ (ឧ. Dropdown: 10, Sticky Header: 100, Modal: 1000)។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប្រអប់ Card មួយដែលមាន `position: relative;`។
2. បង្កើត Close Button (`×`) នៅជ្រុងខាងលើស្តាំដោយប្រើ `position: absolute; top: 10px; right: 10px;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `static`: Default, follows normal flow.
* `relative`: Positioned relative to its normal position.
* `absolute`: Positioned relative to the nearest positioned ancestor (`relative`).
* `fixed`: Positioned relative to the viewport and stays in place during scrolling.
* `sticky`: Toggles between `relative` and `fixed` based on the scroll position.
* `z-index` specifies the stack order of an element (only works on positioned elements).
</details>
