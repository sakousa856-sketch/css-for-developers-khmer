# មេរៀនទី ៣៣៖ ជម្រើសតាមលក្ខណៈសម្បត្តិ (CSS Attribute Selectors)

> **CSS Attribute Selectors ប្រើសម្រាប់រើស Element ណាដែលមាន HTML Attribute ឬតម្លៃ Value ជាក់លាក់។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះជ្រើសរើស Elements តាមឈ្មោះ Attribute
* ចេះជ្រើសរើសតាមលំនាំអក្សរ (Starts with, Ends with, Contains)
* យល់ពីការប្រើប្រាស់ជាក់ស្តែងសម្រាប់ Styling Form Inputs និង File Links

---

## 🔍 បណ្តា Attribute Selectors ទាំង ៦ ប្រភេទ

| Selector | ឧទាហរណ៍ | អត្ថន័យ |
| :---: | :--- | :--- |
| `[attribute]` | `a[target]` | រើសរាល់ `<a>` ណាដែលមាន attribute `target` |
| `[attribute="value"]` | `input[type="text"]` | រើសតែ `<input>` ណាដែលមាន `type` ស្មើនឹង `"text"` ប៉ះបិទ |
| `[attribute~="value"]` | `[title~="flower"]` | រើស Elements ដែល attribute មានពាក្យ `"flower"` ជាពាក្យដាច់ដោយឡែក |
| `[attribute^="value"]` | `a[href^="https"]` | រើសរាល់ Link ណាដែល **ចាប់ផ្តើមដោយ** `"https"` (Secure external links) |
| `[attribute$="value"]` | `a[href$=".pdf"]` | រើសរាល់ Link ណាដែល **បញ្ចប់ដោយ** `".pdf"` (PDF Download links) |
| `[attribute*="value"]` | `a[href*="google"]` | រើសរាល់ Link ណាដែល **មានពាក្យ** `"google"` នៅកន្លែងណាក៏បាន |

---

## 🛠️ ការប្រើប្រាស់ជាក់ស្តែងក្នុងពិភពពិត

### ១. Styling លើ Form Inputs ដាច់ដោយឡែកពីគ្នា
```css
/* Text & Email Inputs */
input[type="text"],
input[type="email"],
input[type="password"] {
  width: 100%;
  padding: 10px 14px;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
}

/* Submit Button */
input[type="submit"] {
  background-color: #2563eb;
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}
```

---

### ២. បន្ថែម Icon ស្វ័យប្រវត្តិតាមប្រភេទ File Link
```css
/* បន្ថែម Icon PDF ពីមុខ link ណាដែលទាញយកឯកសារ PDF */
a[href$=".pdf"]::before {
  content: "📄 ";
}

/* បន្ថែម Icon External លើ Link ណាដែលចេញទៅគេហទំព័រខាងក្រៅ */
a[href^="https://"]::after {
  content: " ↗";
  font-size: 12px;
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Attribute Selectors Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .form-group {
      margin-bottom: 15px;
      max-width: 320px;
    }

    /* Style only specific input types */
    input[type="text"], input[type="email"] {
      width: 100%;
      padding: 8px 12px;
      border: 1px solid #94a3b8;
      border-radius: 4px;
      box-sizing: border-box;
    }

    /* Links with PDF */
    a[href$=".pdf"] {
      color: #dc2626;
      font-weight: bold;
      text-decoration: none;
    }

    a[href$=".pdf"]::before {
      content: "📕 ";
    }
  </style>
</head>
<body>

  <h3>1. Form Styling with Attribute Selectors</h3>
  <div class="form-group">
    <input type="text" placeholder="ឈ្មោះពេញ...">
  </div>
  <div class="form-group">
    <input type="email" placeholder="អ៊ីមែល...">
  </div>

  <h3>2. File Download Links</h3>
  <p><a href="handbook.pdf">ទាញយកសៀវភៅណែនាំ (PDF)</a></p>
  <p><a href="https://example.com" target="_blank">ទៅកាន់គេហទំព័រដៃគូ</a></p>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Case-Insensitive Attribute Selector:** បន្ថែមអក្សរ `i` នៅខាងក្នុងវង់ក្រចក `[href$=".pdf" i]` ដើម្បីឱ្យវាដំណើរការទាំងកន្ទុយ `.pdf` និង `.PDF` (អក្សរធំ)។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. សរសេរ CSS Rule ដោយប្រើ `a[target="_blank"]` ដើម្បីកំណត់ឱ្យតំណភ្ជាប់ដែលបើក Tab ថ្មីមាន `color: #ea580c;`។
2. កំណត់ `input[disabled]` ឱ្យមាន `background-color: #e2e8f0; cursor: not-allowed;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* `[attribute]` selector targets elements with a specified attribute.
* `[attribute="value"]` matches exact value.
* `[attribute^="value"]` matches values starting with the specified string.
* `[attribute$="value"]` matches values ending with the specified string.
* `[attribute*="value"]` matches values containing the specified substring.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>33</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>៣៣</strong> នៃ <strong>៦០</strong></p>

| [← Prev](32-image-gallery.md) | [01](01-introduction.md) | ... | [31](31-dropdowns.md) | [32](32-image-gallery.md) | **[ 33 ]** | [34](34-forms-styling.md) | [35](35-counters.md) | ... | [60](60-modern-features.md) | [Next →](34-forms-styling.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
