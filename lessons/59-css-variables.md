# មេរៀនទី ៥៩៖ អថេរក្នុង CSS (CSS Variables / Custom Properties)

> **CSS Variables (Custom Properties) អនុញ្ញាតឱ្យយើងរក្សាទុកតម្លៃពណ៌ ទំហំ Font និងគម្លាត Spacing ក្នុងអថេរមួយកន្លែង ដើម្បីងាយស្រួលកែសម្រួលទូទាំង Website និងបង្កើតមុខងារ Dark Mode Toggle។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះប្រកាស CSS Variables ក្នុង `:root` Selector
* ចេះទាញយកអថេរមកប្រើតាមរយៈអនុគមន៍ `var()`
* ចេះបង្កើតប្រព័ន្ធ **Dark Mode / Light Mode Theme Switching** តាមស្តង់ដារឧស្សាហកម្ម

---

## 🏷️ ១. ការប្រកាស និងទាញយក CSS Variables

* **ឈ្មោះអថេរ៖** ត្រូវតែចាប់ផ្តើមដោយសញ្ញាដកពីរ `--` ជានិច្ច (ឧ. `--primary-color`)
* **Scope សកល (`:root`):** ប្រកាសក្នុង `:root` ដើម្បីឱ្យគ្រប់ elements ទាំងអស់ក្នុងទំព័រអាចហៅប្រើបាន
* **ការហៅប្រើ៖** ប្រើអនុគមន៍ `var(--variable-name, fallback-value)`

```css
/* 1. ប្រកាសអថេរសកល Global Variables */
:root {
  --primary-color: #2563eb;
  --text-color: #1e293b;
  --bg-color: #f8fafc;
  --card-bg: #ffffff;
  --border-radius: 12px;
  --base-spacing: 16px;
}

/* 2. ទាញយកមកប្រើប្រាស់ */
body {
  background-color: var(--bg-color);
  color: var(--text-color);
}

.btn-primary {
  background-color: var(--primary-color);
  border-radius: var(--border-radius);
  padding: calc(var(--base-spacing) * 0.75) calc(var(--base-spacing) * 1.5);
}
```

---

## 🌓 ២. ការបង្កើតមុខងារ Dark Mode & Light Mode

យើងគ្រាន់តែផ្លាស់ប្តូរតម្លៃនៃអថេរនៅក្នុង `[data-theme="dark"]` ឬ `.dark-mode` ជាការស្រេច ដោយមិនបាច់សរសេរ CSS ឡើងវិញសម្រាប់គ្រប់ Class ឡើយ៖

```css
/* Light Mode (Default) */
:root {
  --bg-main: #ffffff;
  --text-main: #0f172a;
  --card-bg: #f8fafc;
  --border-color: #e2e8f0;
}

/* Dark Mode Theme */
[data-theme="dark"] {
  --bg-main: #0f172a;
  --text-main: #f8fafc;
  --card-bg: #1e293b;
  --border-color: #334155;
}

/* អនុវត្តតាម OS Dark Mode ដោយស្វ័យប្រវត្តិ */
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg-main: #0f172a;
    --text-main: #f8fafc;
    --card-bg: #1e293b;
    --border-color: #334155;
  }
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS + JS Theme Toggle)

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8">
  <title>CSS Variables & Dark Mode Demo</title>
  <style>
    :root {
      --bg-body: #f1f5f9;
      --card-bg: #ffffff;
      --text-title: #0f172a;
      --text-body: #475569;
      --primary: #2563eb;
      --border: #cbd5e1;
    }

    [data-theme="dark"] {
      --bg-body: #090d16;
      --card-bg: #131b2e;
      --text-title: #f8fafc;
      --text-body: #94a3b8;
      --primary: #38bdf8;
      --border: #1e293b;
    }

    body {
      background-color: var(--bg-body);
      color: var(--text-body);
      font-family: Arial, sans-serif;
      padding: 40px;
      transition: background-color 0.3s, color 0.3s;
    }

    .theme-card {
      max-width: 400px;
      margin: 0 auto;
      background-color: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 25px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
      transition: background-color 0.3s;
    }

    .theme-card h2 {
      color: var(--text-title);
      margin-top: 0;
    }

    .toggle-btn {
      background-color: var(--primary);
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <div class="theme-card">
    <h2>🌓 ប្រព័ន្ធ Dark Mode Theme</h2>
    <p>ទំព័រនេះប្រើប្រាស់ CSS Variables ពេញលេញ។ ចុចប៊ូតុងខាងក្រោមដើម្បីប្តូរពណ៌ Theme៖</p>
    <button class="toggle-btn" onclick="toggleTheme()">ប្តូរ Dark / Light Mode</button>
  </div>

  <script>
    function toggleTheme() {
      const html = document.documentElement;
      const current = html.getAttribute('data-theme');
      html.setAttribute('data-theme', current === 'dark' ? 'light' : 'dark');
    }
  </script>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **CSS Variables Case-Sensitive:** `--main-color` និង `--Main-Color` គឺជាអថេរពីរផ្សេងគ្នា។ គួរប្រើទម្រង់ Kebab-case (អក្សរតូចទាំងអស់) ជានិច្ច។
* ✅ **Fallback Value:** អាចដាក់ Fallback ក្នុង `var(--color, #000)` ប្រសិនបើអថេរមិនទាន់ត្រូវបានកំណត់។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត `:root` variables សម្រាប់ `--brand-color`, `--brand-spacing`, `--brand-radius`។
2. យកអថេរទាំងនោះទៅប្រើលើប៊ូតុង និង Cards ក្នុងទំព័ររបស់អ្នក។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* CSS variables (custom properties) are entities defined by CSS authors that contain specific values to be reused throughout a document.
* Declared with double dashes `--` and accessed with `var(--name)`.
* Declaring variables in `:root` gives them global scope across the entire DOM tree.
* Switching custom property values inside `[data-theme="dark"]` provides the most maintainable Dark Mode architecture.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>59</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៥៩</strong> នៃ <strong>៦០</strong></p>

| [← Prev](58-glassmorphism.md) | [01](01-introduction.md) | ... | [56](56-tooltips-and-modals.md) | [57](57-filter-effects.md) | [58](58-glassmorphism.md) | **[ 59 ]** | [60](60-modern-features.md) | [Next →](60-modern-features.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
