# Abbasia Sunday Crew — Firebase/PWA package

## Files
- `sunday_crew_firestore.html` — the existing app, wired to your Firebase project.
- `firestore.rules` — secure Firestore rules for student/leader roles and realtime communication.
- `manifest.json` — installable PWA metadata.
- `sw.js` — service worker/offline shell.
- `icon-180.png`, `icon-192.png`, `icon-512.png` — home-screen/app icons.

## Firebase Console setup
1. Authentication → Sign-in method → enable **Email/Password**.
2. Firestore Database → Rules → replace the open `allow read, write: if true` rules with the included `firestore.rules`.
3. Keep Cloud Firestore as the source of truth. Realtime Database is not required by this version.
4. A first leader must exist in Firebase Auth and have a matching `leaders/{uid}` document before the in-app “create leader” feature can be used.

## Important
Do not put a Firebase service-account JSON or private key in the web app. The Firebase Web API key in the HTML is a normal client configuration value; Firestore Security Rules are what protect the data.

## Hosting
Upload all files to the same folder on GitHub Pages or another HTTPS host. PWA installation requires HTTPS (localhost is also supported for local testing).
