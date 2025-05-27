![iosfolder structure](https://github.com/user-attachments/assets/b23af8e9-9c53-4f23-ab3d-405c9fa7c21d)

ধন্যবাদ! তুমি সঠিকভাবে বলেছো—একটা Flutter প্রজেক্টের iOS ফোল্ডার Xcode-এ খুললে অনেকগুলো ফোল্ডার ও ফাইল দেখা যায়। নিচে **তোমার স্ক্রিনশটে থাকা প্রতিটি ফোল্ডার এবং ফাইল** একে একে বাংলায় ব্যাখ্যা করলাম, **কোনটি কী কাজ করে, কখন দরকার হয়, কেন দরকার হয়, এবং কীভাবে ব্যবহৃত হয়** সব বিস্তারিতভাবে।

---

## ✅ \[Root Level] Runner (📂)

এই Runner হলো Xcode-এ iOS অ্যাপের মূল project group। এটি মূলত iOS এর native অংশ, যেখানে Flutter কোডকে iOS-এর সাথে integrate করা হয়। এর ভেতরে নিচের ফোল্ডারগুলো ও ফাইলগুলো রয়েছে:

---

### 🔹 1. Flutter (📁)

এটি Flutter SDK দ্বারা ব্যবহৃত ফোল্ডার যা Flutter build process এর সময় iOS-specific তথ্য ও frameworks ধারণ করে।

* **AppFrameworkInfo.plist**: Flutter framework সম্পর্কিত iOS metadata। iOS runtime-এ Flutter module ঠিকভাবে কাজ করার জন্য ব্যবহৃত হয়।

* **Debug / Release / Generated (📁)**:

  * **Debug**: debug মোডে অ্যাপ চালানোর জন্য Flutter framework এবং অন্যান্য ফাইল থাকে।
  * **Release**: release মোডে অ্যাপ চালানোর জন্য build করা ফাইল থাকে।
  * **Generated**: Flutter build করার সময় auto-generated ফাইল রাখে। Flutter plugins থেকে তৈরি হওয়া কোড, Dart থেকে নেটিভে ব্রিজ করার ফাইল ইত্যাদি এখানে থাকে।

📌 **এগুলো সাধারণত নিজে edit করতে হয় না**, তবে Flutter build error বা custom integration এর সময় দরকার হতে পারে।

---

### 🔹 2. Runner (📁)

iOS অ্যাপের মূল project files এখানে থাকে।

* **RunnerRelease.xcconfig**: iOS অ্যাপ build configuration ডিফাইন করে (যেমন build settings, code signing)। এটি `Release` মোডে ব্যবহৃত হয়।

* **Main (📁)**:

  * এখানে Storyboard বা .xib ফাইল থাকে।
  * Flutter অ্যাপ মূলত নিজস্ব UI রেন্ডার করে, তাই এই ফোল্ডার খুব বেশি ব্যবহৃত হয় না। তবে Launch Screen বা native UI component থাকলে এখানে রাখতে হয়।

* **Assets (📁)**:

  * iOS অ্যাপের images, app icons ইত্যাদি রাখার জন্য।
  * Flutter এর assets সাধারণত `pubspec.yaml` থেকে নেওয়া হয়, কিন্তু যদি কিছু শুধু iOS-এর জন্য থাকে, তাহলে এখানে রাখা যায়।

* **LaunchScreen.storyboard**: iOS অ্যাপে অ্যাপ চালুর সময় যে প্রথম স্ক্রিনটি দেখা যায়, তার ডিজাইন ফাইল। Flutter splash screen কাস্টমাইজ করতে এটি দরকার।

* **Info.plist**:

  * iOS অ্যাপের config ফাইল।
  * অ্যাপের নাম, version, permissions (camera, microphone, location), App Transport Security, এবং Bundle Identifier এখানে define করা হয়।

* **GeneratedPluginRegistrant.\[h, m]**:

  * Flutter plugins যেগুলো ব্যবহার করছো সেগুলো iOS প্ল্যাটফর্মে register করার জন্য auto-generated ফাইল।
  * `.h` হলো header (Objective-C) এবং `.m` হলো implementation।

* **AppDelegate.swift**:

  * iOS অ্যাপের lifecycle শুরু এখান থেকেই।
  * Flutter engine initialize করা হয় এখানে।
  * যদি Notification, Deep Linking, Firebase setup করতে চাও—তাহলে এখানেই করতে হবে।

* **Runner-Bridging-Header.h**:

  * Swift ও Objective-C কোড একসাথে ব্যবহার করতে হলে এটি দরকার হয়।
  * উদাহরণ: যদি কোনো plugin Objective-C-তে লেখা হয়, এবং তুমি Swift ব্যবহার করো।

---

## ✅ Products (📂)

এখানে Xcode এর build output থাকে।

* **Runner (app icon)**:

  * এটা হচ্ছে iOS অ্যাপের build হয়ে তৈরি হওয়া executable ফাইল (`.app`)।

---

## ✅ Pods (📂)

CocoaPods হল iOS-এ dependency manager। Flutter plugin-গুলো অনেক সময় CocoaPods ব্যবহার করে iOS অংশে integrate হয়। এই ফোল্ডারটা CocoaPods নিজেই তৈরি করে এবং এখানে অনেক উপ-ফোল্ডার থাকে:

---

### 🔹 Pods > Pods-Runner.debug / release / profile (📁)

Flutter অ্যাপ build এর সময় CocoaPods dependency গুলো debug, release বা profile মোড অনুযায়ী আলাদা আলাদা manage করে। এরা হলো build configuration-specific frameworks।

* **Pods-Runner.debug**: Debug মোডে অ্যাপ রান করলে যে dependencies লাগে।
* **Pods-Runner.release**: Release মোডের জন্য।
* **Pods-Runner.profile**: Profile মোডে performance check করার জন্য।

---

### 🔹 Pods > Frameworks > TangramMap

* এটি একটি third-party CocoaPod। সম্ভবত Flutter plugin বা iOS-এর জন্য ব্যবহৃত একটি map library।
* নিজে install বা কোনো plugin install করার মাধ্যমে এসেছে।

---

### 🔹 Pods > Frameworks > Pods\_Runner

* এটি Runner অ্যাপের জন্য CocoaPods দ্বারা build করা frameworks গুলো manage করে।

---

## ✅ Pods (Second time listed –📂 Bottom Group)

এটি প্রকৃত CocoaPods ফোল্ডার (not project group)। এই ফোল্ডারের ভেতরে নিচের গুলো থাকে:

---

### 🔹 Podfile

* CocoaPods এর configuration ফাইল। এখানে dependency গুলো list করা থাকে।
* যেমন:

  ```ruby
  pod 'Firebase/Core'
  pod 'GoogleMaps'
  ```

📌 **কখন দরকার হয়?**

* যদি নতুন Flutter plugin যোগ করো যেটা iOS নেটিভ অংশে নির্ভর করে, তখন `Podfile` update করতে হয়।
* Terminal-এ `pod install` বা `pod update` চালানোর জন্য।

---

### 🔹 Development Pods

* যদি কোনো local plugin বা custom pod যোগ করো, তখন এখানে list হয়।

---

### 🔹 Frameworks

* CocoaPods দ্বারা ব্যবহৃত frameworks গুলো এখানে থাকে। এটি Pods Project-এর অংশ।

---

### 🔹 Pods

* এখানে CocoaPods দ্বারা install হওয়া প্রতিটি pod ফোল্ডারে থাকে।

---

### 🔹 Products

* CocoaPods build output ফাইল।

---

### 🔹 Targets Support Files

* CocoaPods build configuration, scripts ইত্যাদি support ফাইল এখানে থাকে।

---

## ✅ শেষ কথা (Summary):

| অংশ                      | কাজ                     | কখন দরকার                 |
| ------------------------ | ----------------------- | ------------------------- |
| `Runner`                 | মূল iOS অ্যাপ           | সবসময়                     |
| `Flutter`                | Flutter engine ও config | সাধারণত না, debug এ দরকার |
| `Assets`, `LaunchScreen` | UI design               | Splash screen             |
| `AppDelegate.swift`      | Entry point             | Notification, DeepLink    |
| `Info.plist`             | Permissions, Name       | Always                    |
| `Pods`, `Podfile`        | Plugin & dependencies   | Plugin add করলে           |

---

## 💡 Bonus Tip:

✅ যদি Flutter plugin ব্যবহার করে iOS কোডে সমস্যা দেখাও, তখন `Podfile`, `AppDelegate.swift`, এবং `Info.plist` তিনটি ফাইলেই দেখতে হবে।

