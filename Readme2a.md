
# Exp2a – Flutter Basics

This project demonstrates a simple Flutter UI layout using **Text**, **Image**, and **Container** widgets.

## 📌 Features

* Displays a styled **Text widget** (`Hello Flutter!`).
* Loads an **Image from the Internet** (owl picture).
* Shows a **Container widget** with background color, padding, and rounded corners.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';

class Exp2aPage extends StatelessWidget {
  const Exp2aPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.all(16),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          const Text(
            "Hello Flutter!",
            style: TextStyle(
              fontSize: 24,
              fontWeight: FontWeight.bold,
              color: Colors.blue,
            ),
          ),
          const SizedBox(height: 20),
          Image.network(
            "https://flutter.github.io/assets-for-api-docs/assets/widgets/owl.jpg",
            height: 150,
          ),
          const SizedBox(height: 20),
          Container(
            padding: const EdgeInsets.all(12),
            decoration: BoxDecoration(
              color: Colors.amber[200],
              borderRadius: BorderRadius.circular(8),
            ),
            child: const Text("This is inside a Container widget."),
          ),
        ],
      ),
    );
  }
}
```

## ▶️ Running the Code

1. Ensure you have Flutter SDK installed.
2. Create a new Flutter project:

   ```bash
   flutter create exp2a_demo
   cd exp2a_demo
   ```
3. Replace the contents of `lib/main.dart` with:

   ```dart
   import 'package:flutter/material.dart';
   import 'exp2a.dart'; // save your given file as exp2a.dart in lib folder

   void main() {
     runApp(const MyApp());
   }

   class MyApp extends StatelessWidget {
     const MyApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Exp2aPage(),
         ),
       );
     }
   }
   ```
4. Run the app:

   ```bash
   flutter run
   ```

## 📸 Output Preview

* A **blue "Hello Flutter!" text**.
* An **owl image** fetched from the network.
* A **container with amber background** and text inside.

