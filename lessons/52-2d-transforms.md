# មេរៀនទី ៥២៖ ការបំប្លែងរូបរាង 2D (CSS 2D Transforms)

> **CSS 2D Transforms ប្រើសម្រាប់ផ្លាស់ប្តូរទីតាំង បង្វិល ពង្រីក-បង្រួម និងទ្រេតរូបរាងរបស់ Element លើប្លង់ 2D (អ័ក្ស X និង Y)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះរំកិលទីតាំងដោយប្រើ `translate(x, y)`
* ចេះបង្វិលមុំដោយប្រើ `rotate(deg)`
* ចេះពង្រីក-បង្រួមទំហំដោយប្រើ `scale(x, y)`
* ចេះធ្វើឱ្យទ្រេតដោយប្រើ `skew(x, y)` និងប្តូរបង្គោលវិល `transform-origin`

---

## 🔄 អនុគមន៍ 2D Transform ទាំង ៤ សំខាន់ៗ

### ១. `translate(x, y)` (រំកិលទីតាំង)
រំកិល Element ចេញពីទីតាំងបច្ចុប្បន្នដោយមិនប៉ះពាល់ដល់ Normal Document Flow ឡើយ៖
```css
.box {
  transform: translate(50px, 100px); /* ទៅស្តាំ 50px, ចុះក្រោម 100px */
}
```

---

### ២. `rotate(angle)` (បង្វិលមុំ)
បង្វិល Element តាមទ្រនិចនាឡិកា (ដឺក្រេ `deg`):
```css
.card-tilted {
  transform: rotate(15deg);  /* បង្វិលទៅស្តាំ 15 ដឺក្រេ */
  transform: rotate(-10deg); /* បង្វិលត្រឡប់ក្រោយ 10 ដឺក្រេ */
}
```

---

### ៣. `scale(x, y)` (ពង្រីក ឬបង្រួមទំហំ)
* `scale(1.1)` ➔ ពង្រីកធំជាងមុន 10% (ពេញនិយមបំផុតសម្រាប់ Hover Effect លើ Cards & Buttons)
* `scale(0.8)` ➔ បង្រួមតូចមកនៅសល់ 80%

```css
.btn:hover {
  transform: scale(1.05);
}
```

---

### ៤. `skew(x-angle, y-angle)` (ធ្វើឱ្យទ្រេត)
```css
.parallelogram {
  transform: skewX(-20deg); /* ទ្រេតតាមអ័ក្ស X */
}
```

---

### ៥. ការរួមបញ្ចូលគ្នាច្រើន (Multiple Transforms)
សរសេរដកឃ្លាតៗគ្នា៖
```css
.active-card {
  transform: translateY(-8px) scale(1.03) rotate(1deg);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS 2D Transforms Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 40px;
      background-color: #f1f5f9;
      display: flex;
      gap: 30px;
      justify-content: center;
    }

    .box {
      width: 140px;
      height: 100px;
      background: #2563eb;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      border-radius: 8px;
      transition: transform 0.3s ease;
      cursor: pointer;
    }

    .box-translate:hover { transform: translateY(-15px); }
    .box-rotate:hover    { transform: rotate(20deg); }
    .box-scale:hover     { transform: scale(1.2); }
    .box-skew:hover      { transform: skewX(-15deg); }
  </style>
</head>
<body>

  <div class="box box-translate">Translate -15px</div>
  <div class="box box-rotate">Rotate 20deg</div>
  <div class="box box-scale">Scale 1.2x</div>
  <div class="box box-skew">Skew -15deg</div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Performance Note:** ការប្រើប្រាស់ `transform: translate()` ដំណើរការលឿនជាង និងរលូន (60 FPS Hardware Acceleration) ជាងការប្រើ `top/left` ព្រោះវាដំណើរការលើ GPU ដោយមិនបាច់គណនា DOM Reflow ឡើងវិញឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Card មួយមាន `transition: transform 0.3s;`។
2. ពេល `:hover` ឱ្យមាន `transform: translateY(-6px) scale(1.02);`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS 2D transforms allow elements to be translated, rotated, scaled, and skewed.
* `translate(x, y)` moves an element along the X and Y axes.
* `scale(x, y)` increases or decreases element size.
* `rotate(deg)` rotates an element clockwise by specified degrees.
* Transforms are GPU-accelerated and offer high performance (60fps) compared to top/left manipulations.
</details>
