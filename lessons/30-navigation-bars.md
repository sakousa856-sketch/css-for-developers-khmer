# មេរៀនទី ៣០៖ របារបញ្ជា និងមីនុយ (CSS Navigation Bars)

> **Navigation Bar គឺជាធាតុផ្សំសំខាន់បំផុតមួយនៃគេហទំព័រ ដោយអាចរៀបចំជាទម្រង់ Vertical (បញ្ឈរ) ឬ Horizontal (ផ្ដេក)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបង្កើត **Vertical Navigation Bar (Sidebar Menu)**
* ចេះបង្កើត **Horizontal Navigation Bar (Top Navbar)**
* ចេះកំណត់ **Active Link State** និង Hover Transitions

---

## 🧭 ១. Vertical Navigation Bar (Sidebar)

```css
.sidebar {
  width: 220px;
  background-color: #0f172a;
  list-style: none;
  padding: 0;
  margin: 0;
  border-radius: 8px;
}

.sidebar li a {
  display: block; /* ធ្វើឱ្យចុចបានពេញទំហំ Row */
  color: #cbd5e1;
  padding: 12px 20px;
  text-decoration: none;
  transition: background-color 0.2s;
}

.sidebar li a:hover {
  background-color: #1e293b;
  color: #ffffff;
}

.sidebar li a.active {
  background-color: #2563eb;
  color: #ffffff;
  font-weight: bold;
}
```

---

## 🌐 ២. Horizontal Navigation Bar (Top Navbar)

```css
.navbar {
  list-style: none;
  margin: 0;
  padding: 0;
  background-color: #1e293b;
  display: flex; /* ប្រើ Flexbox សម្រាប់រៀបចំជួរដេក */
  border-radius: 8px;
  overflow: hidden;
}

.navbar li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 20px;
  text-decoration: none;
  transition: background-color 0.2s;
}

.navbar li a:hover {
  background-color: #334155;
}

.navbar li a.active {
  background-color: #0284c7;
}

/* រុញ Menu Item ទៅស្តាំបង្អស់ */
.navbar li.right {
  margin-left: auto;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Navigation Bars Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f1f5f9;
    }

    /* Horizontal Navbar */
    .top-nav {
      list-style: none;
      margin: 0 0 30px 0;
      padding: 0;
      background-color: #0f172a;
      display: flex;
      border-radius: 8px;
      overflow: hidden;
    }

    .top-nav a {
      display: block;
      color: #94a3b8;
      padding: 14px 22px;
      text-decoration: none;
      font-weight: 500;
    }

    .top-nav a:hover {
      color: white;
      background-color: #1e293b;
    }

    .top-nav a.active {
      background-color: #2563eb;
      color: white;
    }

    .top-nav .nav-right {
      margin-left: auto;
    }
  </style>
</head>
<body>

  <h2>Top Navigation Bar</h2>
  <ul class="top-nav">
    <li><a href="#home" class="active">ទំព័រដើម</a></li>
    <li><a href="#news">ព័ត៌មាន</a></li>
    <li><a href="#contact">ទំនាក់ទំនង</a></li>
    <li><a href="#about">អំពីយើង</a></li>
    <li class="nav-right"><a href="#login">ចូលគណនី (Login)</a></li>
  </ul>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **`display: block` លើ `<a>`:** ត្រូវដាក់ `display: block` លើ Tag `<a>` ជានិច្ច ដើម្បីឱ្យតំបន់ចុច (Clickable area) រីកពេញផ្ទៃក្រឡា មិនមែនចុចបានតែលើតួអក្សរនោះឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Horizontal Navbar មួយដែលមាន Logo នៅខាងឆ្វេង និង Link Items នៅខាងស្តាំដោយប្រើ `margin-left: auto;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Navigation bars are basically lists of links (`<ul>` and `<li>` elements).
* Setting `display: block` on link elements makes the whole link area clickable.
* Flexbox (`display: flex;`) is the modern standard for creating responsive horizontal navigation bars.
* `margin-left: auto` easily pushes navigation items to the right side of the navbar.
</details>
