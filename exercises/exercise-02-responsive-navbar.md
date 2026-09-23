# លំហាត់អនុវត្តទី ០២៖ បង្កើត Responsive Navigation Bar

## 🎯 គោលបំណង (Objective)
អនុវត្ត **Flexbox និង Media Queries** ដើម្បីបង្កើត Navigation Bar ដែលប្តូរទម្រង់រវាង Mobile និង Desktop។

---

## 📋 លក្ខខណ្ឌតម្រូវ (Requirements)
1. **Desktop View (≥ 768px):**
   * Logo នៅខាងឆ្វេង, Navigation Links នៅខាងស្តាំជាជួរដេក (`display: flex; justify-content: space-between;`)
   * គម្លាតចន្លោះ Links គឺ `gap: 20px`
2. **Mobile View (< 768px):**
   * Logo នៅលើគេ, Navigation Links តម្រៀបជាជួរឈរ (Vertical column stack)

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
  <title>Responsive Navbar Solution</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: Arial, sans-serif; background: #f8fafc; }

    .navbar {
      background-color: #0f172a;
      padding: 15px 24px;
    }

    .nav-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
      max-width: 1100px;
      margin: 0 auto;
    }

    .logo {
      color: #38bdf8;
      font-size: 22px;
      font-weight: bold;
    }

    .nav-menu {
      list-style: none;
      display: flex;
      flex-direction: column;
      width: 100%;
      text-align: center;
      gap: 10px;
    }

    .nav-menu a {
      color: #cbd5e1;
      text-decoration: none;
      font-weight: 500;
      display: block;
      padding: 8px;
    }

    /* Desktop View */
    @media (min-width: 768px) {
      .nav-container {
        flex-direction: row;
        justify-content: space-between;
      }
      .nav-menu {
        flex-direction: row;
        width: auto;
        gap: 24px;
      }
    }
  </style>
</head>
<body>

  <header class="navbar">
    <div class="nav-container">
      <div class="logo">⚡ CodeBrand</div>
      <ul class="nav-menu">
        <li><a href="#">Home</a></li>
        <li><a href="#">Courses</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </header>

</body>
</html>
```
</details>
