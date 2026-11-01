# Diamond Radio ATS Mini

Official firmware releases for the **Diamond Radio ATS Mini** receiver.

- Product and Diamond-specific modifications: **M Khanfar**
- Distribution: **freeware**; Diamond-specific source code is not distributed
- Official website: **[diamondradio.web.app](https://diamondradio.web.app/)**
- Current public firmware version: **1.0.2 — Build 4**

This repository contains release binaries, update metadata, checksums, and license notices only. It is not a source-code repository.

## Downloads

Choose the application image matching the radio's actual flash capacity:

| File | Flash capacity | Maximum application size |
| --- | ---: | ---: |
| `diamond-mini-16mb.bin` | 16 MB | 3,670,016 bytes |
| `diamond-mini-8mb.bin` | 8 MB | 2,621,440 bytes |

Always verify the downloaded file against `SHA256SUMS.txt` before installation. The two images are not interchangeable: an image larger than the radio's application partition must not be installed.

## Installation and dual boot

Diamond Radio ATS Mini uses the Diamond dual-boot layout with two application slots and a separate factory boot manager.

1. Back up the radio's existing firmware and settings.
2. Open the official installation tools on [diamondradio.web.app](https://diamondradio.web.app/).
3. Select the correct 16 MB or 8 MB application image.
4. Install it into an application slot through the Diamond dual-boot tools. **Never overwrite the factory boot-manager partition.**
5. Start the new slot from the Diamond boot manager.

Keep a known-good firmware in the other application slot when testing a new release.

## OTA updates

With **Diamond Dual Boot v2.0** and Diamond Radio **v1.0.2 or newer**, connect Wi-Fi to an internet-enabled network and open **Settings → OTA UPDATE**. Diamond hands the update to the boot manager, which downloads the official release into the **current slot only**, verifies its exact size and SHA-256, and checks that the other slot stayed unchanged.

The manager's **OTA UPDATE → PUBLIC ATS MINI - SAFE OTA** path installs the latest public release into a user-selected slot and displays its version before installation. **SETTINGS → WIFI SETUP** scans networks and saves a manager-owned connection, so OTA also works into empty slots after a clean install. Typed password characters are visible for correction, saved passwords are not displayed, and the manager shows the connected IP address plus a green main-screen status indicator. Receiver-saved credentials can be reused too. A failed or cancelled installation does not select the incomplete image, but the selected slot may need reinstallation; the other slot is not intentionally modified. Keep the radio powered throughout installation.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Its built-in updater writes the opposite slot and will overwrite Diamond Radio if Diamond is installed there. Dual Boot cannot intercept that write. Always update PUBLIC ATS MINI through the manager's **SAFE OTA** path, selecting the same slot where it currently runs. Older manager and Diamond versions also lack the slot-preserving path.

## Legal and third-party notices

Diamond Radio ATS Mini is based on the MIT-licensed GNBD/miniradio receiver framework and includes third-party components. Their copyright and license notices are preserved in:

- [`LICENSE`](LICENSE) — upstream MIT license
- [`DIAMOND_FREEWARE_NOTICE.txt`](DIAMOND_FREEWARE_NOTICE.txt) — Diamond binary distribution terms
- [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) — component attribution
- [`THIRD_PARTY_LICENSES/`](THIRD_PARTY_LICENSES/) — accompanying third-party license texts

Unmodified binary releases may be redistributed free of charge with these notices. Diamond names, logos, and visual identity are not licensed for branding derivative products. No rights of upstream or third-party authors are replaced or removed.
