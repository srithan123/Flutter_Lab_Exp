
# Exp2b – Flutter Layout Widgets

This project demonstrates how to use **Row**, **Column**, and **Stack** widgets in Flutter to arrange UI elements.

## 📌 Features

* **Row Example**: Displays three colored stars arranged horizontally with equal spacing.
* **Column Example**: Displays a list of text items arranged vertically.
* **Stack Example**: Overlays widgets on top of each other with alignment.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';

class Exp2bPage extends StatelessWidget {
  const Exp2bPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        const Text("Row Example"),
        Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: const [
            Icon(Icons.star, color: Colors.red),
            Icon(Icons.star, color: Colors.green),
            Icon(Icons.star, color: Colors.blue),
          ],
        ),
        const SizedBox(height: 20),
        const Text("Column Example"),
        Column(
          children: const [Text("Item 1"), Text("Item 2"), Text("Item 3")],
        ),
        const SizedBox(height: 20),
        const Text("Stack Example"),
        Expanded(
          child: Stack(
            children: [
              Container(color: Colors.yellow),
              Align(
                alignment: Alignment.center,
                child: Container(color: Colors.red, width: 100, height: 100),
              ),
              const Align(
                alignment: Alignment.bottomRight,
                child: Icon(Icons.star, size: 50),
              ),
            ],
          ),
        ),
      ],
    );
  }
}
```

## ▶️ Running the Code

1. Create a new Flutter project or add this file (`exp2b.dart`) inside the `lib` folder.
2. Update `main.dart` as:

   ```dart
   import 'package:flutter/material.dart';
   import 'exp2b.dart';

   void main() {
     runApp(const MyApp());
   }

   class MyApp extends StatelessWidget {
     const MyApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Exp2bPage(),
         ),
       );
     }
   }
   ```
3. Run the app with:

   ```bash
   flutter run
   ```

## 📸 Output Preview

* A **row** with three stars (red, green, blue).
* A **column** with three text items.
* A **stack** with:

  * A yellow background.
  * A centered red square.
  * A star icon aligned at the bottom-right corner.


