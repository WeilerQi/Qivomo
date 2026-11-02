<div align="center">

![Qivomo](assets/Qivomo_icon-round.png)

# Qivomo

**Bring the feel of a keyboard and mouse to mobile games**

A local input-mapping tool for Android　·　No memory reading　·　No game files touched　·　No network access

![Version](https://img.shields.io/badge/version-v1.4.6-4F7CAC?style=flat-square)

![Platform](https://img.shields.io/badge/Android-7.0%2B-3DDC84?style=flat-square\&logo=android\&logoColor=white)

![Size](https://img.shields.io/badge/size-1.8%20MB-9C6ADE?style=flat-square)

![License](https://img.shields.io/badge/license-proprietary%20%C2%B7%20free%20to%20use-555?style=flat-square)

|                                                                                    |                             |                               |                                                               |
| ---------------------------------------------------------------------------------- | --------------------------- | ----------------------------- | ------------------------------------------------------------- |
| [**⬇️ Download the latest version**](https://github.com/WeilerQi/Qivomo/releases)　 | 　[Changelog](CHANGELOG.md)　 | 　[Disclaimer](DISCLAIMER.md)　 | 　[Report an issue](https://github.com/WeilerQi/Qivomo/issues) |

|              |                                             |
| ------------ | ------------------------------------------- |
| **English**　 | 　[简体中文](https://gitee.com/weiler_qi/qivomo) |

</div>

---

## 📥 Download

| Version    | Size   | Requires     | Download                                                                                         |
| ---------- | ------ | ------------ | ------------------------------------------------------------------------------------------------ |
| **v1.4.6** | 1.8 MB | Android 7.0+ | [**Download APK**](https://github.com/WeilerQi/Qivomo/releases/download/v1.4.6/Qivomo-1.4.6.apk) |

> Only the signed release build is published. If a copy of Qivomo has been repackaged, re-signed or otherwise modified by a third party, it did not come from this project — do not install it.

> ⚠️ **Upgrading from v1.4.5 to v1.4.6 requires a clean install.** v1.4.6 is signed with a new release key, and Android refuses to overwrite an app signed by a different key. Before uninstalling, export your configuration from the old build under **Settings → General → Export**; re-import it after installing v1.4.6.  
> From v1.4.6 onward every release shares the same key, so later upgrades install over the top as usual.

> On your phone, just tap the downloaded file to install. If Android warns about an unknown source, allow your browser or file manager to install unknown apps.  
> All previous builds are listed on the [**Releases page**](https://github.com/WeilerQi/Qivomo/releases).

> 🌏 In mainland China, the [Gitee mirror](https://gitee.com/weiler_qi/qivomo/releases) is usually much faster to download from.

---

## ✨ What is this

Qivomo is a **local input-mapping tool** that runs on Android.

It works like this: with Shizuku it deploys a small native daemon under the `shell` user, which reads the physical keyboard, mouse and gamepad input devices directly, then translates key presses and mouse movement into touch events on the screen. That is how you can walk with WASD and aim with a mouse on a phone.

It is only a translation layer — "press a key, produce a finger tap":

- ❌ It does not modify, replace or inject into any game file or process memory
- ❌ It does not read or tamper with any traffic between the game and its servers
- ❌ It does not provide aim assist, wallhacks, speed hacks, macro farming or any other cheat-like feature
- ✅ Its scope is the same as the system's built-in accessibility features and external input device support

> **Intended for**: single-player games, offline games, emulators, accessibility assistance, development and testing, teaching demos.  
> **Not recommended** for PvP, ranked or competitive games — see the [Disclaimer](DISCLAIMER.md).

---

## 🎯 Features

### Mapping engine

- **Native daemon, no root**: once Shizuku grants access, `qivomod` is deployed and reads `/dev/input` as `shell`, bypassing the restrictions Android places on third-party apps reading peripherals
- **9 control types**: key, combo, joystick, look/camera swipe, rapid fire, macro, multi-touch, scroll wheel, directional movement
- **Combos**: every member key must be held before the combo fires (e.g. `Ctrl + Shift + P`); releasing any one of them releases it immediately
- **Per-app profiles**: bind a profile to a package name and it switches automatically when that app comes to the foreground. The foreground app is detected by polling `dumpsys window` through Shizuku, so the overhead is negligible
- **Reference resolution**: coordinates are stored as screen ratios, so one profile works across resolutions. The current resolution can be detected automatically or set by hand

### In-place editing on the floating ball

- Editing **no longer covers the screen** — the game stays visible the whole time
- Only translucent circles remain; drag them into place, then tap an empty spot and press a key to bind it
- A side panel lists controls, changes their type and saves the profile. Its header stays fixed and the body scrolls, so nothing gets pushed off screen in landscape

### Peripherals and feel

| Category         | What you can tune                                                                                                                                                                                                                                                                             |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🖱️ Mouse        | Sensitivity (global plus per-axis X/Y, 0.2x–3.0x), polling rate (auto / 125–1000 Hz / unlimited), smoothing (4 levels), acceleration curve (off / linear / non-linear)                                                                                                                        |
| ⌨️ Keyboard      | Repeat delay (100–1500 ms), repeat rate (5–60 per second), long-press threshold (150–2000 ms)                                                                                                                                                                                                 |
| 🎮 Gamepad       | Brand detection (Xbox / Nintendo / Sony / Flydigi / BETOP / 8BitDo and more), stick dead zone, outer-ring sensitivity, response curve (linear / ease-in / ease-out / S-curve), trigger threshold                                                                                              |
| 📡 Device status | Scans input devices automatically and **lists only real external hardware** (on-board nodes such as the fingerprint reader and power key are filtered out by a name blacklist plus `InputDevice.isExternal()`), showing name, connection type (wired / Bluetooth / 2.4 GHz) and battery level |

Every parameter **takes effect immediately while mapping is running** — no restart needed.

### Interface and theme

- Material 3 · Compose, with a circular reveal transition (420 ms expanding, 300 ms collapsing)
- A bottom capsule navigation bar with a single sliding thumb that follows your finger
- Primary, secondary, text and outline colours are independent; colour wheel, brightness bar, HEX and RGB all stay in sync
- The floating ball's shape, size, opacity and position lock are all adjustable; when hidden it collapses into three small dots at the top edge
- **About page**: icon, version and a one-line description, plus **Check for updates** (Gitee / GitHub), **About the developer** and **Disclaimer**

### Sharing configurations

- **JSON import/export**: the full structure, including app bindings, is preserved
- **Share code**: export as a single line of text (`QVM.xxxxx`) and paste it to import; the old `KM1.` prefix is still accepted
- Everything is stored **on your device** — nothing is uploaded anywhere

### First launch and permissions

- On first launch a **disclaimer** appears (the same text as *About → Disclaimer*). **Agree** only lights up after you scroll to the bottom; declining exits the app
- Only after that are you asked about the "display over other apps" permission. Answering "no" is fine — you can grant it later on the activation page. You are asked once, not on every launch
- **No accessibility service is requested**: injection stays on a single channel. Accessibility cannot read relative mouse movement, and its gesture pointer competes with the injected pointer for the same touch slot, interrupting an in-progress camera drag

The button at the bottom of the activation page **walks you through in order**, and its label follows the first unfinished item:

| Situation                  | Button                               |
| -------------------------- | ------------------------------------ |
| Shizuku not installed      | Get Shizuku                          |
| Service not running        | Start the service                    |
| Qivomo not authorised      | Grant access                         |
| Overlay permission missing | Open settings                        |
| All four ready             | All permissions granted (greyed out) |

### Debugging

- Pointer crosshair, key event log and mouse polling-rate sampling — each overlay is only attached while enabled

---

## 📸 Screenshots

> Naming convention: `assets/screenshots/01-home.png`, `02-edit.png`, `03-settings.png`. 1080×2400 portrait, ideally under 300 KB each.

---

## 🚀 Quick start

### 1. Install

Download the APK above and install it. The first install needs "install unknown apps" to be allowed.

> **Oldest installable version: v1.4.5.** If you ever need to roll back, v1.4.5 is as far as you can go; earlier builds are no longer offered. Rolling back requires uninstalling first (Android will not install a lower versionCode over a higher one), and uninstalling wipes your on-device configuration and the "disclaimer accepted" state — export a backup from Settings beforehand.

### 2. First launch

1. Read the **disclaimer** — **Agree** only lights up at the bottom, and it is worth actually reading
2. You are then asked whether to go grant the "display over other apps" permission; tapping **Yes** takes you straight there
3. Skipping it or answering **No** is fine — you can grant it later on the **Activation & permissions** page

### 3. Set up Shizuku

Qivomo gets shell access through Shizuku. **Root is not required.**

1. Install [Shizuku](https://shizuku.rikka.app/) (or search for it on your app store)
2. Open Shizuku and start the service via **wireless debugging** or **ADB**, following its own guide
3. Back in Qivomo, open **Activation & permissions** and follow the bottom button: grant Shizuku access → grant overlay permission

### 4. Create a profile

1. Tap **New** on the home screen → pick the app to bind (or choose **Generic**)
2. Pick a reference resolution — the default **Auto (this device)** is fine
3. Tap **Edit mapping on floating ball** → tap an empty spot on screen → press a key → a circle appears; drag it where you want it
4. Tap **Done** to save → tap **Start mapping** → switch back to the game

> For step-by-step details per release, see the [Changelog](CHANGELOG.md).

---

## 📋 Requirements

| Item                 | Requirement                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------- |
| OS                   | Android 7.0 (API 24) or newer                                                                                  |
| ABI                  | arm64-v8a / armeabi-v7a                                                                                        |
| Required permissions | Shizuku authorisation, overlay, notifications                                                                  |
| Injection channel    | Shizuku only (no accessibility fallback; if the injector cannot start, it reports an error and stays disabled) |
| Network              | **Not required** — the app makes no network requests                                                           |
| Root                 | **Not required**                                                                                               |


**Known limitations**

- Gamepad vibration strength is currently only stored as a setting; force feedback is not implemented yet (no error, just no rumble)
- The detected gamepad brand decides the trigger range cap (Xbox 1023 / Nintendo and Sony 255); some third-party pads report slightly different axis ranges
- Heavily customised ROMs may restrict overlay window levels; you may need to allow "display pop-up windows in background" and "autostart"

---

## ❓ FAQ

<details>
<summary><b>Do I need root?</b></summary>

No. Qivomo uses Shizuku — a bridge service started via wireless debugging or ADB that runs with shell privileges. That is enough to deploy the daemon, without touching system partitions or unlocking the bootloader.
</details>

<details>
<summary><b>Can I get banned for using this?</b></summary>

Please read section 2 of the [Disclaimer](DISCLAIMER.md) first. Qivomo does not modify the game, inject into its process or forge data, but it does change how you input; in the terms of service of most PvP games, keyboard-and-mouse mapping counts as unfair competition.

**Account risk is entirely yours. The developer will not appeal on your behalf, will not help you get unbanned, and will not provide any way to avoid detection.** If you play competitive games, please use officially supported peripherals or the official emulator instead.
</details>

<details>
<summary><b>Will updating lose my configuration?</b></summary>

No. Your configuration lives in the app's private directory and survives a normal in-place upgrade. But **if the signing key differs between versions, Android refuses to install over the old one** — you have to uninstall first, which loses the configuration. Export a JSON file or a share code before upgrading.

Also note that **v1.4.5 is the lowest version you can roll back to**: earlier builds are no longer published, and Android will not install a lower versionCode, so a rollback always means uninstall, then install v1.4.5.
</details>

<details>
<summary><b>Does it work on iOS, HarmonyOS or emulators?</b></summary>

Not on iOS — there is no comparable input-device permission model. Emulators on Android can usually take keyboard and mouse input directly, so Qivomo is normally unnecessary there. HarmonyOS NEXT has not been tested and is not supported.
</details>

<details>
<summary><b>Nothing happens when I tap "Start mapping" / no circles appear</b></summary>

Check in this order: ① is the Shizuku service running (the system may kill it once the app goes to the background); ② is the overlay permission granted; ③ are all four items on **Activation & permissions** green, and has the bottom button turned into "All permissions granted"; ④ is another mapping app holding the input devices at the same time. If you see "injector failed to start", Shizuku has usually dropped — restart the service in Shizuku, then tap **Start mapping** again in Qivomo.
</details>

<details>
<summary><b>Does it upload my data?</b></summary>

No. There is no business logic that talks to the network: profiles, settings and logs all stay on your device. A share code is a piece of text you copy out yourself; it never passes through a server.
</details>

---

## 🗓️ Recent changes

**v1.4.6** — 2026-11-03
About page entries reordered (About the developer → Support the developer → Disclaimer → Check for updates); new support dialog (Bilibili, Alipay, WeChat — falling back to the browser when the app is missing); Check for updates now links straight to Gitee. The release build now enables code shrinking and obfuscation, cutting the APK from 7.2 MB to 1.8 MB, and is signed with a proper release key.

**v1.4.5** — 2026-11-02
Disclaimer footer wording: "Please read the terms" before you reach the bottom, "Agreeing means you have read them and accept the risk" once you do.

**v1.4.4** — 2026-11-02
First-launch order is now disclaimer first, overlay permission second; the device list filters on-board nodes such as the fingerprint reader and power key.

**v1.4.2** — 2026-11-02
Accessibility service removed (it cannot read relative mouse movement, and its pointer interrupted camera drags); foreground app detection now polls `dumpsys window` through Shizuku; injection failures report an error instead of silently degrading.

**v1.4.0** — 2026-11-01
New **About** page in Settings (check for updates / about the developer / disclaimer); first launch now requires accepting a disclaimer, which only unlocks after scrolling to the end.

Full history in [**CHANGELOG.md**](CHANGELOG.md).

---

## 🐛 Feedback

Please search existing issues before opening a new one. To make a report actionable, include:

| Required | Details |
| --- | --- |
| Device and OS | e.g. Pixel 8 / Android 15 |
| Qivomo version | Shown under Settings → About, e.g. `v1.4.6` |
| Shizuku version and how it was started | Wireless debugging / ADB / root |
| Steps to reproduce | Which screen, what you tapped, what you expected, what happened |
| Logs | Settings → General → Debugging → show key event log, screenshot is enough |

[**→ Open an issue**](https://github.com/WeilerQi/Qivomo/issues/new)

---

## 📄 About this repository

- This repository **only distributes builds, keeps the changelog and collects feedback**. It does not contain source code.
- **Check for updates** inside the app lists both the **Gitee** and **GitHub** repositories; releases and issue tracking live in both. This repository carries the English documentation, the [Gitee repository](https://gitee.com/weiler_qi/qivomo) carries the Chinese originals.
- Qivomo is **closed source**. Redistribution, modification or commercial licensing is not offered.
- The repository contains no game client, crack, patch or copyrighted game asset.
- This project is not affiliated with, endorsed by or licensed by any game developer, publisher, platform or peripheral brand.

## ⚖️ Copyright and licence

Copyright © 2026 WeilerHHC. All rights reserved.

Permitted: installing and using the app on your own devices; sharing an unmodified link to the [releases page](https://github.com/WeilerQi/Qivomo/releases).

Not permitted: decompiling, disassembling, repackaging, stripping or altering the signature or branding before redistribution, commercial use, renting or selling, or publishing derivative versions under this project's name.

See [LICENSE](LICENSE) and the [Disclaimer](DISCLAIMER.md) for the full terms.

---

<div align="center">

**By using Qivomo you confirm that you have read and accepted the [Disclaimer](DISCLAIMER.md) in full.**

</div>
