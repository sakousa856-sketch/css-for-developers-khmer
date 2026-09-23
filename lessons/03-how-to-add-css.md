# មេរៀនទី ០៣៖ របៀបភ្ជាប់ CSS ទៅកាន់ HTML (How to Add CSS)

> **CSS អាចបញ្ចូលទៅកាន់ឯកសារ HTML បានតាម ៣ របៀប៖ External, Internal និង Inline។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះវិធីទាំង ៣ ក្នុងការបញ្ចូល CSS ទៅកាន់ HTML
* ស្គាល់គុណសម្បត្តិ និងគុណវិបត្តិនៃវិធីនីមួយៗ
* យល់ដឹងពីលំដាប់អានុភាពនៃការជាន់គ្នា (Cascading Order)

---

## 🛠️ វិធីទាំង ៣ ក្នុងការបញ្ចូល CSS

### ១. External CSS (ឯកសារ CSS ខាងក្រៅ - និយមប្រើបំផុត)
សរសេរកូដ CSS នៅក្នុង file ដាច់ដោយឡែកដែលមានកន្ទុយ `.css` ហើយភ្ជាប់មកកាន់ HTML ដោយប្រើ `<link>` tag នៅក្នុងផ្នែក `<head>`៖

**File: `style.css`**
```css
body {
  background-color: #f8fafc;
  font-family: sans-serif;
}

h1 {
  color: #0284c7;
}
```

**File: `index.html`**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>External CSS</title>
  <!-- ភ្ជាប់ External CSS -->
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>ទំព័រប្រើប្រាស់ External CSS</h1>
</body>
</html>
```

* **គុណសម្បត្តិ:** កូដស្អាត ងាយស្រួល Maintain អាចប្រើ Share រវាងទំព័រច្រើនបាន និងធ្វើឱ្យ Browser ជួយ Cache លឿន។

---

### ២. Internal CSS (សរសេរក្នុងទំព័រ HTML)
សរសេរកូដ CSS នៅក្នុង `<style>` tag ស្ថិតក្នុងផ្នែក `<head>` នៃឯកសារ HTML តែម្តង៖

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Internal CSS</title>
  <style>
    body {
      background-color: #fefce8;
    }
    p {
      color: #854d0e;
    }
  </style>
</head>
<body>
  <p>ទំព័រនេះប្រើប្រាស់ Internal CSS</p>
</body>
</html>
```

* **ពេលណាគួរប្រើ:** ស័ក្តិសមសម្រាប់ទំព័រណាដែលមាន Style ពិសេសតែមួយ (Single-page styling) មិនចង់ Share ជាមួយទំព័រផ្សេង។

---

### ៣. Inline CSS (សរសេរផ្ទាល់លើ Tag)
សរសេរកូដ CSS ផ្ទាល់នៅក្នុង attribute `style` នៃ HTML element នីមួយៗ៖

```html
<h1 style="color: #dc2626; text-align: center; font-size: 32px;">
  ចំណងជើង Inline Style
</h1>
<p style="background-color: #fef08a; padding: 10px;">
  កថាខណ្ឌនេះមាន Inline Style ផ្ទាល់។
</p>
```

* **គុណវិបត្តិ:** ធ្វើឱ្យកូដ HTML រញ៉េរញ៉ៃ ពិបាកកែប្រែពេលមាន elements ច្រើន។
* **ពេលណាគួរប្រើ:** ប្រើពេលតេស្តកូដលឿនៗ ឬពេលចង់ Override Style ណាមួយជាបន្ទាន់។

---

## 🌊 លំដាប់អានុភាពនៃការអនុវត្ត (Cascading Order / Priority)

នៅពេលដែល element មួយត្រូវបានកំណត់ Style ជាន់គ្នាពីប្រភពផ្សេងៗ Browser នឹងជ្រើសរើស Style មកបង្ហាញតាមលំដាប់អានុភាព (ពីខ្ពស់ទៅទាប)៖

![CSS Cascade Flow](https://raw.githubusercontent.com/sakousa856-sketch/css-for-developers-khmer/main/assets/css-cascade-flow.svg)

1. **Inline Style** (អានុភាពខ្ពស់បំផុតក្នុងចំណោមទាំង ៣ ព្រោះស្ថិតនៅជិត Tag ផ្ទាល់)
2. **External និង Internal Style Sheets** (ស្ថិតក្នុង `<head>`) — កូដណាដែលសរសេរនៅ **ក្រោមគេ** នឹងឈ្នះ (The last rule declared wins)
3. **Browser Default Style** (ស្ទីលលំនាំដើមរបស់ Browser ដូចជា Google Chrome, Safari)

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Best Practice:** ប្រើ **External CSS** ជានិច្ចសម្រាប់ Project ពិតប្រាកដ ដើម្បីរក្សាគោលការណ៍ *Separation of Concerns*។
* ❌ **Pitfall:** ភ្លេចដាក់ `rel="stylesheet"` ក្នុង `<link>` tag ធ្វើឱ្យ Browser មិនព្រម Render CSS។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត file ពីរ៖ `index.html` និង `custom.css` ក្នុង folder តែមួយ។
2. ក្នុង `custom.css` កំណត់ `h2` ឱ្យមាន `color: navy;`។
3. ភ្ជាប់ `custom.css` ទៅកាន់ `index.html` តាមរយៈ `<link>` tag ហើយសាកល្បងបើកលើ Browser។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Three ways to insert CSS: External, Internal, Inline.
* External CSS is defined in a separate `.css` file and linked with `<link rel="stylesheet" href="...">`.
* Internal CSS is defined inside the `<style>` element inside `<head>`.
* Inline CSS is defined via the `style` attribute inside HTML elements.
* Inline styles have the highest priority among the three insertion methods.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>3</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>០៣</strong> នៃ <strong>៦០</strong></p>

| [← Prev](02-syntax-and-selectors.md) | [01](01-introduction.md) | [02](02-syntax-and-selectors.md) | **[ 03 ]** | [04](04-comments.md) | [05](05-colors.md) | ... | [60](60-modern-features.md) | [Next →](04-comments.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
