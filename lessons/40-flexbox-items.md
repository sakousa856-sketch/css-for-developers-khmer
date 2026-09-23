# មេរៀនទី ៤០៖ Flexbox: Item Properties (CSS Flexbox Items)

> **Flex Item Properties ប្រើសម្រាប់កំណត់ឥរិយាបថលើ Element កូនៗនីមួយៗ (Children) ក្នុង Flex Container ដូចជា ការរីកធំ ការរួញតូច និងលំដាប់បង្ហាញ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះគ្រប់គ្រងសមាមាត្ររីកធំ (`flex-grow`) និងរួញតូច (`flex-shrink`)
* ចេះកំណត់ទំហំគោលដំបូង (`flex-basis`)
* ចេះប្រើ `flex` Shorthand Property ត្រឹមត្រូវតាមស្តង់ដារ
* ចេះប្តូរលំដាប់កូន (`order`) និងតម្រឹមកូនដាច់ដោយឡែក (`align-self`)

---

## 🎛️ បណ្តា Flex Item Properties

### ១. `flex-grow` (សមាមាត្ររីកយកលំហទទេ)
កំណត់ថាតើ Item នោះត្រូវរីកប៉ុន្មានដងធៀបនឹង Item ផ្សេងទៀតដើម្បីបំពេញលំហទទេដែលនៅសល់៖
* `flex-grow: 0` (Default): មិនរីកទេ (នៅទំហំដើម)
* `flex-grow: 1`: រីកស្មើៗគ្នាបំពេញលំហទទេ

```css
/* Sidebar ទំហំថេរ, Main Content រីកយកលំហដែលសល់ទាំងអស់ */
.sidebar { width: 250px; }
.main-content { flex-grow: 1; }
```

---

### ២. `flex-shrink` (សមាមាត្ររួញតូចពេលចង្អៀត)
* `flex-shrink: 1` (Default): អនុញ្ញាតឱ្យរួញតូចពេលអេក្រង់ចង្អៀត
* `flex-shrink: 0`: **ហាមមិនឱ្យរួញតូចដាច់ខាត** (រក្សាទំហំដើមជានិច្ច ឧ. សម្រាប់ Logo ឬ Avatar)

---

### ៣. `flex-basis` (ទំហំគោលដំបូង)
កំណត់ទំហំទទឹងដំបូងរបស់ Item មុនពេល `flex-grow` ឬ `flex-shrink` ចូលរួមគណនា (ជំនួស `width`):
```css
.card {
  flex-basis: 300px;
}
```

---

### ៤. `flex` Shorthand Property (និយមប្រើបំផុត ⭐)
រូបមន្តសរសេររួម៖ `flex: [flex-grow] [flex-shrink] [flex-basis];`

```css
/* រូបមន្តទូទៅដែល Developers ប្រើ */
.item-equal  { flex: 1; }           /* flex: 1 1 0% (ចែកទំហំស្មើគ្នាឥតខ្ចោះ) */
.item-auto   { flex: auto; }        /* flex: 1 1 auto */
.item-fixed  { flex: 0 0 250px; }   /* មិនរីក មិនរួញ រក្សា 250px ជាប់ថេរ */
```

---

### ៥. `align-self` (តម្រឹមកូនតែមួយដាច់ដោយឡែក)
Override ឈ្នះ `align-items` របស់ Parent Container សម្រាប់តែកូនមួយគត់នេះ៖
* `auto`, `flex-start`, `flex-end`, `center`, `baseline`, `stretch`

---

### ៦. `order` (ប្តូរលំដាប់បង្ហាញ)
ប្តូរទីតាំងកូនៗដោយមិនបាច់កែកូដ HTML (លេខកាន់តែតូច បង្ហាញមុនគេ, Default = `0`):
```css
.featured-item {
  order: -1; /* រុញមកមុខគេបង្អស់ */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Flex Items Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .dashboard-layout {
      display: flex;
      gap: 20px;
      height: 300px;
    }

    /* Fixed Sidebar (flex: 0 0 220px) */
    .sidebar {
      flex: 0 0 220px;
      background-color: #0f172a;
      color: white;
      padding: 20px;
      border-radius: 8px;
    }

    /* Expanding Main Content (flex: 1) */
    .main-area {
      flex: 1;
      background-color: white;
      border: 1px solid #cbd5e1;
      padding: 20px;
      border-radius: 8px;
    }

    /* Special Aside with align-self */
    .aside-box {
      flex: 0 0 180px;
      background-color: #dbeafe;
      padding: 15px;
      border-radius: 8px;
      align-self: flex-start; /* មិនពង្រីកពេញកម្ពស់ដូចគេ */
    }
  </style>
</head>
<body>

  <div class="dashboard-layout">
    <aside class="sidebar">Sidebar (220px Fixed)</aside>
    <main class="main-area">Main Content Area (flex: 1 ➔ រីកយកលំហដែលនៅសល់)</main>
    <aside class="aside-box">Aside Panel (align-self: flex-start)</aside>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ប្រើ `flex: 1` ជំនួស `width: 100%` ក្នុង Flex Container:** ការដាក់ `width: 100%` លើកូនអាចបង្កឱ្យមានបញ្ហា Overflow ប្រសិនបើមាន `gap` ឬ sibling elements។ `flex: 1;` នឹងគណនាទំហំដែលនៅសល់យ៉ាងត្រឹមត្រូវ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Flex Container មួយមានធាតុ ៣។
2. កំណត់ឱ្យធាតុទី 1 មាន `flex: 1;`, ធាតុទី 2 មាន `flex: 2;` (រីកធំជាងគេពីរដង), និងធាតុទី 3 មាន `flex: 1;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `flex-grow`: Defines the ability for a flex item to grow if necessary.
* `flex-shrink`: Defines the ability for a flex item to shrink if necessary.
* `flex-basis`: Defines the default size of an element before the remaining space is distributed.
* `flex: 0 0 250px;` creates a rigid fixed-width flex item.
* `align-self` allows overriding the container's `align-items` property for individual flex items.
</details>
