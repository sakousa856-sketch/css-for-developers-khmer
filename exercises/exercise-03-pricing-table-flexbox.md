# លំហាត់អនុវត្តទី ០៣៖ បង្កើត Pricing Cards ដោយប្រើ Flexbox

## 🎯 គោលបំណង (Objective)
អនុវត្ត **Flexbox Alignment, Transitions, និង Pseudo-classes (`:nth-child`)** ដើម្បីបង្កើតតារាងតម្លៃ Pricing Cards ៣ ជម្រើស។

---

## 📋 លក្ខខណ្ឌតម្រូវ (Requirements)
1. **Container:** `display: flex; gap: 20px; flex-wrap: wrap;`
2. **Featured Card (កាតកណ្តាល Pro Plan):**
   * មាន Border ពណ៌ខៀវ `#2563eb`
   * មាន Badge "Most Popular"
   * ពង្រីកធំជាងកាតធម្មតាបន្តិចដោយប្រើ `transform: scale(1.05)`
3. **Card Buttons:** មាន Hover Animation រលូន។

---

## 💡 ចម្លើយគំរូ (Solution Key)

<details>
<summary>👉 ចុចទីនេះដើម្បីមើលកូដចម្លើយគំរូ</summary>

```html
<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <title>Pricing Cards Solution</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
      padding: 50px 20px;
    }

    .pricing-wrap {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;
      flex-wrap: wrap;
      max-width: 1000px;
      margin: 0 auto;
    }

    .card {
      flex: 1 1 280px;
      background: white;
      padding: 30px;
      border-radius: 12px;
      border: 1px solid #e2e8f0;
      text-align: center;
      position: relative;
    }

    .card.popular {
      border: 2px solid #2563eb;
      transform: scale(1.04);
      box-shadow: 0 10px 25px rgba(37, 99, 235, 0.15);
    }

    .popular-badge {
      position: absolute;
      top: -12px;
      left: 50%;
      transform: translateX(-50%);
      background: #2563eb;
      color: white;
      font-size: 12px;
      font-weight: bold;
      padding: 4px 12px;
      border-radius: 20px;
    }

    .price {
      font-size: 36px;
      font-weight: bold;
      color: #0f172a;
      margin: 15px 0;
    }

    .btn {
      width: 100%;
      background: #0f172a;
      color: white;
      border: none;
      padding: 12px;
      border-radius: 6px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 20px;
      transition: background 0.2s;
    }

    .card.popular .btn {
      background: #2563eb;
    }
  </style>
</head>
<body>

  <div class="pricing-wrap">
    <div class="card">
      <h3>Basic</h3>
      <div class="price">$9<span style="font-size:14px;color:#64748b;">/mo</span></div>
      <p>សម្រាប់គម្រោងខ្នាតតូច</p>
      <button class="btn">ចុះឈ្មោះ</button>
    </div>

    <div class="card popular">
      <div class="popular-badge">MOST POPULAR</div>
      <h3>Professional</h3>
      <div class="price">$29<span style="font-size:14px;color:#64748b;">/mo</span></div>
      <p>សម្រាប់អាជីវកម្មរីកចម្រើន</p>
      <button class="btn">ចុះឈ្មោះ</button>
    </div>

    <div class="card">
      <h3>Enterprise</h3>
      <div class="price">$99<span style="font-size:14px;color:#64748b;">/mo</span></div>
      <p>សម្រាប់ក្រុមហ៊ុនខ្នាតធំ</p>
      <button class="btn">ចុះឈ្មោះ</button>
    </div>
  </div>

</body>
</html>
```
</details>
