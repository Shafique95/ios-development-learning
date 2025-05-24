 Flutter অ্যাপে `ios/` ফোল্ডার বনাম `android/` ফোল্ডার — তাদের পার্থক্য ও কাজ কী।  **ব্যাখ্যা (বাংলায়)**:

---

## 🥊 `ios/` vs `android/` ফোল্ডার Flutter অ্যাপে

| বিষয়                      | `ios/` ফোল্ডার                | `android/` ফোল্ডার                                    |
| ------------------------- | ----------------------------- | ----------------------------------------------------- |
| 📱 প্ল্যাটফর্ম            | iOS (iPhone, iPad)            | Android (Samsung, Xiaomi, Pixel etc.)                 |
| 🛠️ টুল                   | Xcode (macOS only)            | Android Studio / Gradle                               |
| 📂 মূল ফোল্ডার            | `ios/Runner`                  | `android/app`                                         |
| 🎯 এন্ট্রি পয়েন্ট         | `AppDelegate.swift`           | `MainActivity.kt` or `.java`                          |
| ⚙️ কনফিগারেশন ফাইল        | `Info.plist`, `Podfile`       | `AndroidManifest.xml`, `build.gradle`                 |
| 🎨 আইকন ও স্প্ল্যাশ       | `Assets.xcassets`             | `res/mipmap`, `res/drawable`, `launch_background.xml` |
| 📦 ডিপেন্ডেন্সি ম্যানেজার | CocoaPods (`pod install`)     | Gradle (`build.gradle`)                               |
| 🔐 পারমিশন সেটআপ          | `Info.plist`                  | `AndroidManifest.xml`                                 |
| 📤 রিলিজ বিল্ড            | `.ipa` (iOS App Archive)      | `.apk` / `.aab`                                       |
| 🧪 টেস্ট ডিভাইস           | iPhone সিমুলেটর বা আসল ডিভাইস | Android Emulator বা ফোন                               |

---

## 🔎 কিছু মূল পার্থক্য

### 1. **Entry Point**

* iOS: `AppDelegate.swift` — অ্যাপ চালু হলে এখানে প্রথম কোড রান হয়
* Android: `MainActivity.kt` — Android অ্যাপের প্রথম স্ক্রিন শুরু হয় এখান থেকে

---

### 2. **Permission System**

* iOS: `Info.plist`-এ লিখে ইউজার পারমিশনের কারন জানাতে হয়

  ```xml
  <key>NSCameraUsageDescription</key>
  <string>আমরা ছবি তোলার জন্য ক্যামেরা চাই</string>
  ```

* Android: `AndroidManifest.xml`-এ পারমিশন ডিক্লেয়ার করতে হয়

  ```xml
  <uses-permission android:name="android.permission.CAMERA" />
  ```

---

### 3. **Third-party Library (Native Integration)**

* iOS: `Podfile` (CocoaPods ব্যবহার করে লাইব্রেরি ম্যানেজ করে)

  ```ruby
  pod 'Firebase/Analytics'
  ```

* Android: `build.gradle`

  ```gradle
  implementation 'com.google.firebase:firebase-analytics'
  ```

---

### 4. **Release Build**

* iOS:

  * Xcode > Product > Archive → `.ipa` ফাইল তৈরি হয়
  * App Store Connect এ সাবমিট করতে হয়

* Android:

  * `flutter build apk` বা `flutter build appbundle`
  * Play Store Console এ আপলোড করতে হয়

---

## 🤔 Flutter দিয়ে কাজ করলে এই দুটি ফোল্ডার কখন ব্যবহার করবেন?

| আপনি করতে চান                    | দরকার হবে                                       |
| -------------------------------- | ----------------------------------------------- |
| UI ও Dart কোড লেখা               | `lib/` ফোল্ডার                                  |
| ক্যামেরা বা লোকেশন পারমিশন       | `android/AndroidManifest.xml`, `ios/Info.plist` |
| Firebase যোগ করা                 | দুই ফোল্ডারেই config লাগবে                      |
| iOS only বা Android only feature | প্ল্যাটফর্ম-স্পেসিফিক ফোল্ডার (iOS/Android)     |
| App icon ও splash screen         | `android/app/res/`, `ios/Assets.xcassets/`      |
| App release / publish            | Android → APK/AAB, iOS → IPA                    |

---

## 🎁 Bonus Tip:

Flutter SDK আপনাকে Dart কোড দিয়ে cross-platform UI তৈরি করতে দেয়, কিন্তু কিছু বিষয় **iOS ও Android-এ আলাদা** ভাবে কনফিগার করতেই হয় — তাই `ios/` এবং `android/` ফোল্ডার থাকাটা বাধ্যতামূলক।

