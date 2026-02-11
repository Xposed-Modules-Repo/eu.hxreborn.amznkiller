# AmznKiller

Xposed module built on the modern LSPosed API that hides ads and sponsored content inside the Amazon Android app.

![Build](https://github.com/hxreborn/amznkiller/actions/workflows/build.yml/badge.svg)
![Kotlin](https://img.shields.io/badge/Kotlin-2.3.10-7F52FF?style=flat&logo=kotlin&logoColor=white)
![Android](https://img.shields.io/badge/API-28%2B-3DDC84?logo=android&logoColor=white)

## Features

- Remove sponsored cards, video carousels, and other promotional UI in the Amazon app
- Maintained built-in selector list with remote updates. Optionally use your own self-hosted selector list via custom URL.
- Selector sanitization blocks common CSS injection patterns
- Material 3 Expressive settings UI with Jetpack Compose
- Recommended alongside Private DNS and hosts-based blocking
- Free and open source (FOSS)

## Requirements

- Android 9 (API 28) or higher
- [LSPosed](https://github.com/JingMatrix/LSPosed) (JingMatrix fork recommended)
- Amazon Shopping app (`com.amazon.mShop.android.shopping`)

## Installation

1. Download the APK from [GitHub Releases](https://github.com/hxreborn/amznkiller/releases)
2. Enable the module in LSPosed and scope it to `com.amazon.mShop.android.shopping`
3. Open the AmznKiller companion app to verify the module is active and optionally fetch updated
   lists (built-in filters work out of the box)
4. Force-stop the Amazon app and relaunch it. A toast confirms the module is active.

## Build

```bash
git clone --recurse-submodules https://github.com/hxreborn/amznkiller.git
cd amznkiller
./gradlew buildLibxposed
./gradlew :app:assembleDebug
```

Requires JDK 21 and Android SDK. Configure `local.properties`:

```properties
sdk.dir=/path/to/android/sdk

# Optional signing
RELEASE_STORE_FILE=<path/to/keystore.jks>
RELEASE_STORE_PASSWORD=<store_password>
RELEASE_KEY_ALIAS=<key_alias>
RELEASE_KEY_PASSWORD=<key_password>
```

## Contributing

Pull requests welcome. [Open an issue](https://github.com/hxreborn/amznkiller/issues/new/choose) for bugs or feature requests.

## License

This project is licensed under the GNU General Public License v3.0 -- see the [LICENSE](https://github.com/hxreborn/amznkiller/blob/main/LICENSE) file for details.
