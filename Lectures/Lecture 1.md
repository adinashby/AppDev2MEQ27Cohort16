# Lecture 1 - Dart Programming Basics for Flutter Development

Flutter uses the Dart programming language to build cross-platform mobile applications. This lecture introduces you to essential Dart concepts needed to start developing apps with Flutter. Each section includes code examples and explanations.

## 1. Dart Syntax and Structure

Every Dart program starts with a `main()` function, which acts as the entry point. Statements in Dart end with a semicolon (`;`), and indentation is used for code blocks, similar to other C-style languages.

```dart
void main() {
  print('Hello, Dart!');
}
```

### Comments

- **Single-line**: `// This is a comment`
- **Multi-line**:
  ```dart
  /* This is a 
     multi-line comment */
  ```

## 2. Variables and Data Types

Dart is statically typed but supports type inference using `var`.

### Variable Types

- `var`: Automatically infers the type.
- `final`: A variable that can only be set once (runtime constant).
- `const`: Compile-time constant.

```dart
var name = 'Adin';
final age = 28;
const pi = 3.14;
```

### Common Data Types

- `int`, `double` for numbers
- `String` for text
- `bool` for boolean values

```dart
int year = 2025;
double price = 29.99;
String greeting = 'Hello';
bool isOnline = true;
```

### Null Safety

Dart uses null safety to avoid common runtime errors.

```dart
String? nickname; // nullable
String fullName = 'Adin Ashby'; // non-nullable
```

## 3. Control Flow

Control flow determines how code executes based on conditions.

### Conditional Statements

```dart
if (score > 90) {
  print('Excellent!');
} else if (score > 70) {
  print('Good!');
} else {
  print('Keep trying!');
}
```

### Switch Case

```dart
switch (grade) {
  case 'A':
    print('Awesome!');
    break;
  case 'B':
    print('Nice!');
    break;
  default:
    print('Try harder.');
}
```

### Loops

```dart
for (int i = 0; i < 5; i++) {
  print(i);
}

while (condition) {
  // Loop
}

do {
  // Loop body
} while (condition);
```

## 4. Functions

Functions are reusable blocks of code.

```dart
void greet(String name) {
  print('Hello, $name!');
}

int add(int a, int b) => a + b;
```

### Parameters

- **Positional (optional)**:
  ```dart
  void log(String msg, [String? level]) {
    print('$level: $msg');
  }
  ```

- **Named**:
  ```dart
  void greetUser(String name, {int age = 0}) {
    print('Hello $name, age: $age');
  }
  ```

## 5. Collections

Dart has built-in collections like Lists, Sets, and Maps.

### List

```dart
List<String> fruits = ['Apple', 'Banana'];
fruits.add('Orange');
```

### Set

```dart
Set<int> numbers = {1, 2, 3};
```

### Map

```dart
Map<String, dynamic> user = {
  'name': 'Adin',
  'age': 28
};
```

### Collection Operators

- Spread operator (`...`)
- Collection if/for

```dart
var nav = ['Home', if (loggedIn) 'Logout'];
var list = [1, 2, ...[3, 4]];
```

## 6. Object-Oriented Programming (OOP)

Dart is object-oriented and supports classes and inheritance.

### Class & Object

```dart
class Car {
  String brand;
  Car(this.brand);

  void drive() {
    print('$brand is driving');
  }
}

var myCar = Car('Tesla');
myCar.drive();
```

### Inheritance

```dart
class ElectricCar extends Car {
  ElectricCar(String brand) : super(brand);
}
```

### Mixins

```dart
mixin MusicSystem {
  void playMusic() => print("Playing music...");
}
```

### Getters & Setters

```dart
class Circle {
  double radius;
  Circle(this.radius);

  double get area => 3.14 * radius * radius;
}
```

## 7. Null Safety Deep Dive

Dart enforces null safety by default.

```dart
String? name;
print(name ?? 'No name'); // Default value if null

String? user;
print(user?.length); // Safe access
```

## 8. Asynchronous Programming

Async programming allows non-blocking operations.

### Futures & `async`/`await`

```dart
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Data Loaded';
}
```

### Streams

```dart
Stream<int> numberStream() async* {
  for (int i = 0; i < 3; i++) {
    yield i;
    await Future.delayed(Duration(seconds: 1));
  }
}
```

## 9. Exception Handling

To handle errors gracefully:

```dart
try {
  int result = 10 ~/ 0;
} catch (e) {
  print('Error: $e');
} finally {
  print('Execution finished');
}
```

You can also define **custom exceptions** using classes.

## 10. Packages and Libraries

Use external packages to extend your app’s functionality.

### Importing

```dart
import 'dart:math';
import 'package:flutter/material.dart';
```

### Managing Dependencies

Add packages in `pubspec.yaml`:

```yaml
dependencies:
  http: ^0.14.0
```

Install using:

```bash
flutter pub get
```

## 11. Dart Developer Tools

### Useful CLI Commands

- **Run Dart file**: `dart run filename.dart`
- **Format code**: `dart format .`
- **Analyze code**: `dart analyze`
- **Playground**: Use [https://dartpad.dev](https://dartpad.dev)

## Conclusion

These Dart basics form the foundation for developing apps in Flutter. Mastering these topics will help you build efficient, readable, and scalable mobile applications.

## Some Examples

```dart
void main() {
  print('Hiii');
  
  var number = 42;
  print(number);
  
  int number2 = 33;
  print(number2);
  
  // this is a comment
  
  /*
   * Multi-line 
   * comment
   * */
  
  print("My number is " + number2.toString() + ".");
  print("My number is ${number2}.");
  
  
  late int myInt;
  myInt = 4;
  
  print(myInt);
  
  final name = 'Bob';
  print(name);
  
  //name = 'Alice';
  
  const name2 = 'George';
  print(name2);
  
//   var list = const [99, 88];
//   list[0] = 55;
  
//   print(list);
  
  var foo = const [];
  foo = [1, 2, 3];
  
  foo[0] = 123;
  //foo = 'james';
  
  print(foo);
  
  const Object i = 3; 
  const list = [i as int];
}
```