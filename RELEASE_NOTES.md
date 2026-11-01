# Diamond Radio ATS Mini 1.0.2 — Build 4

Slot-preserving OTA through Diamond Dual Boot v2.0.

## What's new

- Settings → OTA UPDATE now hands the update to Diamond Dual Boot.
- Only the currently running Diamond slot is replaced; the other firmware remains unchanged.
- Dual Boot v2.0 also provides PUBLIC ATS MINI - SAFE OTA into a user-selected slot, with the release version shown during confirmation.
- The manager verifies Diamond's exact image size and SHA-256 and checks the other slot before and after installation.
- Dual Boot SETTINGS → WIFI SETUP scans networks and saves a manager-owned connection, allowing OTA into empty slots after a clean install.
- Typed password characters are visible for correction; saved passwords are not displayed.
- Successful setup shows the network and IP address, and a green WIFI CONNECTED indicator appears on the manager's main screen.
- Receiver-saved WiFi credentials can also be reused.

## Package

- 16 MB and 8 MB ESP32-S3 application images
- SHA-256 checksums for both images
- OTA metadata for supported radios
- Upstream MIT license, Diamond freeware notice, and third-party notices

## Important

Install or upgrade to Diamond Dual Boot v2.0 before using this OTA handoff. Do not use the OTA button inside PUBLIC ATS MINI when preserving the other slot: its built-in updater writes the opposite slot and can overwrite Diamond Radio. Use the manager's PUBLIC ATS MINI - SAFE OTA path and select the slot where PUBLIC ATS MINI currently runs. Back up the existing firmware and keep a known-good application in the other slot. Select the image matching the radio's flash capacity and never overwrite the Diamond factory boot manager.
