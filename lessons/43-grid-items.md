# មេរៀនទី ៤៣៖ Grid: Item Properties (CSS Grid Items)

> **Grid Item Properties ប្រើសម្រាប់គ្រប់គ្រងទីតាំង និងការពង្រីកក្រឡា (Spanning) នៃ Element កូនៗនីមួយៗឆ្លងកាត់ជួរឈរ ឬជួរដេក។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពី **Grid Lines** (បន្ទាត់ព្រំដែនលេខរៀង 1, 2, 3...)
* ចេះពង្រីកក្រឡាកាត់ជួរឈរ (`grid-column: 1 / 3` ឬ `span 2`)
* ចេះពង្រីកក្រឡាកាត់ជួរដេក (`grid-row: 1 / 3`)
* ចេះតម្រឹមកូនតែមួយតាម `justify-self` និង `align-self`

---

## 📐 Grid Lines និងការ Spanning

Grid Container មួយដែលមាន 3 Columns នឹងមាន Grid Lines ចំនួន **4 បន្ទាត់** (1, 2, 3, 4)៖

```
Line 1        Line 2        Line 3        Line 4
  |   Col 1     |   Col 2     |   Col 3     |
```

### ១. `grid-column` (ពង្រីកជួរឈរ)
* `grid-column: 1 / 3;` ➔ ចាប់ផ្តើមពីបន្ទាត់ទី 1 ដល់បន្ទាត់ទី 3 (ពង្រីកយក 2 Columns)
* `grid-column: span 2;` ➔ ពង្រីកយក 2 Columns ពីទីតាំងបច្ចុប្បន្ន
* `grid-column: 1 / -1;` ➔ ពង្រីកពេញទទឹងពីដើមរហូតដល់បន្ទាត់ចុងក្រោយបង្អស់ (`-1`)

```css
.featured-banner {
  grid-column: 1 / -1; /* ពង្រីកពេញគ្រប់ Columns ទាំងអស់ */
}
```

---

### ២. `grid-row` (ពង្រីកជួរដេក)
* `grid-row: 1 / 3;` ➔ ពង្រីកកាត់ ២ ជួរដេកចុះក្រោម

```css
.tall-sidebar {
  grid-row: span 2; /* ពង្រីកកម្ពស់ ២ ជាន់ */
}
```

---

### ៣. `justify-self` & `align-self`
* `justify-self`: តម្រឹមកូននេះតាមជួរដេកផ្ដេក (`start`, `end`, `center`, `stretch`)
* `align-self`: តម្រឹមកូននេះតាមជួរឈរបញ្ឈរ (`start`, `end`, `center`, `stretch`)

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Grid Items Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .bento-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
      max-width: 800px;
      margin: 0 auto;
    }

    .card {
      background: white;
      padding: 20px;
      border-radius: 10px;
      border: 1px solid #cbd5e1;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
    }

    /* Bento Item Spanning */
    .card-wide {
      grid-column: span 2; /* ពង្រីកយក ២ ក្រឡាផ្ដេក */
      background-color: #dbeafe;
    }

    .card-tall {
      grid-row: span 2; /* ពង្រីកយក ២ ក្រឡាបញ្ឈរ */
      background-color: #fef3c7;
    }
  </style>
</head>
<body>

  <h2>Bento Grid Layout</h2>

  <div class="bento-grid">
    <div class="card card-wide">
      <h3>1. Wide Feature (span 2 cols)</h3>
      <p>កាតធំទូលាយសម្រាប់បង្ហាញមុខងារចម្បង។</p>
    </div>

    <div class="card card-tall">
      <h3>2. Tall Stat (span 2 rows)</h3>
      <p>កាតកម្ពស់វែងសម្រាប់ស្ថិតិ ឬផ្សាយពាណិជ្ជកម្ម។</p>
    </div>

    <div class="card"><h3>3. Small Card</h3></div>
    <div class="card"><h3>4. Small Card</h3></div>
    <div class="card card-wide"><h3>5. Bottom Wide Card</h3></div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **`grid-column: 1 / -1`:** គឺជាទម្រង់កូដដ៏មានប្រយោជន៍បំផុតសម្រាប់បង្កើត Full-width Hero Banner ឬ Table Header ក្នុង Grid Layout។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Grid 3 Columns។
2. កំណត់ឱ្យ Item ទី 1 ពង្រីកកាត់ ៣ ជួរឈរពេញលេញ (`grid-column: 1 / -1;`)។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `grid-column: start / end;` specifies a grid item's size and location in terms of column grid lines.
* `grid-row: start / end;` specifies a grid item's size and location in terms of row grid lines.
* `grid-column: span 2;` spans the item across two column tracks.
* `grid-column: 1 / -1;` spans the item across the full width of the grid.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ៤២៖ Grid: Container Properties (CSS Grid Container)](42-grid-container.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ៤៤៖ Grid: Advanced Patterns & Auto Layouts ➡️](44-grid-advanced.md) |
