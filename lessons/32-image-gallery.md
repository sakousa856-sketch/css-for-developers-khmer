# មេរៀនទី ៣២៖ វិចិត្រសាលរូបភាព និង Image Sprites (CSS Image Gallery & Sprites)

> **CSS ជួយឱ្យយើងបង្កើត Image Gallery ដែលមានរបៀបរៀបរយស្អាត និងការប្រើប្រាស់ CSS Image Sprites ដើម្បីកាត់បន្ថយ HTTP Requests។**

---

## 🎯 គោលបំណងមេរៀន (What You Will Learn)
* ចេះបង្កើត Responsive Image Gallery ជាមួយ Hover Zoom Effect
* យល់ដឹងពីបច្ចេកទេស **CSS Image Sprites** និងអត្ថប្រយោជន៍លើ Performance
* ចេះប្រើ `background-position` ដើម្បីបង្ហាញ Icon នីមួយៗចេញពីរូបភាព Sprite រួម

---

## 🖼️ ១. ការបង្កើត Modern Image Gallery

```css
.gallery-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.gallery-item {
  flex: 1 1 250px; /* Responsive Flex Basis */
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  background: white;
}

.gallery-item img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
  transition: transform 0.3s ease;
}

.gallery-item:hover img {
  transform: scale(1.08); /* Zoom effect ពេល Hover */
}
```

---

## 🚀 ២. CSS Image Sprites ជាអ្វី? (Performance Optimization)

**Image Sprite** គឺជាការប្រមូលផ្តុំរូបភាពតូចៗ ឬ Icons ជាច្រើនបញ្ចូលគ្នាក្នុង **រូបភាពធំតែមួយ (Single Combined Image File)**។

### អត្ថប្រយោជន៍៖
* បើអ្នកមាន Icon ចំនួន 10 ដាច់ដោយឡែកពីគ្នា Browser ត្រូវផ្ញើ **10 HTTP Requests** ទៅកាន់ Server។
* ជាមួយ Sprite Sheet មួយ Browser ផ្ញើតែ **1 HTTP Request** ប៉ុណ្ណោះ ដែលជួយឱ្យគេហទំព័រ Load លឿនជាងមុនខ្លាំង!

### របៀបប្រើប្រាស់៖
យើងគ្រាន់តែផ្លាស់ប្តូរ `background-position` (អ័ក្ស X និង Y) ដើម្បីចង្អុលបង្ហាញតែផ្នែកនៃ Icon ណាដែលយើងចង់បាន៖

```css
.icon {
  width: 32px;
  height: 32px;
  background-image: url("icons-sprite.png");
  display: inline-block;
}

.icon-home {
  background-position: 0 0; /* Icon ទីមួយ */
}

.icon-next {
  background-position: -32px 0; /* រំកិលទៅ Icon ទីពីរ */
}
```

---

## 💻 ឧទាហរណ៍កូដជាក់ស្តែង (HTML + CSS)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Image Gallery Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f1f5f9;
    }

    .gallery-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      max-width: 900px;
      margin: 0 auto;
    }

    .gallery-card {
      background: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    }

    .img-wrapper {
      overflow: hidden;
    }

    .gallery-card img {
      width: 100%;
      height: 160px;
      object-fit: cover;
      display: block;
      transition: transform 0.4s ease;
    }

    .gallery-card:hover img {
      transform: scale(1.1);
    }

    .card-caption {
      padding: 12px;
      font-size: 14px;
      color: #334155;
      text-align: center;
      font-weight: 500;
    }
  </style>
</head>
<body>

  <h2 style="text-align: center; margin-bottom: 25px;">វិចិត្រសាលរូបភាពទេសចរណ៍</h2>

  <div class="gallery-container">
    <div class="gallery-card">
      <div class="img-wrapper">
        <img src="../assets/images/gallery-beach.jpg" alt="Beach">
      </div>
      <div class="card-caption">ឆ្នេរសមុទ្រស្អាត</div>
    </div>

    <div class="gallery-card">
      <div class="img-wrapper">
        <img src="../assets/images/gallery-mountain.jpg" alt="Mountain">
      </div>
      <div class="card-caption">ភ្នំខ្ពស់ត្រដែត</div>
    </div>

    <div class="gallery-card">
      <div class="img-wrapper">
        <img src="../assets/images/gallery-forest.jpg" alt="Forest">
      </div>
      <div class="card-caption">ព្រៃឈើខៀវស្រងាត់</div>
    </div>
  </div>

</body>
</html>
```

---

## ⚠️ ចំណុចគួរប្រយ័ត្ន & Best Practices (Common Pitfalls & Tips)
* ✅ **ប្រើ `object-fit: cover` ជានិច្ច:** រូបភាពដែល Upload មកអាចមានទំហំទទឹង និងបណ្តោយខុសៗគ្នា។ ការដាក់ `object-fit: cover;` ការពារកុំឱ្យរូបភាពខូចសមាមាត្រ (Stretched or distorted)។

---

## ✍️ លំហាត់អនុវត្តសាកល្បង (Mini Practice)
1. បង្កើត Responsive Image Grid មាន ៣ Cards។
2. ដាក់ `overflow: hidden;` លើ Wrapper ហើយធ្វើឱ្យរូបភាព Zoom In ពេល Hover។

---

<details>
<summary>📄 English Summary & Key Takeaways</summary>

* An image gallery can easily be built with modern CSS Grid or Flexbox.
* Use `object-fit: cover` to preserve image aspect ratios inside fixed-dimension containers.
* An image sprite is a collection of images put into a single image.
* Sprites reduce the number of server requests and save bandwidth.
</details>
