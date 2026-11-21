# Xperia Watermark For Zeiss

[日本語](README.md) | **English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/version-1.0-brightgreen)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**An Android app that adds an Xperia × ZEISS logo and shooting info as a watermark to photos taken on an Xperia with a ZEISS lens.**

It reads the model name, focal length, aperture, shutter speed, ISO, and date/time from the photo's EXIF data. Then it adds a band with the logos and shooting info under the photo and saves it.
It only works with **photos taken on ZEISS-equipped Xperia phones** (photos from other phones don't appear in the list).

> Want watermarks for every Xperia, not just ZEISS models? → [Xperia All Watermark](https://github.com/Connectan/Xperia-All-Watermark)

---

## ⚠️ Read this first (from the author)

- The APK here is **v1.0 (final release)**. The package name is now `com.connectan.xperiawatermark.zeiss`, and it's a release build, not a debug build.
- Test Beta 3 (package name `com.example`) has a different package name and signature, so it can't be updated in place. If you have Test Beta 3 installed, **uninstall it first**, then install v1.0.
- I sold my Xperia, so **I no longer have a real device to test on**. Future updates are undecided (honestly, there probably won't be any).
- But it **works without a single bug** (I checked Test Beta 3 on a real device; v1.0 only changes the package name and signature, the app itself is the same). Go ahead and use it with confidence.

---

## Download

👉 **[Download the APK from Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)**

File name: `XperiaWatermarkForZeiss_v1.0.apk` (about 20 MB)
SHA-256: `bf27ae5e4213ba6d2950033f721773c0476f0d0b467b7f476002890671daff2a`

---

## Features

| Feature | Details |
|---|---|
| Finds Xperia photos automatically | Scans the photos on your device and uses the EXIF maker (Sony) and model name to list **only photos taken on ZEISS-equipped Xperia phones** |
| Adds the watermark | Adds a band under the photo with the Xperia logo, ZEISS logo, model name, and shooting info, and saves it as a new image (the original photo is untouched) |
| 2 background styles | Choose **Pure White** or **Cyan Gradient** |
| Date/time display | Shows the date and time taken in the bottom right. Turn it off to hide the date and make the camera info stand out |
| Batch processing | Multi-select or "Select all" to save many at once. You can also process only the unprocessed photos in one go |
| See what's done at a glance | Saved photos get a "白 済" (white done) or "青 済" (cyan done) mark. You can save them again too |
| Choose where to save | Choose **internal storage** or **SD card** (saves to internal storage if there's no SD card) |

### What goes into the watermark

| Item | Example |
|---|---|
| Logos | Xperia logo + ZEISS logo |
| Model name | Xperia 1 V |
| Focal length | 24mm |
| Aperture | F1.9 |
| Shutter speed | 1/125s |
| ISO | ISO 100 |
| Date/time (can be turned on/off) | 2024.05.01 12:34 |

\* These example values are for illustration. The actual values come straight from the photo's EXIF.

---

## Supported models

These are the models in the app's detection list (all have ZEISS lenses).

| Model | docomo | au | SoftBank |
|---|---|---|---|
| Xperia 1 II | SO-51A | SOG01 | — |
| Xperia 5 II | SO-52A | SOG02 | A002SO |
| Xperia 1 III | SO-51B | SOG03 | A101SO |
| Xperia 5 III | SO-53B | SOG05 | A103SO |
| Xperia 1 IV | SO-51C | SOG06 | A201SO |
| Xperia 5 IV | SO-54C | SOG09 | A204SO |
| Xperia 1 V | SO-51D | SOG10 | A301SO |
| Xperia 5 V | SO-53D | SOG12 | — |
| Xperia 1 VI | SO-51E | SOG13 | A401SO |
| Xperia 1 VII | SO-51F | SOG15 | A501SO |
| Xperia 1 VIII | SO-51G | SOG17 | A601SO |

- SIM-free and international models also work, as long as the EXIF model name in the photo can be identified as one of the models above.
- **It does not work with Xperia phones without ZEISS (such as the 10 series) or with photos from other makers.**
- Detection is based on **which phone took the photo**, not which phone the app is installed on. So as long as the photo was taken on a ZEISS-equipped Xperia, you can add watermarks on other Android phones too.

---

## How to use

1. Open the app and **allow** access to your photos
2. After "Scanning storage for Xperia photos...", the supported photos appear in a list
3. Tap the photos you want to watermark ("Select all" is also available)
4. Choose a **watermark background style**: Pure White / Cyan Gradient
5. Turn the **date/time display** on or off
6. Choose the **output location** for the watermarked images: internal storage / SD card
7. Tap "Save watermark to the ○ selected photos" to save the watermarked images

\* The app's screens are in Japanese. Some button names above are translated.

Saved photos get a "白 済" or "青 済" mark, so you can tell right away which ones you've processed.

---

## How to install

1. Download the APK from [Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)
2. Tap the downloaded APK
3. If you are asked about "unknown apps", turn on **Allow from this source** for your browser (or file manager)
4. Tap "Install"

> Because this is installed from outside Google Play, Play Protect may show a warning. If it does, tap "More details" → "Install anyway".

---

## Requirements

| Item | Details |
|---|---|
| Android | **7.0 or later** (API 24+) |
| Target | Android 16 (API 36) |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| Photos | JPEGs taken on a ZEISS-equipped Xperia (with EXIF) |

---

## Permissions

| Permission | What it's for |
|---|---|
| Photos and videos (`READ_MEDIA_IMAGES`) | To find photos on the device and add watermarks (Android 13+) |
| Read storage (`READ_EXTERNAL_STORAGE`) | Same as above (Android 12 and earlier) |
| Write storage (`WRITE_EXTERNAL_STORAGE`) | To save watermarked images (Android 9 and earlier) |
| Internet (`INTERNET`, etc.) | Declared by libraries bundled in the app |

The watermark is drawn on the device (with Android's Canvas).

---

## FAQ

**Q. My photos don't show up in the list**
A. Photos taken on anything other than a ZEISS-equipped Xperia, or photos whose EXIF (shooting info) has been removed, will not appear. Images saved from social media or exported from editing apps often have no EXIF.

**Q. Will my original photos be overwritten?**
A. No. The watermarked image is saved **as a separate file**.

**Q. I can't save to the SD card**
A. If there's no SD card, or it can't be detected, the option changes to "Internal storage (SD not detected)" and images are saved to internal storage.

**Q. I want to process the same photo again**
A. Just select a photo marked "済" (done) again and you can **save it again**.

**Q. I can't update over Test Beta 3**
A. v1.0 has a new package name (`com.connectan.xperiawatermark.zeiss`) and signature, so Android treats it as a different app. Uninstall Test Beta 3 first, then install v1.0.

---

## Author

**Connectan (こねくたん)**, also known as 晓玲 清風
- Website: https://connectan.github.io

Lives deep in the rabbit hole of Chinese phones without Japanese certification.

---

## Notes

- "Xperia" is a trademark of Sony Group Corporation, and "ZEISS" is a trademark of Carl Zeiss AG.
- This is an **unofficial app made by an individual**. It is not affiliated with Sony or ZEISS.
- Use at your own risk.
