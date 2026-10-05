# CoC Upgrade Tracker (Android APK)

## Easiest: build online with GitHub (no installs)
1. Create a free GitHub repo and upload everything in this folder (keep the `.github` folder).
2. Open the repo's **Actions** tab, run **Build APK** (it also runs on every push).
3. When it finishes, download the `coc-upgrade-tracker-apk` artifact, unzip it, and install `app-debug.apk` on your phone (allow "install unknown apps").

## Build locally
Needs Node 18+, JDK 17, Android Studio (SDK).
    npm install
    npx cap add android
    npx cap sync android
Then add to android/app/src/main/AndroidManifest.xml (above <application>):
    <uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
    <uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM"/>
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
Then `npx cap open android` and Build > Build APK(s), or `cd android && ./gradlew assembleDebug`.
