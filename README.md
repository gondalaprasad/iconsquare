# ICON Square Android app

A thin Android shell (Capacitor) that opens the live shop at https://iconsquare.store.
The website itself is NOT in this repository. Shop changes appear in the app at once; rebuild only to change the app's name, icon or version.

## Get the APK
1. GitHub, this repository, **Actions** tab, **Build Android APK**.
2. Open the latest run (green tick), scroll to **Artifacts**, download `iconsquare-debug-apk`.
3. Unzip, copy `app-debug.apk` to the phone, install (allow "install unknown apps").
4. To rebuild: Actions, Build Android APK, **Run workflow**.

## Change the icon
Add a 1024x1024 PNG at `assets/icon.png` (Add file, Upload files), commit; the next build uses it.

## Change name, address or package ID
Edit `capacitor.config.json` (`appName`, `server.url`, `appId`). The package ID must never change once the app is on the Play Store.

## Play Store later
This build is a debug-signed APK, fine for installing directly. The Play Store needs a release-signed `.aab` with your own keystore (kept as an encrypted GitHub secret, never committed).

## Known limits
- Google sign-in buttons often do not work inside an app webview (Google blocks it). Use WhatsApp or email code login in the app.
- Native push notifications need Firebase (FCM) and an extra plugin; not included yet.
