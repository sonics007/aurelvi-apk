# Aurelvi APK

Public downloads for Aurelvi, an Android wall panel app for SONOFF NSPanel Pro.
This repository contains **compiled APK files, installation instructions and release automation**.
The Android application source code and signing key are not published here.
The Home Assistant integration is distributed separately.

## Download

[Download the latest APK](https://github.com/sonics007/aurelvi-apk/releases/latest)

Current APK: **0.3.0**, Android package `sk.openpanel.nspanel`, versionCode **5**.
Requires Android 8.0 or newer. The NSPanel Pro target device runs Android 8.1.
This is an initial community build; physical device and Home Assistant testing is still required.

## Install from Windows

Download the `.apk` asset from Releases. Open a terminal in your Android platform-tools folder:

```bat
adb.exe connect PANEL_IP:5555
adb.exe -s PANEL_IP:5555 install -r "C:\path\Aurelvi-0.3.0.apk"
adb.exe -s PANEL_IP:5555 shell am force-stop it.domodreams.nspanel
adb.exe -s PANEL_IP:5555 shell am force-stop sk.openpanel.nspanel
adb.exe -s PANEL_IP:5555 shell am start -n sk.openpanel.nspanel/.MainActivity
```

Replace `PANEL_IP` and the APK path. Confirm any ADB authorization prompt on the panel.
Use `install -r` to keep existing OpenPanel/Aurelvi settings. Updates must have the same signing certificate.
Aurelvi is a separate package from DomoDreams. Verify that Aurelvi runs before setting it as Home:

```bat
adb.exe -s PANEL_IP:5555 shell cmd package set-home-activity sk.openpanel.nspanel/.MainActivity
```

## GitHub updates on the panel

In Aurelvi settings, choose **Update from GitHub** and set:

- Repository: `sonics007/aurelvi-apk`
- APK asset name: leave blank (each release contains one Aurelvi APK).

Aurelvi checks releases periodically. Android installation requires confirmation on the panel.
MQTT and the Home Assistant integration use separate settings. Select the Aurelvi integration mode
when using our own HA integration.

## Maintainer: publish an update

1. Build and sign the APK in the private Android project with the existing signing key.
2. Copy the signed APK into `dist/` with a name such as `Aurelvi-0.3.1.apk`.
3. Update `release.json` with the APK version, increasing Android versionCode, file name and SHA-256.
4. Commit both files to `main`. The workflow verifies SHA-256, creates a draft release,
   uploads the APK and checksum file, then publishes the release.

The workflow distributes an already signed APK. It does not build the app or need a signing secret.
Existing published versions are not overwritten. Inspect the Actions run if publication fails.
Do not upload private source bundles, keystores, credentials or configuration backups here.

## Third-party components

See [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt) for the license notices bundled with the APK.
This project is independent of SONOFF, eWeLink and DomoDreams.
