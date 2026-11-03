# Qur'an Themes (Android)

Offline Android app for Qur'an Themes: 135 themes in ten gateways, all 6,236 verses in Arabic, two English translations, and al-Mukhtasar and Ibn Kathir tafsir.

Every push to `main` builds the app with GitHub Actions and attaches the outputs to a new release (see the Releases page). The app targets Android 16 (API 36), as Google Play requires, and runs on Android 7.0 and later. To build locally: open this folder in Android Studio and run Build > Generate Signed Bundle / APK, or `gradle :app:assembleRelease`.

## Signing

Two outputs come from every build:

- `QuranThemes.apk`, for installing directly. It is signed with the testing key in `signing/testing.jks`, so each new build installs over the previous one. This repository is public, so that key is not secret; never use it for Google Play.
- `QuranThemes-play.aab`, the bundle to upload to Google Play. It is signed with the private upload key, which the build reads from four repository secrets: `UPLOAD_KEYSTORE_B64` (the keystore file, base64-encoded), `UPLOAD_KEYSTORE_PASSWORD`, `UPLOAD_KEY_ALIAS` and `UPLOAD_KEY_PASSWORD`. Without those secrets the build skips the bundle. Turn on Play App Signing in Play Console so Google holds the key that signs the app for users.

## Privacy policy

`docs/privacy.html` is the app's privacy policy, served by GitHub Pages at https://hunaid3.github.io/Qur-an-themes/privacy.html.

## Fonts

Amiri Quran, Amiri, Reem Kufi, Marcellus, Spectral and IBM Plex Sans are bundled under the SIL Open Font License (see `app/src/main/assets/www/fonts/OFL.txt`), so the app renders correctly offline.
