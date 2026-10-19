# Dinkar App

![Android Build](https://github.com/sanjay289/dinkar-app/actions/workflows/android-build.yml/badge.svg)

A small offline Android app about Rashtrakavi **Ramdhari Singh 'Dinkar'** (1908–1974): his life, a timeline, major works, honours and a few famous lines (each with a Share button). Hindi by default, with an English toggle (the choice is remembered).

Plain Java + a `WebView` showing a bundled HTML page (`app/src/main/assets/index.html`). No AndroidX, no network permission.

## Build

```
./gradlew assembleDebug
```

The APK lands in `app/build/outputs/apk/debug/`. CI builds it on every push to `master` and uploads it as an artifact.

Only short excerpts of Dinkar's poems are included; his works remain under copyright in India.

## Release signing

`./gradlew assembleRelease` signs the APK when these Gradle properties are set (keep them in `~/.gradle/gradle.properties`, never in the repo):

```
DINKAR_STORE_FILE=/path/to/dinkar-release.jks
DINKAR_STORE_PASSWORD=...
DINKAR_KEY_ALIAS=dinkar
DINKAR_KEY_PASSWORD=...
```

Without them the release APK is built unsigned; debug builds are unaffected.
