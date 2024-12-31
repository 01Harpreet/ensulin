# Milestone 1: Login Screen

## Goal
Create a login screen that allows users to log in with email and password.

## Tasks
1. Set up Firebase Authentication for managing user accounts.
2. Design a basic UI with fields for email and password.
3. Add functionality to handle login, logout, and error messages.

## Tools Used
- Flutter
- Firebase Authentication
- Visual Studio Code

## Steps Taken
1. **Firebase Setup**:
   - Created a Firebase project and added the Android and iOS apps.
   - Downloaded and added `google-services.json` (for Android) and `GoogleService-Info.plist` (for iOS) to the Flutter app.
   - Enabled Firebase Authentication in the Firebase console.

2. **Login Screen UI**:
   - Designed a simple UI in Flutter using `TextField` for email/password input and `ElevatedButton` for login.

3. **Login Functionality**:
   - Connected the login screen to Firebase for user authentication.
   - Added input validation (e.g., email format check, empty fields check).

## Challenges Faced
- **Issue**: Firebase initialization failed on iOS.
  - **Solution**: Ensured the `GoogleService-Info.plist` file was correctly added to the Xcode project.
- **Issue**: Login button did nothing initially.
  - **Solution**: Added `onPressed` logic to the button to handle Firebase login requests.

## Code Snippet
```dart
import 'package:flutter/material.dart';
import 'package:firebase_auth/firebase_auth.dart';

class LoginScreen extends StatelessWidget {
  final TextEditingController emailController = TextEditingController();
  final TextEditingController passwordController = TextEditingController();

  Future<void> login() async {
    try {
      await FirebaseAuth.instance.signInWithEmailAndPassword(
        email: emailController.text.trim(),
        password: passwordController.text.trim(),
      );
      print('Login Successful');
    } catch (e) {
      print('Login Failed: $e');
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Login')),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            TextField(
              controller: emailController,
              decoration: InputDecoration(labelText: 'Email'),
            ),
            TextField(
              controller: passwordController,
              decoration: InputDecoration(labelText: 'Password'),
              obscureText: true,
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: login,
              child: Text('Login'),
            ),
          ],
        ),
      ),
    );
  }
} 
