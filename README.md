# Qur'an Themes (Android)

Offline Android app for Qur'an Themes: 135 themes in ten gateways, all 6,236 verses in Arabic, two English translations, and al-Mukhtasar and Ibn Kathir tafsir.

Every push to `main` builds a signed release APK with GitHub Actions and attaches it to a new release (see the Releases page). To build locally: open this folder in Android Studio and run Build > Generate Signed Bundle / APK, or `gradle :app:assembleRelease`.

## Signing

Builds are signed with the testing key in `signing/testing.jks`, so each new build installs over the previous one. This repository is public, so that key is not secret. Before publishing to the Play Store, create a private key and supply it to the build through the environment variables `RELEASE_KEYSTORE`, `RELEASE_KEYSTORE_PASSWORD`, `RELEASE_KEY_ALIAS` and `RELEASE_KEY_PASSWORD` (for example from GitHub Actions secrets).

## Fonts

Amiri Quran, Amiri, Reem Kufi, Marcellus, Spectral and IBM Plex Sans are bundled under the SIL Open Font License (see `app/src/main/assets/www/fonts/OFL.txt`), so the app renders correctly offline.
