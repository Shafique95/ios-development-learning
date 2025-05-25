Flutter প্রজেক্টের iOS অংশের **`Runner`** সম্পর্কে বিস্তারিতভাবে **বাংলা ভাষায়** ব্যাখ্যা করছি:

---

## 🚀 **Runner কী?** *(Flutter iOS App Structure)*

`Runner` হলো Flutter অ্যাপের **iOS অংশের মূল অ্যাপ**। এটি সেই জায়গা যেখানে Flutter কোড **iOS নেটিভ কোডে** রান করার জন্য মোড়ানো হয়।

### 📁 আপনি `ios/` ফোল্ডারে যা দেখেন:

```
ios/
├── Runner.xcodeproj
├── Runner.xcworkspace
├── Runner/
│   ├── AppDelegate.swift
│   ├── Assets.xcassets
│   ├── Info.plist
│   └── Main.storyboard (পুরনো প্রজেক্টে)
```

---

## 🧠 **Runner-এর কাজ কী?**

### 1. **Flutter কোড চালানো (iOS এ)**

Flutter কোড (যেটা Dart-এ লেখা) iOS ডিভাইসে রান করতে হলে, সেটাকে নেটিভ iOS কোডের সাথে যুক্ত করতে হয় — সেটা `Runner` করে।

### 2. **App Delegate (Lifecycle Control)**

* `AppDelegate.swift` ফাইলটা Runner-এর মধ্যে থাকে।
* এটি অ্যাপের lifecycle, push notification, Firebase init, deep linking ইত্যাদি হ্যান্ডেল করে।

### 3. **App Configuration**

* `Info.plist` → অ্যাপের নাম, permissions (যেমন: ক্যামেরা, লোকেশন) ইত্যাদি নির্ধারণ করে।
* `Assets.xcassets` → আইকন ও ইমেজ স্টোর হয় এখানে।

---

## 🛠️ **Runner কখন দরকার হয়?**

* যখন আপনি iOS-specific কোনো configuration করতে চান
* Firebase, Push Notification, App Icon, Permission যোগ করতে চান
* যখন Xcode-এ খুলে build/run করতে হয়

---

## ⚙️ **Runner.xcodeproj vs Runner.xcworkspace**

| ফাইল                 | উদ্দেশ্য                              |
| -------------------- | ------------------------------------- |
| `Runner.xcodeproj`   | শুধুমাত্র Runner প্রজেক্ট (Pods ছাড়া) |
| `Runner.xcworkspace` | Runner + CocoaPods (Pods support সহ)  |

> যদি আপনি Flutter প্লাগইন ব্যবহার করেন (যেমন firebase, camera), তাহলে অবশ্যই `Runner.xcworkspace` দিয়ে Xcode ওপেন করবেন।

---

## 🎯 **সারাংশ: Runner মানে কী?**

| বিষয়       | ব্যাখ্যা                                            |
| ---------- | --------------------------------------------------- |
| `Runner`   | Flutter iOS অ্যাপের মূল কন্টেইনার                   |
| কোথায় থাকে | `ios/Runner/` ফোল্ডারে                              |
| কী কাজ করে | iOS অ্যাপ config, lifecycle, native কোড হোস্ট করে   |
| কখন দরকার  | iOS বিল্ড, সেটিংস পরিবর্তন, নেটিভ কোড সংযুক্তির সময় |

