# Milestone 2: Scanning Feature

## Goal
Implement a feature to scan food items and retrieve sugar and carb content using APIs.

## Tasks
1. Set up Google Cloud Vision API for image recognition.
2. Connect to Nutritionix API for retrieving nutritional data.
3. Display scanned food item details on the screen.

## Tools Used
- Google Cloud Vision API
- Nutritionix API
- Flutter Camera Package

## Steps Taken
1. **Google Cloud Vision API Setup**:
   - Registered for a Google Cloud project and enabled the Vision API.
   - Generated an API key and added it to the Flutter app.

2. **Nutritionix API Setup**:
   - Signed up for Nutritionix API and obtained an API key.
   - Tested API calls to retrieve nutritional data.

3. **UI for Scanning**:
   - Added a button to access the camera using Flutter's `camera` package.
   - Created a screen to display the scanned item’s nutritional data.

## Challenges Faced
- **Issue**: Camera permission errors on Android.
  - **Solution**: Updated `AndroidManifest.xml` to request camera permissions.
- **Issue**: API calls timing out.
  - **Solution**: Used `http` package with proper error handling for API requests.

## Code Snippet
```dart
import 'package:flutter/material.dart';
import 'package:google_ml_vision/google_ml_vision.dart';

class ScannerScreen extends StatelessWidget {
  // Add your scanning logic here
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Scan Food')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Add scanning logic
          },
          child: Text('Start Scanning'),
        ),
      ),
    );
  }
}
