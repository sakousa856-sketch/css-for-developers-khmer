# លំហាត់អនុវត្តទី ០៤៖ បង្កើត Admin Dashboard ដោយប្រើ CSS Grid

## 🎯 គោលបំណង (Objective)
អនុវត្ត **CSS Grid (`grid-template-areas`), Grid Lines, និង Responsive Design** ដើម្បីបង្កើតប្លង់ Admin Dashboard ពេញលេញ។

---

## 📋 លក្ខខណ្ឌតម្រូវ (Requirements)
1. **Layout Structure:**
   * Header (កម្ពស់ 60px)
   * Sidebar (ទទឹង 220px)
   * Main Content Area (Scrollable)
   * Footer (កម្ពស់ 40px)
2. **Widgets Area:** ប្រើ `repeat(auto-fit, minmax(200px, 1fr))` សម្រាប់ Stat Cards។
3. **Mobile Layout:** នៅលើអេក្រង់ `< 768px` ត្រូវលាក់ Sidebar ហើយប្តូរ Grid មកនៅសល់តែ 1 Column។

---

## 💡 ចម្លើយគំរូ (Solution Key)

<details>
<summary>👉 ចុចទីនេះដើម្បីមើលកូដចម្លើយគំរូ</summary>

```html
<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Admin Dashboard Grid Solution</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: Arial, sans-serif; background: #f8fafc; color: #1e293b; }

    .grid-app {
      display: grid;
      grid-template-columns: 220px 1fr;
      grid-template-rows: 60px 1fr 40px;
      grid-template-areas:
        "sidebar header"
        "sidebar main"
        "sidebar footer";
      min-height: 100vh;
    }

    .sidebar { grid-area: sidebar; background: #0f172a; color: white; padding: 20px; }
    .header { grid-area: header; background: white; border-bottom: 1px solid #e2e8f0; padding: 0 20px; display: flex; align-items: center; justify-content: space-between; }
    .main { grid-area: main; padding: 20px; }
    .footer { grid-area: footer; background: white; border-top: 1px solid #e2e8f0; padding: 0 20px; display: flex; align-items: center; font-size: 13px; color: #64748b; }

    .stats {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 15px;
    }

    .stat-card {
      background: white;
      padding: 20px;
      border-radius: 8px;
      border: 1px solid #e2e8f0;
    }

    @media (max-width: 768px) {
      .grid-app {
        grid-template-columns: 1fr;
        grid-template-areas:
          "header"
          "main"
          "footer";
      }
      .sidebar { display: none; }
    }
  </style>
</head>
<body>

  <div class="grid-app">
    <aside class="sidebar">Sidebar Navigation</aside>
    <header class="header"><h3>Dashboard Header</h3> <span>Admin 👤</span></header>
    <main class="main">
      <div class="stats">
        <div class="stat-card"><h4>Users</h4><p style="font-size:24px;font-weight:bold;color:#2563eb;">1,200</p></div>
        <div class="stat-card"><h4>Sales</h4><p style="font-size:24px;font-weight:bold;color:#16a34a;">$45,000</p></div>
      </div>
    </main>
    <footer class="footer">Dashboard © 2026</footer>
  </div>

</body>
</html>
```
</details>
