![iosfolder structure](https://github.com/user-attachments/assets/b23af8e9-9c53-4f23-ab3d-405c9fa7c21d)

## 🔷 ১. Runner (📂 Project root)

এই অংশটি হলো iOS অ্যাপের মূল প্রোজেক্ট। এখানে Flutter কোডকে iOS-এ নেটিভভাবে চালাতে সহায়তা করে এমন ফাইল থাকে।

### 🔹 Flutter (📁)

এটি Flutter engine ও build system সম্পর্কিত ফাইল। সাধারণত এখানে নিজে কিছু পরিবর্তন করতে হয় না।

* **AppFrameworkInfo**: এটি একটি প্লিস্ট (Property List) ফাইল যা iOS অ্যাপে embedded Flutter framework-এর কিছু মেটাডেটা ধারণ করে।
* **Debug / Release / Generated**: Flutter যখন build করে তখন প্রয়োজনীয় ডিপেন্ডেন্সি ও binary ফাইল তৈরি করে এই ফোল্ডারে।

📌 **কখন দরকার?** তুমি যদি Flutter framework-level customization করো বা Xcode build error দেখাও তখন মাঝে মাঝে এখানে দেখার প্রয়োজন হতে পারে।

---

### 🔹 Runner (📁)

এটাই হচ্ছে iOS-এর মূল অ্যাপ প্রজেক্ট ফোল্ডার। Flutter অ্যাপ iOS-এ রান করার জন্য এটি ব্যবহৃত হয়।

#### ▪️ RunnerRelease

Build configurations handle করে। এটি auto-generated, release version-এর জন্য।

#### ▪️ Main (📁)

iOS Storyboard থাকে এখানে—এটি iOS UI-এর একটি পুরোনো ধরন। Flutter UI এর ক্ষেত্রে খুব বেশি প্রয়োজন পড়ে না, তবে splash screen বা launch screen সেট করতে ব্যবহৃত হয়।

#### ▪️ Assets

এই ফোল্ডারে তোমার image বা অন্যান্য অ্যাসেট যোগ করতে পারো যদি সেগুলো শুধু iOS-এর জন্য ব্যবহৃত হয়।

#### ▪️ LaunchScreen

iOS অ্যাপ খুললে প্রথম যে স্ক্রিন দেখা যায় সেটির design storyboard ফাইল। এটিতে splash screen design করা যায়।

#### ▪️ Info (Info.plist)

iOS অ্যাপের মেটাডেটা যেমন App Name, Bundle Identifier, permissions (camera, location) ইত্যাদি ডিফাইন করা হয় এখানে।

#### ▪️ AppDelegate.swift

Flutter অ্যাপ ও iOS system-এর মধ্যে কমিউনিকেশন করার জন্য এটি ব্যবহৃত হয়। উদাহরণস্বরূপ, notification handle করা, background task, deep linking ইত্যাদি।

#### ▪️ GeneratedPluginRegistrant

Flutter plugins-কে iOS-এর সাথে যুক্ত করার জন্য auto-generated Swift/Objective-C ফাইল।

#### ▪️ Runner-Bridging-Header.h

Objective-C ও Swift এর মধ্যে যোগাযোগ করতে হলে এই bridging header প্রয়োজন। যখন কোনো Flutter plugin Objective-C-তে লেখা থাকে এবং তুমি Swift ব্যবহার করো তখন এটি অপরিহার্য।

📌 **কখন দরকার?** যখন Swift ও Objective-C একসাথে ব্যবহার করো।

---

## 🔷 ২. Products (📁)

এখানে Xcode এর build output দেখা যায়।

* **Runner**: এটি হচ্ছে compiled iOS অ্যাপ binary (`.app` ফাইল)।

---

## 🔷 ৩. Pods (📁)

CocoaPods হল iOS-এর ডিপেন্ডেন্সি ম্যানেজার। Flutter plugin-গুলো এখানে ইনস্টল হয়।

#### ▪️ Pods-Runner.debug / release / profile

Flutter project যখন build হয় তখন CocoaPods এর ডিপেন্ডেন্সিগুলো profile অনুযায়ী আলাদা হয় (debug, release ইত্যাদি)।

#### ▪️ TangramMap

এটি সম্ভবত একটি third-party CocoaPod (Flutter plugin হিসেবে add করেছিলে)।

#### ▪️ Pods\_Runner

Flutter Runner target এর জন্য CocoaPods dependencies handle করে।

---

## 🔷 ৪. Pods > Podfile

CocoaPods এর কনফিগারেশন ফাইল। এখানে তোমার Flutter plugin ও নেটিভ iOS dependency গুলো ডিফাইন করা থাকে।

📌 **যখন দরকার?**
যদি তুমি plugin version change করো অথবা custom iOS library যোগ করো তখন এই ফাইল modify করতে হয়।

---

## 🔷 ৫. বাকিগুলো (Development Pods, Frameworks, Targets Support Files)

এসব মূলত CocoaPods নিজে থেকে manage করে। এগুলোর মধ্যে dependencies এর internal structure থাকে।

---

## ❓ তুমি কেন Xcode খুলেছো?

👉 কিছু সাধারণ কারণ নিচে দিলাম:

1. **iOS build configuration পরিবর্তন** করতে (যেমন: App icon, permissions, signing)
2. **Splash screen ডিজাইন** করতে (LaunchScreen.storyboard)
3. **Native iOS কোড** (Swift/Objective-C) লিখতে বা debug করতে
4. **Push notification, background task** সেটআপ করতে
5. **Flutter plugin integration সমস্যার সমাধান করতে**
6. **App store-এ publish করার আগে testing ও configuration verify করতে**

---

## 📌 তোমার করণীয় (যদি Flutter iOS-এ ভালোভাবে রান করতে চাও):

1. ✅ `Info.plist` ফাইলে permissions যেমন camera, location add করা শিখো।
2. ✅ `AppDelegate.swift` এ notification বা deeplink ইন্টিগ্রেশন করার পদ্ধতি বুঝো।
3. ✅ `Runner-Bridging-Header.h` যদি ব্যবহার করো, বুঝে করো—Swift ও Objective-C mix করলে দরকার।
4. ✅ `Podfile` কনফিগারেশন বুঝে রাখো—Flutter plugin কাজ না করলে এখানেই সমস্যা থাকে।
5. ✅ Archive ও Test করার জন্য Xcode-এর **Product > Archive** অপশন চেক করো।

---

## 🔚 শেষ কথা:

তুমি যদি Flutter ডেভেলপার হও এবং iOS-এ অ্যাপ রান করতে চাও, তাহলে এই ফাইলগুলো সম্পর্কে ভালো ধারণা থাকা জরুরি। Xcode শুধুমাত্র Native iOS build/test/archive করার জন্য নয়, বরং Flutter-এর plugin integration ও platform-specific configuration এর জন্যও অপরিহার্য।

---

