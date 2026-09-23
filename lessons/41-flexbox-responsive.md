# មេរៀនទី ៤១៖ Flexbox: Layouts ជាក់ស្តែងក្នុងពិភពពិត (Real-World Flexbox Layouts)

> **ការរួមបញ្ចូល Flexbox Properties ទាំងអស់ដើម្បីសាងសង់ប្លង់គេហទំព័រពេញលេញ (Holy Grail Layout, Card Decks, Responsive Split Sections)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបង្កើត **Responsive Card Grid** ជាមួយ `flex-wrap: wrap`
* ចេះបង្កើត **Sticky Footer Layout** (Footer នៅបាតក្រោមជានិច្ច)
* ចេះបង្កើត **Holy Grail 3-Column Layout**

---

## 🏗️ ១. Responsive Card Grid (ដោយគ្មាន Media Queries)

```css
.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  flex: 1 1 280px; /* រីកស្មើគ្នា, រួញបាន, ទំហំមូលដ្ឋាន 280px */
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.08);
}
```

👉 **ដំណើរការ៖** នៅលើអេក្រង់ធំ វាតម្រៀប 3 ឬ 4 Columns។ នៅពេលអេក្រង់រួញតូចជាង 280px វានឹងធ្លាក់បន្ទាត់ដោយស្វ័យប្រវត្តិមកនៅត្រឹម 1 Column!

---

## 🦶 ២. Sticky Footer Pattern (Footer នៅបាតក្រោមទំព័រជានិច្ច)

បញ្ហាទូទៅ៖ ពេលទំព័រមានអត្ថបទតិច Footer តែងរត់ឡើងមកកណ្តាលអេក្រង់។

### 🛠️ ដំណោះស្រាយ Flexbox៖
```css
body {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  margin: 0;
}

main {
  flex: 1; /* រុញ Footer ឱ្យធ្លាក់ទៅបាតក្រោមបង្អស់ជានិច្ច */
}

footer {
  background-color: #0f172a;
  color: white;
  padding: 20px;
  text-align: center;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Real World Layouts</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      background-color: #f1f5f9;
    }

    header {
      background: #1e293b;
      color: white;
      padding: 15px 30px;
    }

    /* Main Area stretches to push footer down */
    main {
      flex: 1;
      padding: 30px;
      max-width: 1100px;
      width: 100%;
      margin: 0 auto;
    }

    .card-deck {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
    }

    .feature-card {
      flex: 1 1 300px;
      background: white;
      padding: 25px;
      border-radius: 8px;
      border: 1px solid #e2e8f0;
    }

    footer {
      background: #0f172a;
      color: #94a3b8;
      text-align: center;
      padding: 15px;
    }
  </style>
</head>
<body>

  <header>
    <h2>🚀 WebApp Brand</h2>
  </header>

  <main>
    <h1 style="margin-bottom: 20px;">មុខងារពិសេសៗរបស់យើង</h1>
    
    <div class="card-deck">
      <div class="feature-card">
        <h3>⚡ Ultra Fast</h3>
        <p>ដំណើរការលឿនរហ័ស គាំទ្រការទាញយកទិន្នន័យក្នុងពេលតែមួយវិនាទី។</p>
      </div>

      <div class="feature-card">
        <h3>🔒 Secure by Default</h3>
        <p>ការពារទិន្នន័យអ្នកប្រើប្រាស់ជាមួយប្រព័ន្ធ End-to-End Encryption។</p>
      </div>

      <div class="feature-card">
        <h3>📱 100% Responsive</h3>
        <p>បង្ហាញរូបរាងស្អាតឥតខ្ចោះលើគ្រប់ទំហំអេក្រង់ Smart Phone និង PC។</p>
      </div>
    </div>
  </main>

  <footer>
    <p>© 2026 WebApp Brand. រក្សាសិទ្ធិគ្រប់យ៉ាង។</p>
  </footer>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **`flex: 1 1 300px`:** គឺជាទម្រង់ដ៏មានអនុភាពក្នុងការបង្កើត Auto-Responsive Cards ដោយមិនបាច់សរសេរ `@media (max-width: ...)` ច្រើនបន្ទាត់។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. អនុវត្តកូដ Sticky Footer ខាងលើក្នុងឯកសារ HTML ផ្ទាល់ខ្លួនរបស់អ្នក។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Responsive card decks can be achieved using `display: flex; flex-wrap: wrap;` and `flex: 1 1 300px;`.
* Sticky Footer is elegantly solved with `body { min-height: 100vh; display: flex; flex-direction: column; }` and `main { flex: 1; }`.
</details>

---

## 🧭 ការរុករកមេរៀន (Lesson Navigation)

| ⬅️ មេរៀនមុន (Previous) | 🏠 មាតិការួម (Table of Contents) | ➡️ មេរៀនបន្ទាប់ (Next) |
| :--- | :---: | ---: |
| [⬅️ មេរៀនទី ៤០៖ Flexbox: Item Properties (CSS Flexbox Items)](40-flexbox-items.md) | [📚 មាតិកាទាំងអស់](../README.md) | [មេរៀនទី ៤២៖ Grid: Container Properties (CSS Grid Container) ➡️](42-grid-container.md) |
