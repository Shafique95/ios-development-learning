

# 📱 Flutter iOS অ্যাপ পাবলিশ গাইড (App Store)

এই গাইডটি Flutter iOS অ্যাপ App Store-এ পাবলিশ করার জন্য প্রয়োজনীয় ধাপগুলো প্রায়োরিটি ভিত্তিতে সাজানো হয়েছে।

---

## ✅ প্রাথমিক কাজ (Must Do First)

### 1. 🎫 Apple Developer Program সাবস্ক্রিপশন করুন

* লিংক: [Apple Developer Program](https://developer.apple.com/programs/)
* খরচ: **\$99/বছর**
* **অ্যাপ পাবলিশ করার জন্য বাধ্যতামূলক**

### 2. 🛠 Xcode ইনস্টল ও সেটআপ

* Mac-এ সর্বশেষ [Xcode](https://developer.apple.com/xcode/) ইনস্টল করুন
* Xcode → `Preferences` → `Accounts` → আপনার Apple ID যুক্ত করুন

### 3. 📦 Flutter প্রোজেক্টে Bundle Identifier ঠিক করুন

```bash
ios/Runner.xcodeproj অথবা ios/Runner.xcworkspace ওপেন করুন
```

* Example: `com.yourcompany.yourapp`

### 4. 🔐 Automatically Manage Signing চালু করুন

Xcode → Runner Target → `Signing & Capabilities` → `Team` নির্বাচন → ✅ Auto-signing চালু

---

## 🚀 বিল্ড ও আপলোড (Build & Upload)

### 5. 🧱 Flutter iOS Release Build তৈরি করুন

```bash
flutter clean
flutter pub get
flutter build ios --release
```

### 6. 📤 Xcode থেকে অ্যাপ আর্কাইভ ও আপলোড

Xcode → `Product` → `Archive` → `Distribute App` → `App Store Connect` → `Upload`

---

## 📝 App Store Connect-এ তথ্য পূরণ

### 7. 📲 App তৈরি করুন

* [App Store Connect](https://appstoreconnect.apple.com) → `My Apps` → ➕ `New App`
* `Bundle ID` নির্বাচন করুন

### 8. 🏷 মৌলিক তথ্য

* **App Name** (ইউনিক)
* **Primary Language**
* **SKU Number** (ইউনিক আইডি স্ট্রিং)

### 9. 💵 প্রাইসিং ও উপলব্ধতা

* Free / Paid নির্বাচন
* Country Availability সেট করুন

### 10. 📋 App Store Listing তথ্য

* **Description**
* **Keywords**
* **Subtitle**
* **Support URL**
* **Marketing URL (ঐচ্ছিক)**

### 11. 🔐 Privacy Policy URL

* ইউজার ডেটা সংগ্রহ করলে অবশ্যই দিতে হবে

### 12. 👶 Age Rating ফর্ম পূরণ

* কন্টেন্ট অনুযায়ী বয়স নির্বাচন করুন

### 13. 🖼 স্ক্রিনশট ও আইকন আপলোড

* বিভিন্ন iPhone ও iPad সাইজে স্ক্রিনশট দিন
* App icon অবশ্যই Xcode-এ ঠিকভাবে যুক্ত থাকতে হবে

---

## ✅ রিভিউ প্রস্তুতি (Submit for Review)

### 14. 🚦 Build নির্বাচন ও সাবমিট

* Build সিলেক্ট করুন → ✅ `Submit for Review`

### 15. 📞 রিভিউ টিমের তথ্য

* ইমেইল, ফোন নম্বর
* যদি অ্যাপে লগইন লাগে, ডেমো ইউজারনেম ও পাসওয়ার্ড দিন

---

## 📡 পোস্ট-সাবমিশন (After Submission)

### 16. 📊 রিভিউ স্ট্যাটাস মনিটর

* **Approved** → App Store-এ লাইভ
* **Rejected** → ফিডব্যাক দেখে ঠিক করে পুনরায় সাবমিট

---

## 🔒 সার্টিফিকেট ও Provisioning Profile সম্পর্কিত নোট

| কাজ                    | Auto-manage Signing (Xcode) | ম্যানুয়ালি লাগে? |
| ---------------------- | --------------------------- | ----------------- |
| ফোনে রান (Development) | ✅ হ্যাঁ                     | ❌ না              |
| App Store এ আপলোড      | ✅ হ্যাঁ                     | ❌ না              |
| কোনো এরর এলে           | ❌ না                        | ✅ প্রয়োজনে       |

---

## 📌 সংক্ষিপ্ত প্রায়োরিটি তালিকা

| Priority | ধাপ                    | কী করবেন                                   |
| -------- | ---------------------- | ------------------------------------------ |
| 1️⃣      | ডেভেলপার একাউন্ট       | সাবস্ক্রাইব করুন, Apple ID সেটআপ করুন      |
| 2️⃣      | Xcode সেটআপ            | Auto-signing চালু করুন                     |
| 3️⃣      | Flutter অ্যাপ বিল্ড    | Release মোডে iOS build করুন                |
| 4️⃣      | অ্যাপ আপলোড            | Xcode → App Store Connect-এ আপলোড          |
| 5️⃣      | অ্যাপ তৈরি ও তথ্য পূরণ | Metadata ও মৌলিক তথ্য যোগ করুন             |
| 6️⃣      | প্রাইভেসি ও প্রাইসিং   | Privacy Policy URL ও Pricing সেট করুন      |
| 7️⃣      | স্ক্রিনশট ও আইকন       | UI/UX উপস্থাপন নিশ্চিত করুন                |
| 8️⃣      | রিভিউ সাবমিশন          | Build নির্বাচন করে Submit করুন             |
| 9️⃣      | রিভিউ ফলোআপ            | Review স্ট্যাটাস চেক করে ফিডব্যাক ফলো করুন |


