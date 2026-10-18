# Firebase setup for Lunch Anime Club

This repository is hosted on GitHub Pages. Firebase can provide Google sign-in and a shared Firestore database on the free Spark plan, subject to Firebase's current usage limits.

## 1. Create a Firebase project
1. Open https://console.firebase.google.com/ and choose **Create a project**.
2. Give it a name such as `lunch-anime-club`. Google Analytics is optional.
3. In **Project settings → General**, add a **Web app** and register the app.
4. Copy the web app's Firebase configuration. It contains public client settings; do not copy or share service-account private keys.

## 2. Enable Google sign-in
1. Open **Build → Authentication → Get started**.
2. Under **Sign-in method**, enable **Google** and choose a support email.
3. Under **Settings → Authorized domains**, make sure `cookiebrews1024.github.io` is listed.

## 3. Create Firestore
1. Open **Build → Firestore Database → Create database**.
2. Choose a location appropriate for your club and start in production mode.
3. Review `firestore.rules` in this repository. Replace `OWNER_EMAIL_REPLACE_ME@example.com` with the exact Google account email that should be the owner, then publish the rules in the Firebase console.

## 4. Finish connecting the site
The site is **not connected to Firebase yet**. After creating the project, provide the Firebase **web app config** (apiKey, authDomain, projectId, appId and any other fields Firebase gives you) and the owner email. These are needed to wire up Google sign-in and move club content from browser-only storage to Firestore.

Never share a Firebase service-account JSON file, private key, passwords, or recovery codes. Firebase web configuration is designed to be included in a website; access control must come from Authentication and Firestore rules, not from keeping that config secret.
