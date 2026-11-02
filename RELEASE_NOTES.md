# Diamond Radio ATS Mini 1.0.3 — Build 5

Reception, stability, FM coverage, and RDS improvements.

## What's new

- Corrected AM AGC-off gain and AVC maximum-gain conversion for stronger, more consistent reception.
- Corrected AM/SSB antenna tuning above 1.8 MHz while retaining automatic MW/LW selection.
- Restored each band's default modulation, including USB on the upper HF ham bands.
- Fixed restoration of the saved 2 kHz AM bandwidth.
- Seek now uses the correct channel spacing independently of fine-tune steps, with RF gain reapplied after every seek path.
- Station naming from the web interface now runs safely in the receiver task, preventing AP-mode reboots and reporting failed saves.
- CW and RTTY decoding now use a yielding worker with bounded shutdown to prevent menu freezes.
- FM coverage now starts at 87.5 MHz.
- RDS resets on retune and station-identity changes, then displays the station name progressively as valid characters arrive instead of waiting for the complete name.
- No additional RSSI/SNR threshold was imposed on RDS decoding.

## Package

- 16 MB and 8 MB ESP32-S3 application images
- SHA-256 checksums for both images
- OTA metadata for supported radios
- Upstream MIT license, Diamond freeware notice, and third-party notices

## Important

Diamond Dual Boot v2.0 updates only the current Diamond slot and preserves the other slot. Do not use the OTA button inside PUBLIC ATS MINI when preserving the other slot: its built-in updater writes the opposite slot and can overwrite Diamond Radio. Use the manager's PUBLIC ATS MINI - SAFE OTA path and select the slot where PUBLIC ATS MINI currently runs. Back up the existing firmware and keep a known-good application in the other slot. Select the image matching the radio's flash capacity and never overwrite the Diamond factory boot manager.
