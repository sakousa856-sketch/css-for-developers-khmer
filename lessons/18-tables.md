# មេរៀនទី ១៨៖ ការកំណត់ Style លើតារាង (CSS Tables)

> **CSS Table Properties ជួយឱ្យតារាងទិន្នន័យមានទម្រង់ស្អាត ងាយស្រួលអាន និងមានមុខងារ Zebra Stripes & Hoverable Rows។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបង្រួមបន្ទាត់ Border ពីរជាន់ឱ្យនៅតែមួយ (`border-collapse: collapse`)
* ចេះកំណត់ពណ៌ក្បាលតារាង និងគម្លាតក្រឡា (`padding`)
* ចេះធ្វើតារាងបែប Zebra Stripes ដោយប្រើ `:nth-child(even)`
* ចេះធ្វើឱ្យតារាងរំកិល Scroll បានលើអេក្រង់ទូរស័ព្ទ (Responsive Table)

---

## 📊 CSS Table Styling សំខាន់ៗ

### ១. `border-collapse: collapse` (ចាំបាច់បំផុត)
តាមលំនាំដើម Browser តែងបង្ហាញបន្ទាត់ Border នៃក្រឡាតារាងនីមួយៗដាច់ពីគ្នា (Double borders)។ ការដាក់ `border-collapse: collapse;` នឹងបង្រួមវាឱ្យនៅសល់បន្ទាត់ទោលស្អាត៖

```css
table {
  width: 100%;
  border-collapse: collapse; /* បង្រួមបន្ទាត់ពីរជាន់ */
}

th, td {
  border: 1px solid #e2e8f0;
  padding: 12px 16px;
  text-align: left;
}
```

---

### ២. Zebra Stripes (ពណ៌ឆ្លាស់គ្នា)
ប្រើ Pseudo-class `:nth-child(even)` ឬ `:nth-child(odd)` ដើម្បីប្តូរពណ៌ផ្ទៃជួរដេករំលងមួយៗ៖

```css
tbody tr:nth-child(even) {
  background-color: #f8fafc;
}
```

---

### ៣. Hoverable Table Rows (ចលនាពេលដាក់ Mouse លើជួរដេក)
```css
tbody tr:hover {
  background-color: #e0f2fe;
  cursor: pointer;
}
```

---

### ៤. Responsive Table (សម្រាប់អេក្រង់ទូរស័ព្ទ)
រុំ `<table>` ដោយ `<div class="table-responsive">`:

```css
.table-responsive {
  width: 100%;
  overflow-x: auto; /* អនុញ្ញាតឱ្យ Scroll ផ្ដេកលើ Mobile */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Tables Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .table-container {
      overflow-x: auto;
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    }

    table {
      width: 100%;
      border-collapse: collapse;
    }

    th {
      background-color: #0f172a;
      color: #ffffff;
      padding: 14px 16px;
      text-align: left;
      font-weight: 600;
    }

    td {
      padding: 12px 16px;
      border-bottom: 1px solid #e2e8f0;
      color: #334155;
    }

    tbody tr:nth-child(even) {
      background-color: #f8fafc;
    }

    tbody tr:hover {
      background-color: #f1f5f9;
    }

    .status-badge {
      background-color: #dcfce7;
      color: #15803d;
      padding: 4px 8px;
      border-radius: 4px;
      font-size: 12px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>តារាងគ្រប់គ្រងសិស្ស (Students List)</h2>
  
  <div class="table-container">
    <table>
      <thead>
        <tr>
          <th>អត្តលេខ</th>
          <th>ឈ្មោះពេញ</th>
          <th>មុខវិជ្ជា</th>
          <th>ស្ថានភាព</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>#001</td>
          <td>សុខ សាន្ត</td>
          <td>Frontend Web Development</td>
          <td><span class="status-badge">Active</span></td>
        </tr>
        <tr>
          <td>#002</td>
          <td>ចាន់ ធីតា</td>
          <td>Full-Stack Developer</td>
          <td><span class="status-badge">Active</span></td>
        </tr>
        <tr>
          <td>#003</td>
          <td>រ័ត្ន វិសាល</td>
          <td>UI/UX Design</td>
          <td><span class="status-badge">Active</span></td>
        </tr>
      </tbody>
    </table>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ដាក់ `padding` លើ `<th>` និង `<td>` ជានិច្ច:** កុំដាក់ padding លើ `<tr>` ព្រោះវានឹងមិនដំណើរការឡើយ។
* ✅ **ប្រើ `border-bottom` ជំនួសឱ្យ Full Grid Border:** ការប្រើតែបន្ទាត់ផ្តេក `border-bottom: 1px solid #e2e8f0;` ធ្វើឱ្យតារាងមើលទៅទាន់សម័យ (Modern UI) ជាងការគូសក្រឡាចត្រង្គគ្រប់ជ្រុង។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតតារាងមួយដែលមាន ៣ ជួរឈរ (Columns) និង ៤ ជួរដេក (Rows)។
2. ដាក់ `border-collapse: collapse;` និងធ្វើ Zebra Stripes ដោយប្រើ `tr:nth-child(even) { background-color: #f3f4f6; }`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `border-collapse: collapse;` sets whether table borders should collapse into a single border.
* `th` and `td` should be given `padding` to create breathing room inside table cells.
* Use `:nth-child(even)` or `:nth-child(odd)` to create striped tables (Zebra striping).
* Wrap tables inside a `div` with `overflow-x: auto` for mobile responsiveness.
</details>
