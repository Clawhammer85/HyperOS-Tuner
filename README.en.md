<div align="center">

# HYPER⚡OS Privacy Tuner

**More privacy, security and speed for your Android phone – step by step, no root.**

[![Build APK](https://github.com/Clawhammer85/HyperOS-Tuner/actions/workflows/apk.yml/badge.svg)](https://github.com/Clawhammer85/HyperOS-Tuner/actions/workflows/apk.yml)
![Version](https://img.shields.io/badge/Version-1.3-2DD4BF)
![Android](https://img.shields.io/badge/Android-10%2B-3DDC84?logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-Jetpack%20Compose-7F52FF?logo=kotlin&logoColor=white)
![No internet](https://img.shields.io/badge/Internet%20permission-none-blue)

[Deutsch](README.md) · English

</div>

---

**HyperOS Privacy Tuner** shows you which settings make your phone more private, secure and faster – and takes you straight to the right place with a single tap. Many items are detected automatically and checked off as soon as you come back. Built for **Xiaomi, Redmi and POCO with HyperOS**, also adapted for **Samsung (One UI)** and other Android devices.

> [!NOTE]
> The app changes nothing without you, and every setting can be reverted. It has **no internet permission** and therefore cannot send any data.

## Contents

- [Features](#features)
- [Supported devices](#supported-devices)
- [Installation](#installation)
- [Advanced: automation and unlock](#advanced-automation-and-unlock)
- [Permissions](#permissions)
- [FAQ](#faq)
- [Building](#building)
- [Project structure](#project-structure)
- [Sources](#sources)
- [License and notes](#license-and-notes)

## Features

### For beginners

- **Introduction on first launch** – five short pages, skippable and available again at any time.
- **“Essentials”** – starts with about ten items instead of the full list.
- **“Next step” assistant** – always shows exactly one open item with an explanation and a big “Set it now” button. Not sure about something? Postpone it with “Later”.

### Checklist

- **40+ researched recommendations** in five categories: privacy, security, network, ads, performance.
- **Direct shortcuts** into the matching menu, with the path always shown.
- **Automatic detection** of screen lock, security patch, screen timeout, USB debugging, Wi‑Fi/Bluetooth scanning, Private DNS, lock screen content, clipboard notice, password visibility, animations, brightness and free storage.
- Apps that aren't installed are skipped; the memory extension advice adapts to your RAM.

### Automation lite – no PC, no password

With a single permission (“Modify system settings”) the app sets:
- screen lock after 1 minute
- hidden passwords while typing
- adaptive brightness (optional)

### Ad filter via Private DNS

Pick a provider, tap “Copy and open settings”, paste – done. All providers are free and need no account:

| Rank | Provider | Hostname | Blocks |
|:---:|---|---|---|
| 1 | **AdGuard DNS** (recommended) | `dns.adguard-dns.com` | ads, trackers, malware |
| 2 | **DNS4EU** – no ads | `noads.joindns4.eu` | ads, malware · EU initiative, GDPR |
| 3 | **HaGeZi DNS** | `root.hagezi.org` | ads, trackers, telemetry · servers in Germany |
| 4 | **Control D** – no ads | `p2.freedns.controld.com` | ads, trackers, malware |
| 5 | **Quad9** | `dns.quad9.net` | malware only · non-profit |

> [!WARNING]
> Mullvad shuts down its public DNS service on **November 2, 2026**. The app detects a configured Mullvad server and asks you to switch.

### Look and feel

- **German and English**, follows the system language or can be switched at the top right
- **Glass design in dark mode** with six color themes: Lagoon, Aurora, Amethyst, Ember, Ocean, Graphite
- Expandable cards, category filters, subtle haptic feedback

## Supported devices

The app detects the manufacturer and adapts menu paths, recommendations and the logo. Tap the logo at the top left to switch manually.

| Manufacturer | Logo | Highlights |
|---|---|---|
| Xiaomi, Redmi, POCO | HYPER⚡OS (older: MI⚡UI) | msa, ad services, recommendations in Xiaomi apps, App Vault, autostart, memory extension |
| Samsung | ONE⚡UI | Auto Blocker, Customization Service, ad blocking (One UI 8.5), Push Service, Galaxy Store, RAM Plus, Secure Folder |
| OnePlus, Oppo, realme, Nothing, Motorola | OXYGEN⚡OS, COLOR⚡OS … | standard Android paths |
| everything else | ANDROID⚡16 | standard Android paths |

Requires **Android 10 or later**. Unlocking via Shizuku requires Android 11 or later.

## Installation

1. Download the latest APK from **[Releases](https://github.com/Clawhammer85/HyperOS-Tuner/releases)** – or, with a GitHub account, from the latest successful run under **[Actions](https://github.com/Clawhammer85/HyperOS-Tuner/actions)** › *Artifacts*.
2. Tap the APK on your phone and allow “Install unknown apps” once.
3. Open the app – the introduction guides you through the rest.

> [!TIP]
> Revoke “Install unknown apps” afterwards – it's even an item on the checklist. On Samsung, “Auto Blocker” must be off briefly for the installation.

Updates install directly over the existing version; checkmarks and settings are kept.

## Advanced: automation and unlock

Everything in this section is **optional**. The checklist works completely without it.

### Automatic run

Sets all system values at once – animations, Wi‑Fi/Bluetooth scanning, lock screen content, clipboard notice, screen timeout, hidden passwords and, if you like, Private DNS. You confirm with fingerprint, face or PIN first. Afterwards the app shows a result per item; “Undo everything” reverts the changes.

The app needs extended rights once for this. **The fingerprint confirmation does not grant these rights** – it only prevents someone else from starting the run on your phone.

### Unlock without a PC – with Shizuku

The **“Advanced”** tab guides you through four steps:

1. Install [Shizuku](https://github.com/thedjchi/Shizuku/releases) (recommended: fork by thedjchi)
2. Start Shizuku via “Wireless debugging”
3. Allow the app to access it
4. “Unlock now”

Afterwards you can uninstall Shizuku – **the unlock stays**. While Shizuku is running, the app removes detected ad and tracking packages at the push of a button and restores them if needed.

### Unlock via PC

Using the [Android SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools):

```bash
adb devices
adb shell pm grant de.hyperos.tuner android.permission.WRITE_SECURE_SETTINGS
adb shell appops set de.hyperos.tuner WRITE_SETTINGS allow
```

> [!IMPORTANT]
> **Xiaomi:** Also turn on “USB debugging (Security settings)” in developer options (requires a Xiaomi account), otherwise HyperOS rejects the commands.
> **Samsung:** Temporarily turn off “Auto Blocker” – it blocks commands via USB.

The app shows matching commands for removing and restoring ad services in the “Advanced” tab, ready to copy. Packages are only removed for your own user (`pm uninstall -k --user 0`); a factory reset or `cmd package install-existing` brings everything back.

## Permissions

| Permission | Purpose | When active |
|---|---|---|
| `QUERY_ALL_PACKAGES` | Detect which preinstalled apps are present | from installation |
| `WRITE_SETTINGS` | Automation lite: screen timeout, password visibility, brightness | only after you agree |
| `WRITE_SECURE_SETTINGS` | Automatic run, “Set automatically” | only after unlocking via Shizuku or PC |
| `USE_BIOMETRIC` | Confirmation before the run and before removing apps | when needed |
| Shizuku provider | Connection to Shizuku | only while Shizuku runs and you agree |
| ~~`INTERNET`~~ | – | **not requested** |

Backed-up original values and your checkmarks stay on the device only. The app is excluded from Android backups.

## FAQ

<details>
<summary><b>Does the app need root?</b></summary>

No. The checklist works without special rights. For the automatic run, a one-time unlock via Shizuku or PC is enough.
</details>

<details>
<summary><b>Play Protect warns during installation – is the app dangerous?</b></summary>

Play Protect is generally cautious about apps from outside the Play Store that it doesn't know yet. The source code is open here and the app has no internet permission. Feel free to let Play Protect scan it.
</details>

<details>
<summary><b>After setting up Private DNS, I have no internet on one Wi‑Fi network.</b></summary>

Some company or hotel networks block the required port 853. Switch Private DNS back to “Automatic” there. Note that Private DNS also bypasses your own DNS filter at home (e.g. Pi-hole).
</details>

<details>
<summary><b>An app no longer works properly after enabling the ad filter.</b></summary>

Very thorough filters occasionally block something legitimate. Quickest test: switch to AdGuard DNS or turn Private DNS off briefly.
</details>

<details>
<summary><b>My banking app won't start anymore.</b></summary>

Some banking apps refuse to work while Shizuku is installed. After unlocking, you can uninstall Shizuku – the app keeps its rights.
</details>

<details>
<summary><b>After a major update, items are open again.</b></summary>

Major HyperOS or One UI updates reset individual values. Also, the Xiaomi Security app scan sometimes turns off developer options, which resets the animation values. The checklist shows affected items as open again.
</details>

<details>
<summary><b>A menu path is different on my device.</b></summary>

Menu names vary slightly between versions. Please open an [issue](https://github.com/Clawhammer85/HyperOS-Tuner/issues) with your device, Android or HyperOS/One UI version and the correct path.
</details>

## Building

**With GitHub Actions:** every push runs the [`apk.yml`](.github/workflows/apk.yml) workflow; the APK is then available under *Actions* › *Artifacts*. Alternatively, upload the project as `HyperOSTuner.zip` – the workflow unpacks it automatically.

**With Android Studio:** open the project and choose *Build › Build APK(s)*.

**From the command line:**

```bash
gradle assembleDebug   # APK: app/build/outputs/apk/debug/app-debug.apk
```

All builds are signed with `app/debug.keystore` so updates can be installed over older versions. For public distribution, a dedicated release key is recommended.

| | |
|---|---|
| Language | Kotlin, Jetpack Compose, Material 3 |
| minSdk / targetSdk | 29 (Android 10) / 35 |
| Dependencies | AndroidX, Shizuku API 13.1.5 |
| App ID | `de.hyperos.tuner` |

## Project structure

```
app/src/main/java/de/hyperos/tuner/
├── MainActivity.kt    UI: introduction, checklist, advanced
├── ManualSteps.kt     All recommendations per manufacturer (German/English)
├── Platform.kt        Manufacturer detection, logo, debloat lists
├── Model.kt           System values, DNS providers, categories
├── Detectors.kt       Automatic detection of completed items
├── SettingsRepo.kt    Reading, backing up, setting and restoring system values
├── ShizukuBridge.kt   Optional unlock without a PC
├── Auth.kt            Confirmation via fingerprint, face or PIN
├── L10n.kt            UI texts
├── Glass.kt           Glass design, haptics, controls
├── Palettes.kt        Color themes
└── Launcher.kt        Shortcuts into settings and apps
```

**New language:** add a field to class `T` in `L10n.kt` and add the texts in `L10n.kt` and `ManualSteps.kt`.

## Sources

The recommendations are based on current guides and projects (as of October 2026): smartzone.de and Notebookcheck (ads in HyperOS), techbone.de (HyperOS and One UI paths), netzwelt.de (One UI 8.5, Auto Blocker), Samsung Community, SamMobile and Android Authority, Android Central, the debloat projects [ovsky/hyperos-debloater](https://github.com/ovsky/hyperos-debloater) and [BloodBlinker/hyperos-debloat](https://github.com/BloodBlinker/hyperos-debloat), the [Shizuku wiki](https://github.com/thedjchi/Shizuku/wiki) as well as the DNS providers' pages ([AdGuard](https://adguard-dns.io), [DNS4EU](https://www.joindns4.eu), [HaGeZi](https://github.com/hagezi/dns-servers), [Control D](https://controld.com/free-dns), [Quad9](https://quad9.net)) and [Mullvad](https://mullvad.net/en/blog/2026/9/3/shutting-down-our-public-encrypted-dns-servers-and-sponsoring-quad9-instead) on the DNS shutdown.

## License and notes

**License:** not yet chosen.

This project is not affiliated with Xiaomi, Samsung or Google. HyperOS, MIUI, One UI, Galaxy and Android are trademarks of their respective owners. Use at your own risk – removed packages can be restored at any time, and a factory reset returns the device to its original state.
