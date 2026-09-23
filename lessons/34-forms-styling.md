# មេរៀនទី ៣៤៖ ការកំណត់ Style លើ Forms & Inputs (CSS Forms)

> **ការកំណត់ Style លើ Form Inputs ជួយឱ្យទម្រង់ចុះឈ្មោះ ឬ Login មានភាពស្រស់ស្អាត ងាយស្រួលបំពេញ និងបង្កើន Conversion Rate។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះកំណត់ Style លើ Text Inputs, Textarea, Select Dropdowns
* ចេះបង្កើត Focus Glow Effect លើ Input
* ចេះរៀបចំ Form Layout និង Submit Buttons ស្អាតកម្រិត Professional

---

## 📝 គន្លឹះសំខាន់ៗក្នុងការ Styling Forms

```css
/* 1. Reset និងកំណត់ទំហំ */
input[type="text"],
input[type="email"],
input[type="password"],
textarea,
select {
  width: 100%;
  padding: 12px 16px;
  font-size: 15px;
  border: 1.5px solid #cbd5e1;
  border-radius: 8px;
  background-color: #ffffff;
  color: #1e293b;
  box-sizing: border-box;
  transition: all 0.2s ease-in-out;
}

/* 2. Focus Glow State ពេល User ចុចវាយអក្សរ */
input:focus,
textarea:focus,
select:focus {
  outline: none;
  border-color: #3b82f6;
  box-shadow: 0 0 0 4px rgba(59, 130, 246, 0.15); /* Modern Focus Ring */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Forms Styling Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
      padding: 40px;
    }

    .form-card {
      max-width: 400px;
      margin: 0 auto;
      background: #ffffff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
    }

    .form-title {
      margin-top: 0;
      color: #0f172a;
      text-align: center;
    }

    .form-group {
      margin-bottom: 18px;
    }

    label {
      display: block;
      margin-bottom: 6px;
      font-size: 14px;
      font-weight: 600;
      color: #334155;
    }

    input[type="text"],
    input[type="email"] {
      width: 100%;
      padding: 10px 14px;
      border: 1.5px solid #cbd5e1;
      border-radius: 6px;
      box-sizing: border-box;
      font-size: 14px;
      transition: border-color 0.2s, box-shadow 0.2s;
    }

    input:focus {
      outline: none;
      border-color: #2563eb;
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
    }

    .btn-submit {
      width: 100%;
      background-color: #2563eb;
      color: white;
      padding: 12px;
      font-size: 16px;
      font-weight: bold;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.2s;
    }

    .btn-submit:hover {
      background-color: #1d4ed8;
    }
  </style>
</head>
<body>

  <div class="form-card">
    <h2 class="form-title">ចុះឈ្មោះគណនី</h2>
    <form>
      <div class="form-group">
        <label for="fullname">ឈ្មោះពេញ</label>
        <input type="text" id="fullname" placeholder="ឧ. សុខ សាន្ត">
      </div>

      <div class="form-group">
        <label for="email">អ៊ីមែល</label>
        <input type="email" id="email" placeholder="example@mail.com">
      </div>

      <button type="submit" class="btn-submit">បង្កើតគណនី</button>
    </form>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **`box-sizing: border-box;`:** បើគ្មាន `border-box` ទេ នៅពេលដាក់ `width: 100%;` រួមជាមួយ `padding: 12px;` នោះ Input នឹងលៀនហៀរចេញក្រៅ Form Card ភ្លាម។
* ✅ **កុំភ្លេច `label` Associated ID:** ត្រូវដាក់ `<label for="inputId">` ជានិច្ច ដើម្បីឱ្យពេល User ចុចលើអក្សរ Label វានឹង Focus ចូល Input ដោយស្វ័យប្រវត្តិ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Login Card មាន Input Email, Password និងប៊ូតុង Submit។
2. ដាក់ Focus Glow Ring ពណ៌បៃតង (`rgba(16, 185, 129, 0.2)`) នៅពេល Focus។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Set `box-sizing: border-box` to ensure padding and border stay within the input width.
* Use `:focus` to provide modern outline rings with `box-shadow: 0 0 0 3px rgba(...)`.
* Connect labels to inputs via `for` and `id` attributes for improved user experience and accessibility.
</details>
