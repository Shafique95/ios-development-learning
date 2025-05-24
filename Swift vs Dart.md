 **Swift বনাম Dart syntax তুলনা করে** শেখার জন্য — বিশেষ করে যদি আপনি Flutter/Dart ব্যাকগ্রাউন্ড থেকে Swift (iOS) শেখা শুরু করে থাকেন, তাহলে এই তুলনা অনেক সাহায্য করবে।

---

## 🔁 Swift vs Dart Syntax Comparison (বাংলায় ব্যাখ্যাসহ)

| কাজ                  | Dart                                      | Swift                                              |
| -------------------- | ----------------------------------------- | -------------------------------------------------- |
| ভ্যারিয়েবল ডিক্লেয়ার | `var name = "John";`                      | `var name = "John"`                                |
| কনস্ট্যান্ট          | `const pi = 3.14;`<br>`final name = "A";` | `let pi = 3.14`                                    |
| ফাংশন                | `void greet() { print("Hi"); }`           | `func greet() { print("Hi") }`                     |
| ফাংশন রিটার্ন        | `int add(int a, int b) => a + b;`         | `func add(a: Int, b: Int) -> Int { return a + b }` |
| ক্লাস                | `class Person {}`                         | `class Person {}`                                  |
| Constructor          | `Person(this.name);`                      | `init(name: String) { self.name = name }`          |
| ইনহেরিটেন্স          | `class Cat extends Animal {}`             | `class Cat: Animal {}`                             |
| Optional / Null      | `String? name;`                           | `var name: String?`                                |
| Null check           | `name ?? "Guest"`                         | `name ?? "Guest"`                                  |
| if condition         | `if (a > b) {}`                           | `if a > b {}`                                      |
| for loop             | `for (var i = 0; i < 5; i++)`             | `for i in 0..<5`                                   |
| List                 | `List<String> items = []`                 | `var items: [String] = []`                         |
| Map                  | `Map<String, int> map = {}`               | `var map: [String: Int] = [:]`                     |
| Arrow function       | `() => print("hi")`                       | `{ print("hi") }` (trailing closure)               |
| Switch case          | `switch(x) { case 1: break; }`            | `switch x { case 1: break }`                       |

---

## 🎯 কিছু Swift Syntax উদাহরণ (Flutter চেনা ভাষায়)

### ✅ ১. ভ্যারিয়েবল ও কনস্ট্যান্ট

```dart
// Dart
var name = "Ali";
final age = 25;
const pi = 3.14;
```

```swift
// Swift
var name = "Ali"
let age = 25      // Immutable
let pi = 3.14     // Compile-time const
```

---

### ✅ ২. ফাংশন

```dart
int sum(int a, int b) => a + b;
```

```swift
func sum(a: Int, b: Int) -> Int {
    return a + b
}
```

---

### ✅ ৩. ক্লাস ও কনস্ট্রাক্টর

```dart
class Person {
  String name;
  Person(this.name);
}
```

```swift
class Person {
    var name: String
    init(name: String) {
        self.name = name
    }
}
```

---

### ✅ ৪. লিস্ট (Array)

```dart
List<String> fruits = ["apple", "banana"];
```

```swift
var fruits: [String] = ["apple", "banana"]
```

---

### ✅ ৫. Null / Optional Handling

```dart
String? name;
print(name ?? "Guest");
```

```swift
var name: String?
print(name ?? "Guest")
```

---

### ✅ ৬. লুপ

```dart
for (var i = 0; i < 5; i++) {
  print(i);
}
```

```swift
for i in 0..<5 {
    print(i)
}
```

---

## 🧠 Key Differences: (Short Summary)

| বিষয়             | Dart              | Swift                                     |
| ---------------- | ----------------- | ----------------------------------------- |
| null safety      | built-in          | optional-based                            |
| async/await      | same style        | same style (with `async` and `await`)     |
| Type inference   | supported (`var`) | supported (`var`)                         |
| Arrow syntax     | ✅                 | ❌ traditional closure or trailing closure |
| Named parameters | ✅ with `{}`       | ✅ with `paramName:`                       |
| Struct support   | ❌                 | ✅ (Swift has both struct & class)         |

---

## ✅ আপনি কীভাবে শিখবেন?

* আপনি যদি Flutter জানেন → Swift অনেকটাই পরিচিত লাগবে
* আমি চাইলে আপনাকে Flutter Widget vs SwiftUI View তুলনাও করতে পারি
* চাইলে SwiftUI দিয়ে ছোট app component বানিয়ে হাতে-কলমে দেখাতে পারি

---



* Dart → Swift syntax cheat sheet (PDF)
* Function, class, UI component mapping
* Project structure mapping (Flutter vs SwiftUI)

  
---

## ✍️ Sample Syntax Comparison

| Feature         | Dart                                | Swift                                |
|----------------|-------------------------------------|--------------------------------------|
| Variable        | `var name = "Ali";`                | `var name = "Ali"`                   |
| Constant        | `const pi = 3.14;`                 | `let pi = 3.14`                      |
| Function        | `int add(int a, int b) => a + b;`  | `func add(a: Int, b: Int) -> Int`    |
| Class           | `class Person {}`                  | `class Person {}`                    |
| List            | `List<String> items = [];`         | `var items: [String] = []`           |
| Null Check      | `name ?? "Guest"`                  | `name ?? "Guest"`                    |

---

## 🛠️ How to Generate the PDF

1. Make sure Python is installed on your system.
2. Install the required package:
    ```bash
    pip install fpdf
    ```
3. Run the script:
    ```bash
    python generate_pdf.py
    ```

The file `Dart_to_Swift_Syntax_Cheat_Sheet.pdf` will be generated in the current directory.

---

## 🙌 Contributions

Feel free to open a PR if you'd like to expand this cheat sheet with:

- SwiftUI vs Flutter Widgets
- Async/Await comparisons
- Real-world example components

---

## 📜 License

MIT License © 2025 [Your Name]


