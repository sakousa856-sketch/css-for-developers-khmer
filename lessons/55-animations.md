# មេរៀនទី ៥៥៖ ចលនា Keyframes (CSS Animations & @keyframes)

> **CSS Animations អនុញ្ញាតឱ្យ Elements ធ្វើចលនាស្មុគស្មាញជាបន្តបន្ទាប់ដោយស្វ័យប្រវត្តិតាមរយៈ `@keyframes` rule ដោយមិនបាច់ពឹងផ្អែកលើ JavaScript ឡើយ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ដឹងពីរបៀបបង្កើតចលនាតាមរយៈ `@keyframes` (`from/to` ឬ `0%, 50%, 100%`)
* ស្គាល់ Properties សំខាន់ៗ៖ `animation-name`, `duration`, `iteration-count`, `fill-mode`
* ចេះបង្កើតចលនា Loading Spinner និង Pulse Animation

---

## 🎬 ១. ការបង្កើតចលនាតាមរយៈ `@keyframes`

`@keyframes` កំណត់ថាតើនៅដំណាក់កាលភាគរយនីមួយៗនៃពេលវេលា Element ត្រូវមាន Style យ៉ាងដូចម្តេច៖

```css
/* បង្កើត Animation ឈ្មោះ pulse-glow */
@keyframes pulse-glow {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.7;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}
```

---

## 🎛️ ២. បណ្តា Animation Properties

* **`animation-name`:** ឈ្មោះ Animation ដែលបានប្រកាសក្នុង `@keyframes`
* **`animation-duration`:** រយៈពេលនៃមួយជុំ (ឧ. `2s`)
* **`animation-iteration-count`:** ចំនួនជុំ (`3`, ឬ `infinite` វិលរហូតមិនចេះចប់)
* **`animation-direction`:** ទិសដៅ (`normal`, `reverse`, `alternate` ទៅហើយត្រឡប់មកវិញ)
* **`animation-fill-mode`:** `forwards` (រក្សា Style នៃ 100% ជាប់ថេរពេលចលនាចប់)

### Animation Shorthand:
```css
.pulse-badge {
  /* name | duration | timing | delay | iteration-count | direction */
  animation: pulse-glow 2s ease-in-out infinite;
}
```

---

## 🔄 ៣. ការបង្កើត Loading Spinner

```css
@keyframes spin {
  0%   { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.spinner {
  width: 40px;
  height: 40px;
  border: 4px solid #e2e8f0;
  border-top: 4px solid #2563eb; /* គែមខាងលើពណ៌ខៀវ */
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Animations Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 50px;
      background-color: #0f172a;
      color: white;
      display: flex;
      gap: 40px;
      align-items: center;
      justify-content: center;
    }

    /* 1. Spin Animation */
    @keyframes spin {
      100% { transform: rotate(360deg); }
    }

    .loader {
      width: 45px;
      height: 45px;
      border: 4px solid #334155;
      border-top: 4px solid #38bdf8;
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }

    /* 2. Floating Card Animation */
    @keyframes floatUpDown {
      0%, 100% { transform: translateY(0); }
      50%      { transform: translateY(-12px); }
    }

    .floating-box {
      background: #1e293b;
      padding: 20px 30px;
      border-radius: 12px;
      border: 1px solid #38bdf8;
      box-shadow: 0 10px 25px rgba(56, 189, 248, 0.2);
      animation: floatUpDown 3s ease-in-out infinite;
    }
  </style>
</head>
<body>

  <div class="loader"></div>

  <div class="floating-box">
    <h3>✨ Floating UI Box</h3>
    <p>ចលនាអណ្តែតឡើងចុះរលូនគ្មានទីបញ្ចប់</p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Accessibility (`prefers-reduced-motion`):** អ្នកប្រើប្រាស់មួយចំនួនមានបញ្ហាវិលមុខនឹងចលនា។ គួរគោរពសិទ្ធិអ្នកប្រើដោយបិទចលនាបើពួកគេជ្រើសរើស Reduced Motion ក្នុង OS Settings៖
  ```css
  @media (prefers-reduced-motion: reduce) {
    * { animation: none !important; transition: none !important; }
  }
  ```

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Loading Spinner មួយដោយប្រើ `@keyframes spin`។
2. បង្កើតចលនា Pulsing Dot ពណ៌បៃតងសម្រាប់បង្ហាញស្ថានភាព "Online"។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* An animation lets an element gradually change from one style to another.
* `@keyframes` specifies the animation code with percentage checkpoints (`0%` to `100%` or `from`/`to`).
* `animation: name duration timing-function delay iteration-count direction fill-mode;`.
* Always support `prefers-reduced-motion` for accessible user experience.
</details>
