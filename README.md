![Aurelvi](logo.svg)

# Aurelvi Panel

Public signed APK releases for NSPanel Pro and compatible Android 8+ wall panels. Android source code and signing keys are not included in this repository.

[Download the latest APK](https://github.com/sonics007/aurelvi-apk/releases/latest) · [Home Assistant integration](https://github.com/sonics007/aurelvi-ha/releases/latest)

## Install or update

Download the APK from Releases and install over the existing application:

```bat
adb.exe -s PANEL_IP:5555 install -r Aurelvi-0.3.7.apk
```

Do not uninstall to update. APK 0.3.7 uses the same signing certificate as previous releases and has versionCode 9.

For in-app updates use repository `sonics007/aurelvi-apk` and leave the optional asset name empty. Android installation confirmation is required.

## 0.3.7

80 original skins with six new material families: Art Deco, Hi-Fi, Ceramic, Japandi, Glass and Neon. The Hi-Fi meter reflects confirmed fan output, not audio levels. Settings includes native RSA-SHA256 licence application. No private issuer key is in the APK. All skins are currently open preview and checkout is disabled.

Use HA 0.3.7 for complete selectable room inventories, paired control plates and room rebuild/removal. Visit [Aurelvi](https://sonics007.github.io/aurelvi-ha/) for the updated dark/light website and design gallery.

## 0.3.4

Choose an alarm tone, audition it, set volume and enable an optional gentle fade-in. Three original Aurelvi tones plus the classic beep are included. Use HA integration 0.3.4 for the redesigned Studio workspace, prominent room builder and wallpaper gallery/uploads.

## 0.3.3

After installation updates, Aurelvi automatically returns to the foreground even when it is not the default Home app. The Home Assistant integration remains at 0.3.2.

## 0.3.2

Dedicated clock alarm dialog, public-settings snapshots for HA, 32 original Aurelvi skins, cover controls, clock customization and optional Android TTS notifications. Use with Aurelvi HA 0.3.2 for the new Studio controls and room builder. In the panel settings select **Aurelvi** mode to connect to the Aurelvi integration.

Native speech engines, sensors and full end-to-end behavior still require verification on the user's device. SHA-256 checksums are attached to each release.
