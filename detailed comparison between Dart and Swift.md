Here's a **detailed comparison between Dart and Swift**, covering all major topics along with **syntax and examples**. This will help you understand both languages side-by-side if you're a cross-platform or native developer exploring both.

---

## 🔰 Overview

| Feature     | Dart                                      | Swift                                  |
| ----------- | ----------------------------------------- | -------------------------------------- |
| Creator     | Google                                    | Apple                                  |
| Platform    | Cross-platform (Flutter)                  | Apple-only (iOS, macOS, watchOS, etc.) |
| Type System | Statically typed (with type inference)    | Statically typed (with type inference) |
| Use Case    | Flutter apps (Android, iOS, Web, Desktop) | Native Apple ecosystem development     |

---

## 📚 Topics Covered

1. **Hello World**
2. **Variables & Constants**
3. **Data Types**
4. **Operators**
5. **Control Flow (if, switch)**
6. **Loops (for, while)**
7. **Functions**
8. **Classes & Objects**
9. **Constructors**
10. **Inheritance**
11. **Mixins / Protocols**
12. **Null Safety**
13. **Collections (List, Map, Set)**
14. **Exception Handling**
15. **Async & Await**
16. **Extensions**
17. **Generics**

---

## 1. 🔊 Hello World

**Dart:**

```dart
void main() {
  print('Hello, Dart!');
}
```

**Swift:**

```swift
import Foundation
print("Hello, Swift!")
```

---

## 2. 🪙 Variables & Constants

**Dart:**

```dart
var name = 'Alice';
final age = 25;
const pi = 3.14;
```

**Swift:**

```swift
var name = "Alice"
let age = 25 // constant
```

---

## 3. 🔢 Data Types

**Dart:**

```dart
int a = 10;
double b = 3.14;
String c = 'hello';
bool d = true;
```

**Swift:**

```swift
var a: Int = 10
var b: Double = 3.14
var c: String = "hello"
var d: Bool = true
```

---

## 4. ➕ Operators

**Dart:**

```dart
int x = 5;
int y = 2;
print(x + y); // 7
```

**Swift:**

```swift
let x = 5
let y = 2
print(x + y)
```

---

## 5. 🔁 If / Switch

**Dart:**

```dart
if (x > y) {
  print('x is greater');
} else {
  print('y is greater');
}

switch (x) {
  case 1:
    print('One');
    break;
  default:
    print('Default');
}
```

**Swift:**

```swift
if x > y {
  print("x is greater")
} else {
  print("y is greater")
}

switch x {
case 1:
  print("One")
default:
  print("Default")
}
```

---

## 6. 🔂 Loops

**Dart:**

```dart
for (int i = 0; i < 5; i++) {
  print(i);
}
```

**Swift:**

```swift
for i in 0..<5 {
  print(i)
}
```

---

## 7. 🧩 Functions

**Dart:**

```dart
int add(int a, int b) => a + b;
```

**Swift:**

```swift
func add(a: Int, b: Int) -> Int {
  return a + b
}
```

---

## 8. 🧱 Classes & Objects

**Dart:**

```dart
class Person {
  String name;
  Person(this.name);
}

var p = Person('John');
```

**Swift:**

```swift
class Person {
  var name: String
  init(name: String) {
    self.name = name
  }
}

let p = Person(name: "John")
```

---

## 9. 🏗️ Constructors

**Dart:**

```dart
class Person {
  String name;
  int age;

  Person(this.name, this.age);
}
```

**Swift:**

```swift
class Person {
  var name: String
  var age: Int

  init(name: String, age: Int) {
    self.name = name
    self.age = age
  }
}
```

---

## 10. 🧬 Inheritance

**Dart:**

```dart
class Animal {
  void sound() => print('Animal sound');
}

class Dog extends Animal {
  @override
  void sound() => print('Bark');
}
```

**Swift:**

```swift
class Animal {
  func sound() {
    print("Animal sound")
  }
}

class Dog: Animal {
  override func sound() {
    print("Bark")
  }
}
```

---

## 11. 💡 Mixins / Protocols

**Dart (Mixin):**

```dart
mixin Walk {
  void walk() => print('Walking...');
}

class Person with Walk {}

void main() {
  Person().walk();
}
```

**Swift (Protocol):**

```swift
protocol Walk {
  func walk()
}

class Person: Walk {
  func walk() {
    print("Walking...")
  }
}
```

---

## 12. 🛑 Null Safety

**Dart:**

```dart
String? name = null;
```

**Swift:**

```swift
var name: String? = nil
```

---

## 13. 📦 Collections

**Dart:**

```dart
List<String> names = ['A', 'B'];
Map<String, int> scores = {'Math': 90};
Set<int> nums = {1, 2, 3};
```

**Swift:**

```swift
let names: [String] = ["A", "B"]
let scores: [String: Int] = ["Math": 90]
let nums: Set<Int> = [1, 2, 3]
```

---

## 14. ❗ Exception Handling

**Dart:**

```dart
try {
  throw Exception('Error!');
} catch (e) {
  print(e);
}
```

**Swift:**

```swift
enum MyError: Error {
  case somethingWrong
}

do {
  throw MyError.somethingWrong
} catch {
  print("Error caught")
}
```

---

## 15. 🧵 Async & Await

**Dart:**

```dart
Future<void> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  print('Data fetched');
}
```

**Swift:**

```swift
func fetchData() async {
  try? await Task.sleep(nanoseconds: 1_000_000_000)
  print("Data fetched")
}
```

---

## 16. ✒️ Extensions

**Dart:**

```dart
extension StringExtension on String {
  String greet() => 'Hello, $this';
}

print('World'.greet()); // Hello, World
```

**Swift:**

```swift
extension String {
  func greet() -> String {
    return "Hello, \(self)"
  }
}

print("World".greet()) // Hello, World
```

---

## 17. 🧬 Generics

**Dart:**

```dart
class Box<T> {
  T value;
  Box(this.value);
}
```

**Swift:**

```swift
class Box<T> {
  var value: T
  init(value: T) {
    self.value = value
  }
}
```

---

## 🎯 Summary Table

| Feature           | Dart                     | Swift                                 |
| ----------------- | ------------------------ | ------------------------------------- |
| Platform          | Cross-platform (Flutter) | iOS/macOS native                      |
| Null Safety       | Yes                      | Yes                                   |
| Extension Methods | Yes                      | Yes                                   |
| Async/Await       | Yes                      | Yes                                   |
| Mixins            | Yes                      | No (uses protocols instead)           |
| Hot Reload        | Yes (Flutter)            | Yes (Xcode Preview, but less dynamic) |



