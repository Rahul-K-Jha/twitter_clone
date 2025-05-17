# Twitter Clone

A Flutter-based Twitter clone featuring authentication, home feed, navigation drawer, and more.

## Features

- **Authentication**: Sign up and log in with email or phone, Google sign-in supported.
- **Home Feed**: Main timeline screen.
- **Navigation Drawer**: Access to user options and navigation.
- **Terms & Conditions**: Dedicated page for Twitter-like terms.
- **State Management**: Uses `provider` for managing UI state (e.g., toggling between email/phone input).
- **Firebase Integration**: Uses Firebase for authentication and backend services.
- **Environment Variables**: Sensitive keys are loaded from a `.env` file using `flutter_dotenv`.

## Getting Started

### Prerequisites

- [Flutter](https://flutter.dev/docs/get-started/install)
- A Firebase project (see below for setup)

### Setup

1. **Clone the repository**

2. **Install dependencies**
   ```sh
   flutter pub get
   ```

3. **Configure Firebase**
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/).
   - Enable Email/Password and Google authentication.
   - Download your `google-services.json` and place it in `android/app/`.

4. **Environment Variables**
   - Create a `.env` file in the project root:
     ```
     FIREBASE_API_KEY=your_api_key
     FIREBASE_APP_ID=your_app_id
     FIREBASE_MESSAGING_SENDER_ID=your_sender_id
     FIREBASE_PROJECT_ID=your_project_id
     FIREBASE_STORAGE_BUCKET=your_storage_bucket
     ```
   - **Do not commit your `.env` file!** (It is already in `.gitignore`.)

5. **Run the app**
   ```sh
   flutter run
   ```

## Project Structure

- `lib/main.dart` - App entry point, initializes Firebase and dotenv, sets up providers.
- `lib/firebase_options.dart` - Loads Firebase config from environment variables.
- `lib/logic_source/provider_logic/business_logic.dart` - Provider for UI logic (e.g., toggling input type).
- `lib/layout/pages/authentication/` - Authentication screens (login, signup, method selection).
- `lib/layout/pages/home_screen/` - Home feed screen.
- `lib/layout/pages/drawer/` - Navigation drawer.
- `lib/layout/pages/twitter_conditions/` - Terms and conditions page.
- `lib/layout/widgets/` - Reusable widgets (e.g., custom app bar).

## Dependencies

- `firebase_core`
- `firebase_auth`
- `google_sign_in`
- `provider`
- `flutter_dotenv`
- `auto_size_text`
- `url_launcher`
- `webview_flutter`

## Notes

- For production, ensure your `.env` is securely managed and not included in version control.
- You may want to provide a `.env.example` for other developers.
