# ThinktoEra Productivity

ThinktoEra is a calm, cross-platform productivity workspace for planning work, managing tasks and projects, reviewing progress, and protecting time for deep focus.

The current release targets Windows. The Flutter codebase is structured to support Android, iOS, macOS, Linux, and Web in future releases.

## Features

### Overview

- Dashboard with daily activity, priorities, overdue work, and momentum
- Calendar-based productivity history
- Weekly reviews and completion insights
- Monthly Review placeholder for a future release

### Planning

- Daily planner with date-based planning
- Reusable built-in and custom planner templates
- Tasks with categories, priorities, due dates, filtering, and sorting
- Projects with task summaries, progress, archive controls, and details
- Weekly and Monthly Planner placeholders

### Focus and organization

- Focus Mode with configurable session presets
- Local session restoration and completion notifications
- Kanban and AI Assistant placeholders
- Local reminders and notification center

### Account and privacy

- Google Sign-In and Firebase Authentication
- Cross-device synchronization for Firestore-backed data
- User-data export
- Account and cloud-data deletion
- Light and dark themes
- Responsive desktop, split-view, tablet, and mobile layouts
- No advertising, location collection, Firebase Analytics, or Firebase Crashlytics

## Technology

- [Flutter](https://flutter.dev/) and Dart
- [Riverpod](https://riverpod.dev/) for application state
- [GoRouter](https://pub.dev/packages/go_router) for navigation
- [Firebase Authentication](https://firebase.google.com/docs/auth) for accounts
- [Cloud Firestore](https://firebase.google.com/docs/firestore) for synchronized data
- `flutter_local_notifications` for reminders
- Optional [Sentry](https://sentry.io/) error reporting

## Data storage

Authenticated user data is stored under account-scoped Firestore paths:

```text
users/{userId}/tasks
users/{userId}/projects
users/{userId}/planner
users/{userId}/plannerTemplates
users/{userId}/weeklyReviews
users/{userId}/settings
```

Focus sessions and some notification state are stored locally and may not synchronize between devices.

See the complete [Privacy Policy](privacy-policy.html).

## Project structure

```text
lib/
├── app/
│   ├── router/          # GoRouter configuration
│   └── theme/           # Color, theme, and gradient definitions
├── core/
│   ├── connectivity/    # Connectivity and synchronization status
│   ├── layout/          # Responsive application shell
│   ├── services/        # Notifications and shared services
│   └── widgets/         # Reusable UI, motion, and startup widgets
├── features/
│   ├── auth/
│   ├── calendar/
│   ├── dashboard/
│   ├── feedback/
│   ├── focus/
│   ├── notifications/
│   ├── planner/
│   ├── projects/
│   ├── tasks/
│   └── weekly_review/
├── firebase_options.dart
└── main.dart
```

Feature modules generally follow presentation, application, domain, and data layers where the feature requires them.

## Requirements

- Flutter SDK compatible with the version declared in `pubspec.yaml`
- Dart SDK compatible with the version declared in `pubspec.yaml`
- A Firebase project with Authentication and Cloud Firestore enabled
- Visual Studio with Desktop development with C++ for Windows builds
- Platform-specific tooling for any additional Flutter target

Check your environment:

```powershell
flutter doctor
```

## Local setup

1. Clone the repository:

   ```powershell
   git clone https://github.com/MR-Anon1/thinktoera.git
   cd thinktoera
   ```

2. Install dependencies:

   ```powershell
   flutter pub get
   ```

3. Configure Firebase for your own Firebase project:

   ```powershell
   dart pub global activate flutterfire_cli
   flutterfire configure
   ```

4. Enable the required authentication provider in Firebase Console:

   - Open **Authentication → Sign-in method**.
   - Enable Google Sign-In.
   - Add the platform configuration required for each target you build.

5. Create and deploy account-scoped Firestore Security Rules. At minimum, rules should require authentication and ensure `request.auth.uid` matches the `{userId}` path segment.

6. Run the Windows application:

   ```powershell
   flutter run -d windows
   ```

Do not commit private service-account credentials, signing certificates, Sentry DSNs, or other secrets.

## Optional Sentry configuration

Sentry is disabled when no DSN is supplied. To enable error reporting for a build:

```powershell
flutter run -d windows --dart-define=SENTRY_DSN=YOUR_SENTRY_DSN
```

The application disables default personally identifiable information and performance tracing in its Sentry configuration. Review the privacy policy and your Sentry project settings before enabling reporting in a distributed build.

## Splash screen

Native splash assets are generated with `flutter_native_splash`:

```powershell
dart run flutter_native_splash:create
```

The native launch screen hands off to the animated ThinktoEra startup experience. A full application restart is required to test the native splash screen.

## Quality checks

Format the code:

```powershell
dart format lib test
```

Run static analysis:

```powershell
flutter analyze
```

Run automated tests:

```powershell
flutter test
```

## Production build

Build the Windows application:

```powershell
flutter build windows --release
```

The project also contains MSIX metadata in `pubspec.yaml` for Microsoft Store packaging. Review the identity, publisher, version, capabilities, privacy-policy URL, and Store listing details before creating a submission.

## Security and privacy

- Firebase Authentication identifies signed-in users.
- Firestore Security Rules restrict access to account-specific documents.
- Firebase communication uses HTTPS.
- The application does not use Firebase Analytics or Firebase Crashlytics.
- Optional Sentry reporting is controlled at build time.
- The current version contains no advertisements, advertising SDKs, purchases, or subscriptions.
- No location data is requested or collected.

Security issues and sensitive reports should not be posted publicly. Contact the developer directly at [khawalepoorab@gmail.com](mailto:khawalepoorab@gmail.com).

## Roadmap

- Weekly Planner
- Monthly Planner
- Monthly Review
- Kanban workspace
- AI Assistant
- Upgrade options
- Expanded Android, iOS, and Web support

Roadmap items are plans rather than commitments and may change as the project evolves.

## Developer

Developed by **Poorab Khawale**.

- GitHub: [MR-Anon1](https://github.com/MR-Anon1)
- Email: [khawalepoorab@gmail.com](mailto:khawalepoorab@gmail.com)
- Privacy Policy: [privacy-policy.html](privacy-policy.html)

## License

No open-source license has been granted for this repository. Unless a separate license file states otherwise, all rights are reserved by the developer.
