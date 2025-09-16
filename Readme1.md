
# Flutter Experiments – Integrated App

This project combines multiple **Flutter experiments** into a single application using a **TabBar** navigation system. Each tab demonstrates a different concept in Flutter, from basic widgets to state management.

## 📌 Features

* **Tab Navigation:** Uses `DefaultTabController` with five tabs.
* **Experiments Included:**

  1. **Exp2a – Widgets** → Text, Image, Container basics.
  2. **Exp2b – Layouts** → Row, Column, and Stack layouts.
  3. **Exp3 – Responsive** → Screen-size based UI using `MediaQuery`.
  4. **Exp4 – Navigation** → Moving between screens with `Navigator`.
  5. **Exp5 – State Management** → Using `setState` and `Provider`.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';
import 'exp_2a.dart';
import 'exp_2b.dart';
import 'exp_3.dart';
import 'exp_4.dart';
import 'exp_5.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: DefaultTabController(
        length: 5,
        child: Scaffold(
          appBar: AppBar(
            title: const Text("Flutter Experiments"),
            bottom: const TabBar(
              isScrollable: true,
              tabs: [
                Tab(text: "2a Widgets"),
                Tab(text: "2b Layouts"),
                Tab(text: "3 Responsive"),
                Tab(text: "4 Navigation"),
                Tab(text: "5 State Mgmt"),
              ],
            ),
          ),
          body: const TabBarView(
            children: [
              Exp2aPage(),
              Exp2bPage(),
              Exp3Page(),
              Exp4Page(),
              Exp5Page(),
            ],
          ),
        ),
      ),
    );
  }
}
```

## ▶️ Running the Code

1. Create a Flutter project:

   ```bash
   flutter create flutter_experiments
   cd flutter_experiments
   ```
2. Add your experiment files inside the `lib` folder:

   * `exp_2a.dart`
   * `exp_2b.dart`
   * `exp_3.dart`
   * `exp_4.dart`
   * `exp_5.dart`
3. Update `main.dart` with the above code.
4. Add **provider** dependency for Exp5 in `pubspec.yaml`:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     provider: ^6.0.5
   ```
5. Run the app:

   ```bash
   flutter run
   ```

## 📸 Output Preview

* **Tab 1 (Widgets)** → Displays Text, Image, Container.
* **Tab 2 (Layouts)** → Shows Row, Column, Stack.
* **Tab 3 (Responsive)** → Changes layout by screen width.
* **Tab 4 (Navigation)** → Demonstrates screen navigation.
* **Tab 5 (State Mgmt)** → Demonstrates setState vs Provider.


