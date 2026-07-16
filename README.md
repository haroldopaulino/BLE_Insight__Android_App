# BLE Insight Android + AOSP Watch Scanner

**Multi-module Android Bluetooth Low Energy scanner built with Kotlin for phones and AOSP watches, featuring real-time BLE discovery, device details, advertisement analysis, RSSI sorting, battery-conscious wearable scanning, and a clean Material 3 user experience.**

BLE Insight is a professional-grade Bluetooth Low Energy scanner by Harold Paulino. The project includes a full Android phone experience and a compact AOSP watch experience, making it useful for mobile, embedded, firmware, IoT, wearable, and connected-device engineering workflows.

The app helps engineers discover nearby BLE devices, inspect advertisement data, evaluate signal strength, and validate whether embedded peripherals are advertising correctly across phone and wearable environments.

<img width="1536" height="1024" alt="ble_insight_android" src="https://github.com/user-attachments/assets/b9b79cab-3ff6-4e54-88c8-f70debf8aa7c" />

---

## Why This Project Matters

Bluetooth Low Energy is widely used in wearables, smart locks, medical devices, sensors, fitness devices, asset trackers, AOSP watches, industrial equipment, and embedded IoT hardware. BLE Insight is valuable because it turns Android and AOSP wearable devices into practical BLE inspection tools.

This repository demonstrates:

- Kotlin Android development
- Multi-module Android project organization
- Phone and AOSP watch app targets
- Bluetooth Low Energy scanning
- Real-time nearby-device discovery
- RSSI sorting and signal visibility
- Device detail inspection
- Advertisement flag inspection
- Service UUID inspection
- Manufacturer data inspection
- Service data inspection
- Runtime Bluetooth/location permission handling
- Battery-conscious wearable scanning
- Material 3 UI design
- Clean mobile tooling for embedded and firmware validation

---

## Project Overview

BLE Insight is organized as a multi-module Android project:

| Module | Purpose |
|---|---|
| `phone` | Full Android phone experience with scanning, device details, advertisement flags, service UUIDs, manufacturer data, and service data |
| `wearable` | Compact AOSP watch experience with battery-conscious BLE scanning, RSSI sorting, device details, and advertisement flag inspection |

The current repository README identifies the app as a multi-module Android BLE scanner and describes the `phone` and `wearable` modules. It also notes that the wearable scanner uses balanced scan mode, delayed batch delivery, a 30-second scan window, a capped in-memory device list, and stops scanning when the activity leaves the foreground.

---

## Main Features

### Phone BLE Scanner

The phone app provides the full BLE analysis experience.

It supports:

- BLE scanning
- Device list display
- Device details
- Advertisement flags
- Service UUIDs
- Manufacturer data
- Service data

This makes the phone app useful during embedded development, BLE firmware testing, QA validation, and device bring-up.

### AOSP Watch BLE Scanner

The wearable app provides a compact watch-focused BLE scanning experience.

It supports:

- BLE scanning on an AOSP watch form factor
- RSSI sorting
- Device details
- Advertisement flag inspection
- Battery-conscious scanning behavior

This is especially valuable because wearable devices have smaller screens, tighter battery constraints, and different usability expectations than phones.

### Battery-Conscious Wearable Scanning

The wearable scanner is designed with efficiency in mind.

The wearable README behavior includes:

- Balanced scan mode
- Delayed batch delivery
- 30-second scan window
- Capped in-memory device list
- Scanning stops when the activity leaves the foreground

This shows practical awareness of wearable power and memory constraints.

### Real-Time BLE Discovery

The app discovers nearby BLE devices and updates the UI as scan results arrive. This is useful for checking whether a BLE peripheral is advertising and whether Android can detect it reliably.

### RSSI Sorting

RSSI sorting helps engineers identify nearby devices quickly, especially in environments where many BLE devices are broadcasting at once.

### Device Details

BLE Insight provides device details that help engineers inspect how Android reports a peripheral and whether the scan data matches expected firmware behavior.

### Advertisement Flags

Advertisement flags expose low-level BLE advertising metadata. A dedicated flags view makes the scanner more useful for debugging embedded BLE behavior.

