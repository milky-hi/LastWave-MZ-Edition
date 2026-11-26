# LastWave MZ Edition

An independent community fork of LastWave Native focused initially on app-private offline downloads and clearer storage visibility.

## What this fork changes

- New default offline audio downloads are written beneath the app's private files directory: `files/offline_downloads/<download-folder>/...`.
- Optional `.lrc` lyric sidecars are written beside the corresponding private audio files.
- A user-selected Storage Access Framework (SAF) folder remains an explicit alternative destination. Choosing a SAF folder means the user has opted into that external location.
- App-private files are not sent to Android's media scanner, so new private downloads should not appear in the system-wide music library.
- The Storage screen reports device-volume capacity/available bytes and measures the private offline-download directory. It also reuses the upstream download count/size, cache controls, clear-download action and Downloads management flow.

## Important storage facts

App-private storage is an organization/privacy choice, not cloud storage or compression. Audio still occupies the same physical device storage. Android removes app-private files when the app is uninstalled or its data is cleared. Existing downloads created by an earlier version are not automatically migrated by this change; they may remain in their previous public or user-selected location until the user manages them.

## Build

Use Android Studio with the JDK version supported by the project, install the Android SDK platform/build-tools required by `app/build.gradle.kts`, then open this folder as a Gradle project. Or run:

```bash
./gradlew :app:assembleDebug
```

On Windows:

```powershell
.\gradlew.bat :app:assembleDebug
```

The debug APK, if the build succeeds, is normally at `app/build/outputs/apk/debug/app-debug.apk`.

## Before publishing

1. Build with the repository's GitHub Actions workflow or locally.
2. Install on a test Android phone and test a new download, playback after force-stop/relaunch, lyrics, delete-one/delete-all, cache clear, SAF custom folder, and app upgrade.
3. Confirm new default downloads do not appear in the public Music folder and that Storage reports their size.
4. Review the upstream license and notices. This repository includes GPL-3.0; distribute the derivative under GPL-3.0 and retain required notices/source.
5. Do not imply this is an official LastWave release. Keep upstream attribution and clearly label it an independent fork.

## Scope note

This fork does not claim a cloud-backed download system, an offline-download quota, automatic cleanup of user downloads, or a verified APK. The cache-size setting controls cache policy, not the size of saved offline songs.
