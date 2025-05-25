Flutter-এ iOS অ্যাপে **Pods** ব্যবহার করা হয় CocoaPods-এর মাধ্যমে, যেটা iOS-এর জন্য একটি dependency manager। এখন চলুন বিষয়টা বিস্তারিতভাবে **বাংলা ভাষায়** ব্যাখ্যা করি:

---

## 🎯 **Pods কী?**

**Pods** হচ্ছে CocoaPods-এর মাধ্যমে ব্যবহৃত লাইব্রেরি বা প্যাকেজ যা iOS অ্যাপে ইন্টিগ্রেট করা হয়। Flutter যখন iOS অ্যাপে কিছু প্লাগইন (যেমন: `camera`, `firebase`, `google_maps`) ব্যবহার করে, তখন সেই প্লাগইনগুলো Objective-C/Swift কোডের ওপর নির্ভর করে। এই নেটিভ কোডগুলিকে ম্যানেজ করতে **CocoaPods** ব্যবহৃত হয়।

---

## ❓ **কেন Pods ব্যবহার করা হয়?**

Flutter প্লাগইন যখন iOS-এর জন্য কিছু নেটিভ কোড যোগ করে, তখন সেই কোডগুলোর জন্য third-party dependency দরকার হয়। CocoaPods:

* এই dependency-গুলো ডাউনলোড করে,
* সেগুলো প্রজেক্টে ইনস্টল করে,
* build settings আপডেট করে।

**উদাহরণ:** `firebase_core` প্লাগইন ব্যবহার করলে `Firebase/Core` লাইব্রেরি iOS অ্যাপে যুক্ত করতে CocoaPods দরকার হয়।

---

## 📦 **Pods কখন লাগে?**

Pods প্রয়োজন হয়:

1. যখন আপনি কোনো Flutter প্লাগইন ব্যবহার করছেন যেটা iOS-এ নেটিভ কোড ব্যবহার করে।
2. Flutter প্রজেক্ট iOS-এ রান করার আগে `pod install` বা `pod update` করতে হয়।
3. আপনি যদি `ios/Podfile` এ কিছু পরিবর্তন করেন।

---

## ⚙️ **কিভাবে Pods ব্যবহার করবেন?**

### ✅ প্রথমে নিশ্চিত করুন আপনার macOS-এ CocoaPods ইনস্টল আছে:

```bash
sudo gem install cocoapods
```

### ✅ তারপর Flutter iOS প্রজেক্টে যান:

```bash
cd ios
pod install
```

### ✅ অথবা Flutter থেকে সরাসরি:

```bash
flutter pub get
flutter build ios
```

Flutter নিজেই `pod install` চালিয়ে দেবে।

---

## 🛠️ **সমস্যা হলে কী করবেন?**

* `pod deintegrate` → পুরোনো Pod ফাইল সরাতে
* `pod install` → নতুন করে ইনস্টল করতে
* `pod update` → সমস্ত পড আপডেট করতে

---

## 🔚 **সারসংক্ষেপে:**

| বিষয়          | ব্যাখ্যা                                     |
| ------------- | -------------------------------------------- |
| **Pods কী**   | CocoaPods dependency system                  |
| **কেন দরকার** | iOS নেটিভ লাইব্রেরি ব্যবহারের জন্য           |
| **কখন দরকার** | Flutter প্লাগইন ইন্সটল বা iOS বিল্ড করার সময় |
| **কিভাবে**    | `pod install`, `flutter build ios`           |


