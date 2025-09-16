
# Exp4 – Flutter Navigation (Navigator & Routes)

This project demonstrates how to use the **Navigator widget** and **named routes** in Flutter to move between multiple screens.

## 📌 Features

* Implements **two screens** (`FirstScreen` and `SecondScreen`).
* Uses `Navigator.pushNamed()` to navigate forward.
* Uses `Navigator.pop()` to go back.
* Demonstrates the concept of **routing and navigation** in Flutter.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';

class Exp4Page extends StatelessWidget {
  const Exp4Page({super.key});

  @override
  Widget build(BuildContext context) {
    return Navigator(
      onGenerateRoute: (settings) {
        if (settings.name == '/second') {
          return MaterialPageRoute(builder: (_) => const SecondScreen());
        }
        return MaterialPageRoute(builder: (_) => FirstScreen());
      },
    );
  }
}

class FirstScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(
      child: ElevatedButton(
        onPressed: () => Navigator.pushNamed(context, '/second'),
        child: const Text("Go to Second Screen"),
      ),
    );
  }
}

class SecondScreen extends StatelessWidget {
  const SecondScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Center(
      child: ElevatedButton(
        onPressed: () => Navigator.pop(context),
        child: const Text("Back"),
      ),
    );
  }
}
```

## ▶️ Running the Code

1. Add this file (`exp4.dart`) inside your `lib` folder.
2. Update `main.dart`:

   ```dart
   import 'package:flutter/material.dart';
   import 'exp4.dart';

   void main() {
     runApp(const MyApp());
   }

   class MyApp extends StatelessWidget {
     const MyApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Exp4Page(),
         ),
       );
     }
   }
   ```
3. Run the app:

   ```bash
   flutter run
   ```

## 📸 Output Preview

* **First Screen** → Button `"Go to Second Screen"`.
* **Second Screen** → Button `"Back"`.
* Navigation works both ways using **Navigator push & pop**.


