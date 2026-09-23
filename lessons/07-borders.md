# មេរៀនទី ០៧៖ បន្ទាត់ព្រំដែន (CSS Borders)

> **CSS Border Properties ប្រើសម្រាប់កំណត់បន្ទាត់ព័ទ្ធជុំវិញ Element និងធ្វើឱ្យជ្រុងមូល (Rounded Corners)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ស្គាល់គ្រប់ប្រភេទនៃ **border-style**
* ចេះកំណត់ **border-width, border-color** និង **Shorthand property**
* ចេះកំណត់ Border តាមជ្រុងនីមួយៗ (`top, right, bottom, left`)
* ចេះប្រើប្រាស់ **border-radius** ដើម្បីធ្វើជ្រុងមូល ឬរាងជារង្វង់មូល

---

## 🧱 Border Properties សំខាន់ៗ

### ១. `border-style` (ប្រភេទបន្ទាត់ - ចាំបាច់ត្រូវតែមាន)
បើគ្មាន `border-style` ទេ នោះ Border នឹងមិនបង្ហាញឡើយ៖
* `solid`: បន្ទាត់ត្រង់រលូន
* `dashed`: បន្ទាត់ដាច់ៗជាកង់ៗ
* `dotted`: បន្ទាត់ចុចៗជាគ្រាប់ៗ
* `double`: បន្ទាត់ភ្លោះពីរជាន់
* `none`: គ្មានបន្ទាត់ព្រំដែន

```css
p.solid  { border-style: solid; }
p.dashed { border-style: dashed; }
p.dotted { border-style: dotted; }
```

---

### ២. Border Width & Color
```css
p {
  border-style: solid;
  border-width: 2px;
  border-color: #3b82f6;
}
```

---

### ៣. `border` Shorthand Property
សរសេររួមគ្នាក្នុងបន្ទាត់តែមួយតាមលំដាប់៖ `width` ➔ `style` ➔ `color`

```css
.card {
  border: 1px solid #e2e8f0;
}
```

---

### ៤. កំណត់តាមជ្រុងនីមួយៗ (Individual Sides)
```css
.quote-box {
  /* បន្ទាត់ក្រាស់ពណ៌ខៀវតែខាងឆ្វេងប៉ុណ្ណោះ */
  border-left: 4px solid #2563eb;
  padding-left: 15px;
}
```

---

### ៥. `border-radius` (ជ្រុងមូល)
ប្រើសម្រាប់ធ្វើឱ្យជ្រុងរបស់ Element មូលស្អាត ឬបម្លែងរូបរាងឱ្យទៅជារង្វង់មូល (Circle):

```css
/* ជ្រុងមូលធម្មតា */
.button {
  border-radius: 8px;
}

/* រង្វង់មូល (Circle / Avatar) */
.avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

/* កំណត់ជ្រុងទាំង ៤ ខុសៗគ្នា (Top-Left, Top-Right, Bottom-Right, Bottom-Left) */
.custom-card {
  border-radius: 20px 0px 20px 0px;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Borders Demo</title>
  <style>
    .card {
      width: 280px;
      padding: 20px;
      margin: 15px;
      background-color: #ffffff;
      border: 2px solid #e2e8f0;
      border-radius: 12px;
    }

    .alert {
      border-left: 5px solid #ef4444;
      background-color: #fef2f2;
      padding: 12px;
      border-radius: 4px;
    }

    .avatar-img {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      border: 3px solid #3b82f6;
    }
  </style>
</head>
<body>

  <div class="card">
    <img class="avatar-img" src="../assets/images/avatar-user.jpg" alt="User Avatar">
    <h3>User Profile</h3>
    <div class="alert">
      ចំណាំ៖ គណនីរបស់អ្នកជិតផុតកំណត់ហើយ។
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **ភ្លេចដាក់ `border-style`:** ប្រសិនបើសរសេរត្រឹមតែ `border-width: 2px; border-color: red;` នោះ Border នឹងមិនបង្ហាញឡើយ ព្រោះតម្លៃលំនាំដើមរបស់ `border-style` គឺ `none`។
* ✅ **Avatar Perfect Circle:** ដើម្បីឱ្យ `border-radius: 50%` ចេញជារង្វង់មូលស្អាត ត្រូវប្រាកដថា `width` និង `height` របស់ Element នោះមានប្រវែងស្មើគ្នា។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប្រអប់ `<div>` មួយមាន `border: 2px dashed #3b82f6;`។
2. ដាក់ `border-radius: 16px;` និង `padding: 20px;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `border-style` property specifies what kind of border to display (`solid`, `dashed`, `dotted`, `none`, etc.).
* The `border-width` property sets the width of the border.
* The `border-color` property sets the color of the border.
* `border: 1px solid black;` is the shorthand for width, style, and color.
* `border-radius` creates rounded corners or circles (`50%`).
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ០៦៖ ផ្ទៃខាងក្រោយ (CSS Backgrounds)](06-backgrounds.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ០៨៖ គម្លាតខាងក្រៅ (CSS Margins) ➡️](08-margins.md) |
