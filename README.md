# LEGEND EDITOR

Professional Android video editor (work in progress).

## Status: Phase 0 (build pipeline), NOT yet verified

This repository contains only a Kotlin + Jetpack Compose launch screen and a
GitHub Actions workflow that builds a debug APK. It has not been built yet.
Phase 0 is complete only when a GitHub Actions run is green and the APK
installs and opens on a device.

## How the APK is built

- Workflow: `.github/workflows/android.yml`
- Triggers: every push, or manually via Actions > Build Debug APK > Run workflow
- Toolchain: JDK 17, Gradle 8.10.2 (installed by the workflow), Android Gradle
  Plugin 8.7.3, Kotlin 2.0.21, Compose BOM 2024.10.01
- Output: artifact `LEGEND-EDITOR-debug-apk` (a ZIP containing `app-debug.apk`)
- No Gradle wrapper is committed. The workflow installs a pinned Gradle version.

## Known limitation

Each CI run creates a new debug signing key, so installing a newer build over an
older one can fail. Uninstall the old build first.

## Feature status

| Item | Status |
|---|---|
| Android project (Kotlin, Compose) | Written, unbuilt |
| GitHub Actions debug APK build | Written, unbuilt |
| Launch screen | Written, unbuilt |
| Fixed debug signing key | Pending |
| Phase 1 (home, navigation, projects) | Not started |
