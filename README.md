# TBTechs

Indie software studio building at the systems level.

Local AI inference. OS-level enforcement. Offline-first mobile apps.  
Real implementations. No cloud wrappers. No soft timers.

---

## Projects

### [Aria Prime](https://github.com/TITANICBHAI/aria-prime) — On-Device AI Agent for Android

Runs quantized LLMs entirely on-device via a custom JNI bridge to **llama.cpp** with OpenCL GPU acceleration. A 1,063-line `AgentLoop` drives a `read → decide → act → observe` cycle — backed by a **SAM2 visual segmentation engine**, Android **AccessibilityService** screen context, a **gesture execution engine**, and a **reinforcement learning policy network**. No API key. No server.

`Kotlin` `Compose` `llama.cpp` `JNI/NDK` `OpenCL` `SAM2` `AccessibilityService` `RL policy`

---

### [FocusFlow](https://github.com/TITANICBHAI/FocusFlow) — Hard-Enforcement Android App Blocker

Five independent enforcement layers, all active at once:

1. **AccessibilityService** — intercepts every window-change event instantly
2. **Null-routing VPN** — cuts network access on-device, no external server
3. **Device Administrator** — blocks uninstall during active sessions
4. **System Guard** — intercepts navigation to Accessibility Settings and Clear Data
5. **SHA-256 session PIN** — native hash check gates all stop-session operations

Content-level blocking (YouTube Shorts, Instagram Reels), boot recovery, weekly Temptation Report, 30+ OEM brands. Completely free.

`Kotlin` `Android` `AccessibilityService` `VPN` `Device Admin` `SHA-256`

Live: [focusflowapp.pages.dev](https://focusflowapp.pages.dev)

---

### [FocusFlow JVM](https://github.com/TITANICBHAI/FocusFlow-jvm) — Windows Focus Enforcement

Monitors the foreground window every **500ms** via `Win32 GetForegroundWindow()` through JNA. On detection of a blocked app: `ProcessHandle.destroyForcibly()` kills it, a `taskkill /F` fallback fires, an always-on-top Compose overlay appears, the attempt is logged to **SQLite**, and — if network blocking is enabled — `netsh advfirewall` + `New-NetFirewallRule` add a live firewall rule. Same SHA-256 session PIN as the Android version. Ships as a standalone **EXE or MSI** via jpackage.

`Kotlin 1.9` `Compose Multiplatform Desktop 1.6` `JNA 5.14` `Win32` `PowerShell` `SQLite` `jpackage`

Live: [focusflowpc.pages.dev/](https://focusflowpc.pages.dev/)

---

### [PeopleMemory](https://github.com/TITANICBHAI/PeopleMemory) — 100% Offline Private Relationship Manager

All storage is on-device via **AsyncStorage**. The vault is **SHA-256 PIN** protected. Features: trust-level tracking (0-10, colour-coded), rich notes (likes, dislikes, quick facts), local reminders for birthdays and meetings, voice interaction notes with timestamps, colour-coded groups, auto-calculated relationship health score, meeting prep cards, and an activity journal. Zero cloud. Zero tracking. Zero account. No network permissions in the manifest.

`React Native` `Expo SDK 54` `TypeScript` `Expo Router` `AsyncStorage` `SHA-256`

Live: [peoplememory.pages.dev](https://peoplememory.pages.dev)

---

## Stack

| Domain | Technologies |
|---|---|
| Android | Kotlin, Jetpack Compose, AccessibilityService, JNI, NDK, C++ |
| Windows | Kotlin Multiplatform, Compose Desktop, JNA, Win32, PowerShell |
| Mobile | React Native, Expo SDK 54, TypeScript, Expo Router |
| AI / ML | llama.cpp, SAM2, OpenCL GPU, GGUF quantization, RL policy networks |
| Systems | Process kill, VPN tunneling, firewall rules, native crash handling |

---

[tbtechs.dev](https://titanicbhai.github.io)
