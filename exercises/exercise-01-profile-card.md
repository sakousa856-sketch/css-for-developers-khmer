# លំហាត់អនុវត្តទី ០១៖ បង្កើត Profile Card Component

## 🎯 គោលបំណង (Objective)
អនុវត្តចំណេះដឹងពី **CSS Box Model, Borders, Shadows, និង Google Fonts** ដើម្បីបង្កើតកាតព័ត៌មានផ្ទាល់ខ្លួន (Profile Card)។

---

## 📋 លក្ខខណ្ឌតម្រូវ (Requirements)
1. **Container:** ទទឹងអតិបរមា `320px`, ផ្ទៃក្រោយពណ៌ស, ជ្រុងមូល `16px`, មាន Soft Shadow ស្អាត។
2. **Avatar Image:** រូបរាងរង្វង់មូល (`border-radius: 50%`), ទំហំ `96px x 96px`, មាន Border ពណ៌ខៀវ `3px solid #3b82f6`។
3. **Typography:** ចំណងជើងឈ្មោះ Bold `20px`, តួនាទីការងារ (Job Title) ពណ៌ប្រផេះ `14px`។
4. **Follow Button:** ផ្ទៃពណ៌ខៀវ `#2563eb`, ជ្រុងមូល `8px`, មាន Hover Transition ឡើងលើ `-2px` និងចេញ Shadow។

---

## 💡 ចម្លើយគំរូ (Solution Key)

<details>
<summary>👉 ចុចទីនេះដើម្បីមើលកូដចម្លើយគំរូ</summary>

```html
<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <title>Profile Card Solution</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f5f9;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      margin: 0;
    }

    .profile-card {
      width: 100%;
      max-width: 320px;
      background: #ffffff;
      padding: 30px 24px;
      border-radius: 16px;
      box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.08);
      text-align: center;
    }

    .avatar {
      width: 96px;
      height: 96px;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid #3b82f6;
      margin-bottom: 16px;
    }

    .name {
      font-size: 20px;
      color: #0f172a;
      margin: 0 0 6px 0;
    }

    .title {
      font-size: 14px;
      color: #64748b;
      margin: 0 0 20px 0;
    }

    .btn-follow {
      width: 100%;
      background-color: #2563eb;
      color: white;
      border: none;
      padding: 12px;
      font-size: 15px;
      font-weight: 600;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    .btn-follow:hover {
      background-color: #1d4ed8;
      transform: translateY(-2px);
      box-shadow: 0 6px 15px rgba(37, 99, 235, 0.3);
    }
  </style>
</head>
<body>

  <div class="profile-card">
    <img class="avatar" src="../assets/images/avatar-user.jpg" alt="Avatar">
    <h3 class="name">សុខ វិច្ឆិកា</h3>
    <p class="title">Senior Frontend Developer</p>
    <button class="btn-follow">Follow +</button>
  </div>

</body>
</html>
```
</details>
