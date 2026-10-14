![Aurelvi](logo.svg)

# Aurelvi Panel

Public signed APK releases for NSPanel Pro and compatible Android 8+ wall panels. Android source code and signing keys are not included in this repository.

[Download the latest APK](https://github.com/sonics007/aurelvi-apk/releases/latest) · [Home Assistant integration](https://github.com/sonics007/aurelvi-ha/releases/latest)

## Install or update

Download the APK from Releases and install over the existing application:

```bat
adb.exe -s PANEL_IP:5555 install -r Aurelvi-0.3.3.apk
```

Do not uninstall to update. APK 0.3.3 uses the same signing certificate as 0.3.0 and has versionCode 7.

For in-app updates use repository `sonics007/aurelvi-apk` and leave the optional asset name empty. Android installation confirmation is required.

## 0.3.3

After installation updates, Aurelvi automatically returns to the foreground even when it is not the default Home app. The Home Assistant integration remains at 0.3.2.

## 0.3.2

Dedicated clock alarm dialog, public-settings snapshots for HA, 32 original Aurelvi skins, cover controls, clock customization and optional Android TTS notifications. Use with Aurelvi HA 0.3.2 for the new Studio controls and room builder. In the panel settings select **Aurelvi** mode to connect to the Aurelvi integration.

Native speech engines, sensors and full end-to-end behavior still require verification on the user's device. SHA-256 checksums are attached to each release.
