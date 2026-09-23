# មេរៀនទី ៤៧៖ RWD: Responsive Images & Media

> **រូបភាព និងវីដេអូដែលមិនមែនជា Responsive គឺជាមូលហេតុចម្បងដែលធ្វើឱ្យប្លង់គេហទំព័រហៀរធ្លាយ (Overflow) លើទូរស័ព្ទដៃ។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះធ្វើឱ្យរូបភាពបត់បែនស្វ័យប្រវត្តិ (`max-width: 100%; height: auto;`)
* ចេះគ្រប់គ្រងសមាមាត្ររូបភាពតាម `object-fit` និង `object-position`
* ចេះប្រើប្រាស់ **`aspect-ratio`** ទំនើបសម្រាប់វីដេអូ និងកាត (16/9, 1/1, 4/3)

---

## 🖼️ ១. រូបមន្ត Responsive Image ស្តង់ដារ

```css
img {
  max-width: 100%; /* ការពារកុំឱ្យរូបភាពរីកហៀរចេញក្រៅ Parent Container */
  height: auto;    /* រក្សាសមាមាត្រកម្ពស់ដើម (Aspect Ratio) កុំឱ្យសំប៉ែត */
  display: block;
}
```

---

## 📐 ២. `object-fit` (គ្រប់គ្រងរូបភាពក្នុង Fixed Container)

នៅពេលយើងកំណត់ទំហំប្រអប់រាងថេរ (ឧ. កាត Avatar `80px x 80px` ឬ Product Cover `300px x 200px`)៖
* `object-fit: cover;` ➔ ពង្រីករូបភាពឱ្យពេញប្រអប់ ដោយរក្សាសមាមាត្រ (កាត់គែមលើសចោល) ⭐
* `object-fit: contain;` ➔ បង្ហាញរូបភាពទាំងមូលឱ្យឃើញគ្រប់ជ្រុងក្នុងប្រអប់
* `object-fit: fill;` (Default) ➔ ទាញពង្រីករូបភាពឱ្យពេញប្រអប់ (បណ្តាលឱ្យរូបភាពខូចសំប៉ែត)

```css
.card-thumbnail {
  width: 100%;
  height: 220px;
  object-fit: cover; /* រូបភាពស្អាតជានិច្ច មិនខូចសមាមាត្រ */
  object-position: center;
}
```

---

## 🎬 ៣. `aspect-ratio` ទំនើប (សមាមាត្រវីដេអូ និងរូបភាព)

ជំនួសឱ្យ Padding Hack បុរាណ យើងអាចកំណត់សមាមាត្រផ្ទាល់បានយ៉ាងងាយ៖

```css
/* សមាមាត្រ 16:9 សម្រាប់ YouTube Video ឬ Hero Banner */
.video-wrapper {
  width: 100%;
  aspect-ratio: 16 / 9;
}

/* សមាមាត្រ 1:1 សម្រាប់ Instagram Square Photo */
.square-avatar {
  width: 120px;
  aspect-ratio: 1 / 1;
  border-radius: 50%;
  object-fit: cover;
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
  <title>Responsive Media Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f8fafc;
    }

    .media-card {
      max-width: 450px;
      margin: 0 auto;
      background: white;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    }

    .media-card img {
      width: 100%;
      aspect-ratio: 16 / 9;
      object-fit: cover;
      display: block;
    }

    .card-body {
      padding: 20px;
    }
  </style>
</head>
<body>

  <div class="media-card">
    <img src="../assets/images/hero-bg-nature.jpg" alt="Landscape">
    <div class="card-body">
      <h3>ទេសភាពធម្មជាតិស្រស់បំព្រង</h3>
      <p>រូបភាពនេះត្រូវបានកំណត់ <code>aspect-ratio: 16 / 9</code> និង <code>object-fit: cover</code> ធានាសោភ័ណភាពស្អាតនៅលើគ្រប់ឧបករណ៍។</p>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **Global Reset:** តែងតែដាក់ `img, video { max-width: 100%; height: auto; }` ក្នុង Base CSS របស់អ្នកជានិច្ច ដើម្បីធានាថារូបភាពទាំងអស់ក្នុងគេហទំព័រនឹង Responsive ដោយស្វ័យប្រវត្តិ។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើតប្រអប់រូបភាពមួយដែលមាន `width: 300px; aspect-ratio: 1 / 1;` និង `object-fit: cover; border-radius: 50%;`។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* Responsive images will automatically adjust to fit the size of the screen (`max-width: 100%; height: auto;`).
* `object-fit: cover` clips the image to fit its container while preserving its aspect ratio.
* Modern `aspect-ratio: 16 / 9` easily creates video or banner proportions without old padding hacks.
</details>
