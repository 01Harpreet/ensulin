---
#### **docs/milestone-1.md** (To be added as you progress)
Document your first milestone (e.g., Login Screen) here once completed.

```markdown
# Milestone 1: Login Screen

## Tools Used
- Flutter
- Firebase Authentication

## Progress
1. Connected Firebase to the Flutter app.
2. Created a login UI with email and password fields.

## Challenges Faced
- Encountered an error with Firebase configuration. Fixed it by downloading the correct `google-services.json` file.

## Code Snippet
```dart
// Sample Flutter login UI code
import 'package:flutter/material.dart';

class LoginScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Login')),
      body: Center(
        child: Column(
          children: [
            TextField(decoration: InputDecoration(hintText: 'Email')),
            TextField(decoration: InputDecoration(hintText: 'Password')),
            ElevatedButton(onPressed: () {}, child: Text('Login'))
          ],
        ),
      ),
    );
  }
}
