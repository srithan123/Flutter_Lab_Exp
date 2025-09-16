
# Exp3 – Flutter Responsive Layout

This project demonstrates **responsive UI design in Flutter** using `MediaQuery` to adapt the layout based on screen size.

## 📌 Features

* Uses `MediaQuery` to detect the device screen width.
* Dynamically switches background color and text based on screen size:

  * **Small Screen (≤ 600px width)** → Blue background.
  * **Large Screen (> 600px width)** → Green background.
* Displays the current screen width in pixels.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';

class Exp3Page extends StatelessWidget {
  const Exp3Page({super.key});

  @override
  Widget build(BuildContext context) {
    var size = MediaQuery.of(context).size;
    bool isLarge = size.width > 600;

    return Center(
      child: Container(
        padding: const EdgeInsets.all(20),
        color: isLarge ? Colors.green[200] : Colors.blue[200],
        child: Text(
          isLarge
              ? "Large Screen Layout (${size.width}px)"
              : "Small Screen Layout (${size.width}px)",
          style: const TextStyle(fontSize: 18),
        ),
      ),
    );
  }
}
```

## ▶️ Running the Code

1. Add the file `exp3.dart` inside your project’s `lib` folder.
2. Update `main.dart` as:

   ```dart
   import 'package:flutter/material.dart';
   import 'exp3.dart';

   void main() {
     runApp(const MyApp());
   }

   class MyApp extends StatelessWidget {
     const MyApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Exp3Page(),
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

* On a **small screen (< 600px)** → Blue background with `"Small Screen Layout"`.
* On a **large screen (> 600px)** → Green background with `"Large Screen Layout"`.

