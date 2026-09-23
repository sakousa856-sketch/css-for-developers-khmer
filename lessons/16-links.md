# មេរៀនទី ១៦៖ ការកំណត់ Style លើ Link (CSS Links)

> **CSS អនុញ្ញាតឱ្យយើងកំណត់ Style លើតំណភ្ជាប់ `<a>` តាមរយៈ State ទាំង ៤៖ `:link`, `:visited`, `:hover` និង `:active`។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ស្គាល់ Link States ទាំង ៤ និងលំដាប់ច្បាប់ **LVHA**
* ចេះលុបបន្ទាត់ក្រោម Link (`text-decoration: none`)
* ចេះបម្លែង Link ឱ្យក្លាយជាប៊ូតុងដ៏ទាក់ទាញ (Button-styled Links)

---

## 🔗 Link States ទាំង ៤ នៃ `<a>`

1. **`a:link`:** តំណភ្ជាប់ធម្មតាដែលមិនទាន់មាននរណាចុចចូលមើល
2. **`a:visited`:** តំណភ្ជាប់ដែលអ្នកប្រើប្រាស់ធ្លាប់បានចុចចូលមើលរួចហើយ
3. **`a:hover`:** នៅពេលអ្នកប្រើប្រាស់ដាក់ Mouse Cursor ពីលើ Link
4. **`a:active`:** ក្នុងខណៈពេលដែលអ្នកប្រើប្រាស់កំពុងចុចសង្កត់លើ Link

---

## 📜 ច្បាប់លំដាប់ LVHA (The LVHA Rule)

ដើម្បីឱ្យ CSS Link States ដំណើរការត្រឹមត្រូវ 100% អ្នក **ត្រូវតែសរសេរតាមលំដាប់លំដោយ LVHA ជានិច្ច**៖

$$\mathbf{L}\text{ (:link)} \longrightarrow \mathbf{V}\text{ (:visited)} \longrightarrow \mathbf{H}\text{ (:hover)} \longrightarrow \mathbf{A}\text{ (:active)}$$

```css
/* 1. Link */
a:link {
  color: #2563eb;
  text-decoration: none;
}

/* 2. Visited */
a:visited {
  color: #7c3aed;
}

/* 3. Hover */
a:hover {
  color: #1d4ed8;
  text-decoration: underline;
}

/* 4. Active */
a:active {
  color: #dc2626;
}
```

---

## 🔘 ការបម្លែង Link ទៅជាប៊ូតុង (Link as a Button)

```css
a.button-link {
  display: inline-block;
  background-color: #2563eb;
  color: #ffffff;
  padding: 12px 24px;
  text-decoration: none;
  font-weight: 600;
  border-radius: 6px;
  transition: all 0.2s ease;
}

a.button-link:hover {
  background-color: #1d4ed8;
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(37, 99, 235, 0.3);
}

a.button-link:active {
  transform: translateY(0);
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Links Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    /* Custom Text Link */
    .custom-link {
      color: #0284c7;
      text-decoration: none;
      font-weight: 500;
      border-bottom: 2px solid transparent;
      transition: border-color 0.2s ease;
    }

    .custom-link:hover {
      border-bottom-color: #0284c7;
    }

    /* Button Link */
    .btn-primary {
      display: inline-block;
      margin-top: 15px;
      background-color: #0f172a;
      color: white;
      text-decoration: none;
      padding: 10px 20px;
      border-radius: 6px;
      transition: background-color 0.2s;
    }

    .btn-primary:hover {
      background-color: #334155;
    }
  </style>
</head>
<body>

  <p>ស្វែងយល់បន្ថែមតាមរយៈ <a href="#" class="custom-link">ឯកសារណែនាំផ្លូវការ</a> របស់យើង។</p>

  <a href="#" class="btn-primary">បង្កើតគណនីថ្មី</a>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ❌ **សរសេរខុសលំដាប់ LVHA:** បើអ្នកសរសេរ `:hover` មុន `:link` នោះពេល Hover វានឹងមិនផ្លាស់ប្តូរពណ៌ឡើយ ព្រោះត្រូវ Rule `:link` Override ជាន់ពីលើ។
* ✅ **Accessibility:** កុំប្តូរពណ៌ Link ឱ្យដូចនឹងពណ៌អត្ថបទធម្មតាពេក ព្រោះអ្នកប្រើប្រាស់នឹងមិនដឹងថាជាតំណភ្ជាប់អាចចុចបានឡើយ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតតំណភ្ជាប់ `<a>` មួយដែលមាន `text-decoration: none;`។
2. ពេល `:hover` ឱ្យមាន `background-color: #dbeafe; color: #1e40af; border-radius: 4px;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The four links states are: `a:link`, `a:visited`, `a:hover`, `a:active`.
* Always follow the LVHA order: `a:link` MUST come before `a:visited`, `a:hover` MUST come after `a:link` and `a:visited`, and `a:active` MUST come after `a:hover`.
* Links can be styled as buttons using `display: inline-block`, `padding`, and `border-radius`.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>16</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>១៦</strong> នៃ <strong>៦០</strong></p>

| [← Prev](15-icons.md) | [01](01-introduction.md) | ... | [14](14-fonts.md) | [15](15-icons.md) | **[ 16 ]** | [17](17-lists.md) | [18](18-tables.md) | ... | [60](60-modern-features.md) | [Next →](17-lists.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
