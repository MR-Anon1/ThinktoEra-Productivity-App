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
- See the complete [Privacy Policy](privacy-policy.html).

## Security and privacy

- Firebase Authentication identifies signed-in users.
- Firestore Security Rules restrict access to account-specific documents.
- Firebase communication uses HTTPS.
- The application does not use Firebase Analytics or Firebase Crashlytics.
- Optional Sentry reporting is controlled at build time.
- The current version contains no advertisements, advertising SDKs, purchases, or subscriptions.
- No location data is requested or collected.

## Developer

Developed by **Poorab Khawale**.

- GitHub: [MR-Anon1](https://github.com/MR-Anon1)
- Instagram: [poorab_khawale](https://instagram.com/poorab_khawale)
- Privacy Policy: [privacy-policy.html](privacy-policy.html)

## License

No open-source license has been granted for this repository. Unless a separate license file states otherwise, all rights are reserved by the developer.
