# Diamond Radio ATS Mini 1.0.1

First public Diamond Radio ATS Mini firmware release, with verified over-the-air updates.

## Highlights

- Diamond Radio receiver interface for ATS Mini ESP32-S3/SI4732 hardware
- FT8 decoding, station map, country information, and FT8 over WiFi
- Safe A/B OTA updates with release notes, exact-size checks, and SHA-256 verification
- Separate application images for 16 MB and 8 MB radios
- WiFi receiver control, EiBi schedule support, and Diamond dual-boot compatibility

## Package

- 16 MB and 8 MB ESP32-S3 application images
- SHA-256 checksums for both images
- OTA metadata for supported radios
- Upstream MIT license, Diamond freeware notice, and third-party notices

## Important

This is a beta release for hardware testing. Back up the existing firmware and keep a known-good application in the other dual-boot slot. Select the image matching the radio's flash capacity and never overwrite the Diamond factory boot manager.
