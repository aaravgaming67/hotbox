# HotBox Website

Static booking website for HotBox - PC & PS Gaming Lounge, Thane.

## GitHub Pages Setup

If you only uploaded the files to a GitHub repository, the site will not automatically open as a website. You need to enable GitHub Pages:

1. Open your GitHub repository.
2. Go to `Settings`.
3. Go to `Pages`.
4. Under `Build and deployment`, choose:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Click `Save`.
6. Wait 1-3 minutes, then open the Pages URL GitHub gives you.

The website files must be in the repository root, meaning `index.html`, `styles.css`, `script.js`, and `firebase-config.js` should not be inside an extra folder unless GitHub Pages is pointed to that folder.

## PS5 Pricing

- 1 player on PS5: Rs 100 per hour
- 2 players on one PS5: Rs 180 per hour

## Firebase Setup

GitHub Pages only hosts the website. It does not deploy Firestore rules or create a Firebase backend. To make online bookings work:

1. Create a Firebase project.
2. Enable Firestore Database.
3. Create a Web App in Firebase project settings.
4. Paste the Web App config into `firebase-config.js`.
5. Install Firebase CLI if needed:

```bash
npm install -g firebase-tools
```

6. Login and deploy:

```bash
firebase login
firebase init
firebase deploy
```

The website saves bookings locally until `firebase-config.js` contains real Firebase values. After that, new bookings are also written to the `bookings` Firestore collection.

## Quick Fixes

- If the GitHub page is blank, check that `script.js` and `firebase-config.js` were uploaded beside `index.html`.
- If the design is missing, check that `styles.css` was uploaded beside `index.html`.
- If booking works but says local only, add real Firebase values in `firebase-config.js`.
- If Firebase saves fail, deploy `firestore.rules` with Firebase CLI.
