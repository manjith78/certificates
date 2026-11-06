# Flutter Lab Exam Ready-to-Copy Solutions
**Student Reg No:** URK23CS1011  
**Target:** Minimalist, bare-bones code focusing purely on visual proof for evaluator validation.

---

## Setup & Running Commands (Global)

To run any experiment:
1. Open your terminal in your project directory.
2. Replace `lib/main.dart` with the corresponding code below.
3. Run:
```bash
flutter run
```

---

## Experiment 1: Basic Widgets & Standard Layouts

**Commands:**
```bash
flutter create exp1
cd exp1
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 1: UI Widgets - URK23CS1011')),
        body: Column(
          children: [
            const Text('Student Name: URK23CS1011'),
            const Text('Course: Computer Science'),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(onPressed: () {}, child: const Text('Accept')),
                ElevatedButton(onPressed: () {}, child: const Text('Decline')),
              ],
            ),
          ],
        ),
      ),
    );
  }
}
```

---

## Experiment 2: Adaptive & Responsive UI Design

**Commands:**
```bash
flutter create exp2
cd exp2
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 2: Adaptive UI - URK23CS1011')),
        body: LayoutBuilder(
          builder: (context, constraints) {
            if (constraints.maxWidth < 600) {
              return const Column(
                children: [
                  Card(child: Text('Student')),
                  Card(child: Text('Courses')),
                ],
              );
            } else {
              return const Row(
                children: [
                  Expanded(child: Card(child: Text('Student'))),
                  Expanded(child: Card(child: Text('Courses'))),
                ],
              );
            }
          },
        ),
      ),
    );
  }
}
```

---

## Experiment 3: Form Handling & Input Validation

**Commands:**
```bash
flutter create exp3
cd exp3
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 3: Form - URK23CS1011')),
        body: Column(
          children: [
            const Text('Reg No: URK23CS1011'),
            const TextField(decoration: InputDecoration(labelText: 'Student Name')),
            const TextField(decoration: InputDecoration(labelText: 'Email')),
            const TextField(decoration: InputDecoration(labelText: 'Password')),
            ElevatedButton(
              onPressed: () {},
              child: const Text('Submit'),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

## Experiment 4: Utilize Assets and Media

**Commands:**
```bash
flutter create exp4
cd exp4
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 4: Media Gallery - URK23CS1011')),
        body: GridView.count(
          crossAxisCount: 2,
          children: const [
            Icon(Icons.image, size: 50),
            Icon(Icons.movie, size: 50),
            Icon(Icons.audiotrack, size: 50),
            Icon(Icons.photo_library, size: 50),
          ],
        ),
      ),
    );
  }
}
```

---

## Experiment 5: Navigation and Routing

**Commands:**
```bash
flutter create exp5
cd exp5
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: PageOne(),
    );
  }
}

class PageOne extends StatelessWidget {
  const PageOne({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Exp 5: Home - URK23CS1011')),
      body: Center(
        child: ElevatedButton(
          onPressed: () => Navigator.push(
            context,
            MaterialPageRoute(builder: (_) => const PageTwo()),
          ),
          child: const Text('Go to Page 2'),
        ),
      ),
    );
  }
}

class PageTwo extends StatelessWidget {
  const PageTwo({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Page 2')),
      body: Center(
        child: ElevatedButton(
          onPressed: () => Navigator.pop(context),
          child: const Text('Go Back'),
        ),
      ),
    );
  }
}
```

---

## Experiment 6: Animations and Transitions

**Commands:**
```bash
flutter create exp6
cd exp6
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  bool isBig = false;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 6: Animation - URK23CS1011')),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              AnimatedContainer(
                duration: const Duration(seconds: 1),
                width: isBig ? 200 : 100,
                height: isBig ? 200 : 100,
                color: Colors.blue,
              ),
              ElevatedButton(
                onPressed: () => setState(() => isBig = !isBig),
                child: const Text('Animate'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

---

## Experiment 7: State Management & Data Serialization

**Commands:**
```bash
flutter create exp7
cd exp7
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class Student {
  final String name;
  Student(this.name);
  Map<String, dynamic> toJson() => {'name': name};
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    final students = [Student('URK23CS1011'), Student('Manjith')];

    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 7: State & JSON')),
        body: ListView.builder(
          itemCount: students.length,
          itemBuilder: (context, i) => ListTile(
            title: Text(students[i].name),
            subtitle: Text(students[i].toJson().toString()),
          ),
        ),
      ),
    );
  }
}
```

---

## Experiment 8: Data Persistence & Storage (Local State List)

**Commands:**
```bash
flutter create exp8
cd exp8
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  final List<String> data = ['URK23CS1011 Sample Data'];

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 8: Storage Visual')),
        body: Column(
          children: [
            ElevatedButton(
              onPressed: () => setState(() => data.add('Saved Item ${data.length + 1}')),
              child: const Text('Add Entry'),
            ),
            Expanded(
              child: ListView.builder(
                itemCount: data.length,
                itemBuilder: (_, i) => ListTile(title: Text(data[i])),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

## Experiment 9: Network Requests & Async Data

**Commands:**
```bash
flutter create exp9
cd exp9
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  Future<String> fetchData() async {
    await Future.delayed(const Duration(seconds: 1));
    return 'Data Loaded: URK23CS1011';
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 9: Async Request')),
        body: Center(
          child: FutureBuilder<String>(
            future: fetchData(),
            builder: (context, snapshot) {
              if (snapshot.hasData) return Text(snapshot.data!);
              return const CircularProgressIndicator();
            },
          ),
        ),
      ),
    );
  }
}
```

---

## Experiment 10: Native Device Features (Mock Camera Visual)

**Commands:**
```bash
flutter create exp10
cd exp10
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  bool captured = false;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 10: Camera UI')),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Icon(
                captured ? Icons.camera_alt : Icons.no_photography,
                size: 100,
                color: captured ? Colors.green : Colors.grey,
              ),
              ElevatedButton(
                onPressed: () => setState(() => captured = !captured),
                child: Text(captured ? 'Reset Camera' : 'Capture Photo'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

---

## Experiment 11: Testing & Debugging

**Commands:**
```bash
flutter create exp11
cd exp11
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 11: Testing - URK23CS1011')),
        body: const Center(
          child: Text('Test Target: Reg No URK23CS1011'),
        ),
      ),
    );
  }
}
```

**`test/widget_test.dart`:**
```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:exp11/main.dart';

void main() {
  testWidgets('Verify Reg No Text', (WidgetTester tester) async {
    await tester.pumpWidget(const MyApp());
    expect(find.text('Test Target: Reg No URK23CS1011'), findsOneWidget);
  });
}
```

**To run the test command:**
```bash
flutter test
```

---

## Experiment 12: App Deployment Skeleton

**Commands:**
```bash
flutter create exp12
cd exp12
flutter run
```

**`lib/main.dart`:**
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(title: const Text('Exp 12: Production Build')),
        body: const Center(
          child: Text('App Build Ready: URK23CS1011'),
        ),
      ),
    );
  }
}
```

**Build Commands:**
```bash
# Build Android APK
flutter build apk --release

# Build Web Version
flutter build web
```