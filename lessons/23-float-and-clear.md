# មេរៀនទី ២៣៖ ការបណ្តែតធាតុ (CSS Float & Clear)

> **CSS `float` ប្រើសម្រាប់រុញបណ្តែត Element ទៅឆ្វេង ឬស្តាំ ដើម្បីឱ្យអត្ថបទរត់ព័ទ្ធជុំវិញវា (ដូចក្នុងទំព័រកាសែត)។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* យល់ពីរបៀបប្រើ `float: left` និង `float: right`
* យល់ពីបញ្ហា "Parent Collapse" នៅពេលកូនប្រើ Float
* ចេះដោះស្រាយបញ្ហាដោយប្រើ `clear: both` និងរូបមន្តទំនើប **The Clearfix Hack**

---

## 🌊 របៀបប្រើ CSS Float

```css
img.avatar-left {
  float: left;
  margin-right: 15px;
  margin-bottom: 10px;
}

img.avatar-right {
  float: right;
  margin-left: 15px;
  margin-bottom: 10px;
}
```

---

## 💥 បញ្ហា Parent Height Collapse (Parent រួញបាត់កម្ពស់)

នៅពេលដែល elements ខាងក្នុងទាំងអស់ប្រើ `float` ពួកវានឹងរបូតចេញពី Normal Flow ធ្វើឱ្យ **Parent Container បាត់បង់កម្ពស់ (Height = 0px)** ហាក់ដូចជាគ្មានកូននៅខាងក្នុងអញ្ចឹង។

### 🛠️ ដំណោះស្រាយ៖ The Modern Clearfix Hack
យើងត្រូវប្រើ Pseudo-element `::after` លើ Parent Container ដើម្បី Clear កូនៗដែល Float៖

```css
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

*(ឬដំណោះស្រាយទំនើបខ្លីមួយទៀតគឺដាក់ `display: flow-root;` ឬ `overflow: auto;` លើ Parent)*

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Float Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    /* Modern Clearfix */
    .article-card::after {
      content: "";
      display: table;
      clear: both;
    }

    .article-card {
      background: white;
      border: 1px solid #cbd5e1;
      padding: 20px;
      border-radius: 8px;
      max-width: 600px;
    }

    .float-image {
      float: left;
      width: 140px;
      height: 100px;
      object-fit: cover;
      margin-right: 15px;
      margin-bottom: 10px;
      border-radius: 6px;
    }
  </style>
</head>
<body>

  <div class="article-card">
    <img class="float-image" src="../assets/images/article-tech.jpg" alt="Tech Article">
    <h3>ចំណងជើងអត្ថបទបច្ចេកវិទ្យា</h3>
    <p>
      ការប្រើប្រាស់ Float អនុញ្ញាតឱ្យរូបភាពបណ្តែតនៅខាងឆ្វេង ហើយអត្ថបទទាំងអស់នេះរត់ព័ទ្ធជុំវិញរូបភាពយ៉ាងស្អាត។ ជាមួយ Clearfix Hack នោះ Parent Card នឹងមិនរួមរួញបាត់កម្ពស់ឡើយ។
    </p>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* 💡 **Modern Layout Note:** សព្វថ្ងៃនេះ **Flexbox និង Grid** ត្រូវបានយកមកប្រើជំនួស Float សម្រាប់ការរៀបចំប្លង់ទូទៅ (Page Layouts) ព្រោះវាស្រួលជាង និងគ្មានបញ្ហា Clearfix។ យើងប្រើ `float` តែក្នុងករណី **រុញរូបភាពឱ្យអត្ថបទរត់ព័ទ្ធជុំវិញ** ប៉ុណ្ណោះ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតកថាខណ្ឌមួយដែលមានរូបភាព `<img>` មួយនៅខាងក្នុង។
2. កំណត់ `float: right; margin-left: 15px;` លើរូបភាព ហើយសង្កេតមើលរបៀបដែលអត្ថបទរត់ព័ទ្ធជុំវិញ។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* The `float` property specifies whether an element should float to the left, right, or not at all.
* Floating elements are taken out of the normal flow, causing parent collapse.
* The Clearfix Hack (`::after { content: ""; display: table; clear: both; }`) prevents the parent from collapsing.
* For full page layouts, prefer Flexbox or CSS Grid over Float.
</details>

---

<div align="center">

### 🧭 ការរុករកមេរៀន (Lesson Pagination)

<p>Showing Lesson <strong>23</strong> of <strong>60</strong> &nbsp;•&nbsp; មេរៀនទី <strong>២៣</strong> នៃ <strong>៦០</strong></p>

| [← Prev](22-overflow.md) | [01](01-introduction.md) | ... | [21](21-position.md) | [22](22-overflow.md) | **[ 23 ]** | [24](24-inline-block.md) | [25](25-align.md) | ... | [60](60-modern-features.md) | [Next →](24-inline-block.md) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |

<br/>

[🏠 ត្រឡប់ទៅមាតិការួម (Table of Contents)](../README.md)

</div>
