# FuckMeta

<p align="center">
  <strong>A lightweight, high-performance Xposed / LSPosed module to completely block, strip, and isolate Meta AI from WhatsApp on Android.</strong>
</p>

<p align="center">
  <a href="https://github.com/libxposed/api"><img src="https://img.shields.io/badge/Xposed%20API-v82%20%7C%20v102-blue.svg" alt="Xposed API" /></a>
  <a href="https://developer.android.com/about/versions/11"><img src="https://img.shields.io/badge/Android-11%2B%20(API%2030%2B)-green.svg" alt="Android Version" /></a>
  <a href="https://github.com/LSPosed/LSPosed"><img src="https://img.shields.io/badge/LSPosed-Supported-brightgreen.svg" alt="LSPosed" /></a>
  <a href="https://github.com/fzer0x/FuckMeta/releases"><img src="https://img.shields.io/badge/GitHub-Releases-blue.svg" alt="Releases" /></a>
</p>

---

## Overview

**FuckMeta** is an Android Xposed module designed to purge all Meta AI integrations, bot suggestions, floating ring buttons, and prompt shortcuts from **WhatsApp** (`com.whatsapp`).

Without modifying original app binaries or risking account integrity, **FuckMeta** operates seamlessly in memory via LSPosed to restore a private, clean, and distraction-free messaging interface.

---

## Key Features

- **Server-Side Feature Neutralization**: Dynamically suppresses Meta AI feature flags, onboarding flows, and gating checks.
- **UI & Layout Sanitization**:
  - Removes the purple Meta AI Floating Action Button (FAB).
  - Sanitizes the top search bar placeholder text from *"Meta AI fragen oder suchen"* to *"Chat suchen..."*.
  - Neutralizes AI accessibility prompts and suggestion chips.
- **Privacy Preservation**: Blocks background AI telemetry, bot queries, and prompt suggestions.
- **Zero Binary Patching**: Operates entirely in runtime memory via LSPosed. Original app signatures and updates remain intact.
- **Dynamic Compatibility**: Resilient against WhatsApp updates using intelligent runtime class resolution.
- **Integrated Update Checker**: In-app GitHub release checker to stay up-to-date.

---

## Requirements

- **Rooted Android Device** (Magisk, KernelSU, APatch, or Zygisk Next)
- **LSPosed Framework** installed and functional
- **Android 11** (API Level 30) or higher
- **WhatsApp** (`com.whatsapp`) installed

---

## Installation & Setup

1. **Download Release APK**:
   - Download the latest `FuckMeta.apk` from [GitHub Releases](https://github.com/fzer0x/FuckMeta/releases).
   - Install the APK on your device.

2. **Enable Module in LSPosed**:
   - Open **LSPosed Manager**.
   - Navigate to **Modules** -> **FuckMeta**.
   - Enable the module.
   - Under **Scope**, ensure **WhatsApp** (`com.whatsapp`) is selected.

3. **Restart WhatsApp**:
   - Force-stop WhatsApp (`Settings` -> `Apps` -> `WhatsApp` -> `Force Stop`) or execute via ADB:
     ```bash
     adb shell am force-stop com.whatsapp
     adb shell am start -n com.whatsapp/.Main
     ```
   - Launch WhatsApp: Meta AI is now completely removed.

---

## Frequently Asked Questions (FAQ)

### Does this require modifying the WhatsApp APK?
No. FuckMeta hooks runtime memory calls using LSPosed. The original WhatsApp APK remains untouched.

### Will WhatsApp updates break the module?
FuckMeta uses dynamic runtime resolution to handle internal obfuscation changes across WhatsApp updates.

### Does this affect standard chat or call features?
No. Only Meta AI, AI bot suggestions, and prompt elements are isolated. Standard messaging, voice/video calls, status, and media sharing function normally.

---

## Disclaimer

This software is provided for personal privacy enhancement and educational research purposes only. It is not affiliated with, sponsored by, or endorsed by Meta Platforms, Inc. or WhatsApp LLC.

---

## License

Copyright (c) All Rights Reserved. Proprietary software release. Redistribution, decompilation, or reverse engineering of binary releases is prohibited without prior authorization.