### Service UUIDs, Manufacturer Data, and Service Data

The phone module includes deeper advertisement inspection, including service UUIDs, manufacturer data, and service data. These fields are important for embedded products, beacons, sensors, proprietary BLE peripherals, and custom firmware payloads.

---

## Technical Stack

| Area | Technology |
|---|---|
| Language | Kotlin |
| Platform | Android phone and AOSP watch |
| UI | Android UI / Material 3 |
| Bluetooth | Android Bluetooth Low Energy APIs |
| Project type | Multi-module Android project |
| Modules | `phone`, `wearable` |
| Wearable behavior | Balanced scan mode, delayed batch delivery, scan window, capped list |
| Build system | Gradle Kotlin DSL |
| License | GPL-3.0 |

---

## Repository Structure

```text
BLE_Insight__Android_App/
├── gradle/
├── phone/
├── wearable/
├── build.gradle.kts
├── gradle.properties
├── gradlew
├── gradlew.bat
├── settings.gradle.kts
├── README.md
└── LICENSE
```

The repository is 100% Kotlin and currently contains the `phone` and `wearable` modules.

---

## Architecture Direction

BLE Insight separates phone and wearable experiences into dedicated modules so each form factor can optimize its UI and scanning behavior.

```text
BLE_Insight__Android_App
      ├── phone
      │     └── full BLE scanner and advertisement inspection
      │
      └── wearable
            └── compact AOSP watch BLE scanner with efficiency-focused scanning
```

This is a good structure because phone and wearable apps share the same product mission but have different screen, battery, and interaction constraints.

---

## Phone Module

The phone module is the full BLE scanner experience.

It is designed for:

- Full-size device list browsing
- Device details
- Advertisement flags
- Service UUID review
- Manufacturer data review
- Service data review
- Engineering/debugging workflows

The phone app is useful when deeper BLE advertisement inspection is needed during firmware bring-up or QA validation.

---

## Wearable Module

The wearable module is optimized for AOSP watch use.

It is designed for:

- Quick scans from a watch
- Compact BLE device display
- RSSI-based review
- Device detail checks
- Advertisement flag inspection
- Reduced scan impact on battery and memory

This demonstrates practical mobile engineering across constrained hardware.

---

## BLE Data Use Cases

BLE Insight can help validate:

| Question | Why it matters |
|---|---|
| Is the device advertising? | Confirms embedded firmware is broadcasting |
| Is Android detecting the peripheral? | Confirms platform discovery behavior |
| What is the RSSI? | Helps test signal quality and range |
| Which services are advertised? | Validates BLE profile exposure |
| Is manufacturer data present? | Confirms proprietary payload behavior |
| Is service data present? | Confirms service-specific advertisement data |
| What flags are present? | Helps debug low-level advertisement configuration |
| Does wearable scanning behave efficiently? | Confirms watch-friendly scan strategy |

---

## Embedded, Firmware, and IoT Relevance

This project is especially valuable for embedded and firmware workflows because BLE scanner apps are commonly used during device development.

A firmware engineer can use BLE Insight to verify:

- BLE advertising behavior
- Service UUID configuration
- Manufacturer data payloads
- Service data payloads
- RSSI behavior during range testing
- Advertisement flags
- Phone vs wearable discovery differences
- Watch scanning behavior under battery-conscious constraints

This makes BLE Insight a strong bridge between Android development, AOSP wearable development, and embedded BLE product validation.

---

## How to Build

1. Clone the repository.
2. Open the root project in Android Studio.
3. Let Gradle sync using the included wrapper.
4. Select the `phone` run configuration to test the Android phone app.
5. Select the `wearable` run configuration to test the AOSP watch app.
6. Build and run on real hardware when possible.
7. Grant Bluetooth/location permissions when prompted.
8. Start scanning to inspect nearby BLE devices.

BLE scanning should be tested on physical Android or wearable hardware because emulators generally do not provide reliable access to real nearby BLE advertisements.

---

## Owner

by Harold Paulino

---

## License

This project is licensed under the GPL-3.0 license.
