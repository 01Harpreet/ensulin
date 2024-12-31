# Milestone 3: Alerts & Multi-language Support

## Goal
1. Add alerts for sugar and carb intake limits.
2. Enable Punjabi language support.

## Tasks
1. Implement daily limit tracking for sugar and carbs.
2. Add push notifications to alert users when nearing/exceeding limits.
3. Use `flutter_localizations` for multi-language support.

## Tools Used
- Firebase Cloud Messaging (for alerts)
- flutter_localizations package

## Steps Taken
1. **Daily Limit Tracking**:
   - Added a settings screen to let users set their sugar and carb limits.
   - Created logic to calculate remaining sugar/carbs after each scan.

2. **Push Notifications**:
   - Set up Firebase Cloud Messaging to send alerts when limits are exceeded.

3. **Multi-language Support**:
   - Added localization using Flutter’s `intl` package.
   - Created `.arb` files for English and Punjabi translations.

## Challenges Faced
- **Issue**: Translating UI to Punjabi.
  - **Solution**: Used Google Translate for initial translations and validated with a native speaker.

## Code Snippet
```dart
import 'package:flutter/material.dart';

class SettingsScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Settings')),
      body: Center(
        child: Column(
          children: [
            Text('Set Sugar Limit'),
            // Add logic to input sugar limit
          ],
        ),
      ),
    );
  }
}
