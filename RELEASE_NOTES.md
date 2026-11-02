# Diamond Radio ATS Mini 1.0.4 — Build 6

Adds selectable Wi-Fi transmit power for radios that need reduced Wi-Fi current.

## What's new

- New **Settings → WI-FI POWER** menu with **NORMAL** and **SAFE - 13 dBm** choices.
- **NORMAL** is the default and preserves the existing behavior: a 14 dBm maximum, or the existing adaptive 14/13/8/5 dBm levels when Power Save is enabled.
- **SAFE - 13 dBm** applies a fixed 13 dBm limit, including when Power Save is active.
- The setting applies immediately and is saved across restarts. It covers station/AP mode, scans, the web console, and FT8-over-Wi-Fi.
- Diamond Dual Boot v2.1 provides a separate **SETTINGS → WIFI POWER** choice for manager Wi-Fi setup and OTA. Its initial default is SAFE; NORMAL restores the manager's previous default transmit power.

## Package

- 16 MB and 8 MB ESP32-S3 application images
- SHA-256 checksums for both images
- OTA metadata for supported radios
- Upstream MIT license, Diamond freeware notice, and third-party notices

## Compatibility note

Some clone boards can reset or brown out when Wi-Fi transmission causes a power-supply voltage drop. SAFE mode is intended for those boards. This release has been installed and hash-verified on a v4 radio; confirmation on an affected clone still requires field testing. Reducing transmit power can reduce Wi-Fi range.

## Important

Diamond Dual Boot v2.0 or newer updates only the current Diamond slot and preserves the other slot. Do not use the OTA button inside PUBLIC ATS MINI when preserving the other slot: its built-in updater writes the opposite slot and can overwrite Diamond Radio. Use the manager's PUBLIC ATS MINI - SAFE OTA path and select the slot where PUBLIC ATS MINI currently runs. Back up the existing firmware and keep a known-good application in the other slot. Select the image matching the radio's flash capacity and never overwrite the Diamond factory boot manager.
