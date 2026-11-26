# LastWave MZ Edition — Smart Storage update

This fork adds a device-storage overview to the existing Storage settings screen.

## Added
- Displays total internal-storage capacity and currently available space.
- Displays the actual byte size of files under the app-private `files/offline_downloads` directory.
- Refreshes these figures through the existing Storage screen refresh cycle.
- Reuses the existing downloaded-music count/size, cache limit, cache clearing, delete-all-downloads, and Downloads management flows.

## Existing download location
The supplied source already writes default offline downloads to `context.filesDir/offline_downloads/<folder>` in `TrackDownloadManagerStorage.kt`. A user-selected SAF folder remains an explicit external destination. App-private files still consume physical device storage and are removed when app data is cleared or the app is uninstalled.

## Not implemented in this update
- A hard maximum quota for offline song downloads. The existing cache-size slider controls cached artwork/streamed audio only, not downloaded music.
- Automated cache expiry policies beyond the cache behaviour already present in the project.

## Verification
Source changes were reviewed locally. Android compilation could not be completed in this environment because Gradle 9.3.1 could not be downloaded (`UnknownHostException: services.gradle.org`). Build and device testing are still required before publishing an APK/release.
