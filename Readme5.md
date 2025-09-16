
# Exp5 – Flutter State Management

This project demonstrates **state management in Flutter** using two approaches:

1. **setState** (local stateful widget).
2. **Provider** (app-wide state management).

## 📌 Features

* **Stateful Example with setState:**

  * Uses a `StatefulWidget` to manage and update a counter value.
  * Calls `setState()` to refresh the UI when the button is pressed.

* **Provider Example:**

  * Uses the `provider` package for global state management.
  * A `ChangeNotifier` (`CounterModel`) manages the counter value.
  * The `Consumer` widget rebuilds only when the model changes.

## 📂 Code Overview

```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';

class Exp5Page extends StatelessWidget {
  const Exp5Page({super.key});

  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (_) => CounterModel(),
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          const Text("Stateful Example with setState:"),
          StatefulCounter(),
          const Divider(),
          const Text("Provider Example:"),
          ConsumerCounter(),
        ],
      ),
    );
  }
}

// Stateful Example
class StatefulCounter extends StatefulWidget {
  @override
  State<StatefulCounter> createState() => _StatefulCounterState();
}

class _StatefulCounterState extends State<StatefulCounter> {
  int count = 0;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text("Count: $count"),
        ElevatedButton(
          onPressed: () => setState(() => count++),
          child: const Text("Increment"),
        ),
      ],
    );
  }
}

// Provider Example
class CounterModel extends ChangeNotifier {
  int count = 0;
  void increment() {
    count++;
    notifyListeners();
  }
}

class ConsumerCounter extends StatelessWidget {
  const ConsumerCounter({super.key});

  @override
  Widget build(BuildContext context) {
    final counter = context.watch<CounterModel>();
    return Column(
      children: [
        Text("Count: ${counter.count}"),
        ElevatedButton(
          onPressed: counter.increment,
          child: const Text("Increment"),
        ),
      ],
    );
  }
}
```

## ▶️ Running the Code

1. Add `provider` to your `pubspec.yaml`:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     provider: ^6.0.5
   ```
2. Save the file as `exp5.dart` inside the `lib` folder.
3. Update `main.dart`:

   ```dart
   import 'package:flutter/material.dart';
   import 'exp5.dart';

   void main() {
     runApp(const MyApp());
   }

   class MyApp extends StatelessWidget {
     const MyApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Exp5Page(),
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

* **Stateful Example** → Button increments a counter using `setState`.
* **Provider Example** → Button increments a counter using a shared state (`Provider`).


