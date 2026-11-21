# Diamond Radio ATS Mini 1.0.8 — Build 9

This release adds NAVTEX maritime safety-message decoding on the radio and through Diamond PC Control, with continuous live USB text for NAVTEX, CW, and RTTY.

## What's new

### NAVTEX on ATS Mini

- Decode NAVTEX directly on the radio without a computer, audio cable, or hardware modification.
- Select standard MF and HF maritime channels, including 518 kHz, 490 kHz, and 4209.5 kHz.
- Tune accurately in USB, adjust the tuning step, or enter a frequency directly from the decoder menu.
- Follow live spectrum, tone markers, SYNC/LOCK, and error status while messages arrive.
- Press the knob to switch between tuning and scrolling through received text.

The displayed frequency is the **USB dial frequency**, normally 1.7 kHz below the NAVTEX channel. For example, use **516.30 kHz USB** for the **518 kHz** channel.

### NAVTEX in PC Control

1. Connect the ATS Mini by USB and open [Diamond PC Control](https://diamondradio.web.app/pc-control.html) in Chrome or Edge.
2. Open **NAVTEX**, select a channel preset, or enter the USB dial frequency in kHz.
3. Click **TUNE NAVTEX**. Received text appears continuously in the green live-message box; no audio cable is needed.
4. Use **SAVE LOG** to save the message as a TXT file.
5. Open **NAV SCHED** for the offline worldwide timetable, scheduled-now and upcoming-station filters, QTH distance sorting, and one-click tuning.

### Volume and reception guidance

A tested ATS Mini starting point is **radio volume 38**, approximately **60% in PC Control**. This is not a fixed requirement. Antenna, signal strength, interference, and the local environment change the optimum.

Adjust volume during an active transmission while watching SYNC/LOCK and ERR. Increase a very low setting if the signal is buried in noise; reduce it if high volume causes overload or distortion. Higher volume is not automatically better. Accurate USB tuning and centering the two tones between the markers are equally important.

### USB text reliability

NAVTEX, CW, and RTTY text now continues beyond the initial visible box and through long messages. New text is forwarded incrementally without allocating large USB snapshots, and long-message rollover retains the latest text correctly.

All receiver controls, digital decoders, maps, weather tools, waterfalls, and other features from earlier releases remain available.

## Development status and known browser-close issue

**ATS Mini PC Control and FT8 website integration remain under active development.** A known native-USB/browser issue can make the ATS Mini reboot when the final browser tab that owns its USB connection is closed or reloaded. This can still happen after using DISCONNECT.

For now, keep the original PC Control or FT8 tab open while using the radio. Open website links in new tabs rather than closing the original. If the radio restarts after a page closes, reconnect normally; the firmware and saved settings remain installed.

## Updating to v1.0.8

Connect the radio to an internet-enabled Wi-Fi network and use either:

- **Diamond Dual Boot → OTA UPDATE**, or
- **Diamond Radio → Settings → OTA UPDATE**.

With Diamond Dual Boot v2.0 or newer, Diamond's OTA path updates only the current Diamond slot and verifies the downloaded image's exact size and SHA-256. Keep the radio powered and connected throughout the update. Keeping known-good firmware in the other slot is recommended.

For manual installation, download the application image matching the radio's actual **16 MB or 8 MB** flash capacity and install it into an application slot using the official Diamond tools. Never overwrite the factory boot-manager partition.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Its built-in updater writes the opposite slot and can overwrite Diamond Radio. Update PUBLIC ATS MINI only through the manager's **PUBLIC ATS MINI - SAFE OTA** path, selecting the same slot where it currently runs.

## Package

- Separate 16 MB and 8 MB ESP32-S3 application images
- OTA metadata with exact image sizes and SHA-256 hashes
- `SHA256SUMS.txt` for download verification
- Upstream MIT license, Diamond freeware notice, and third-party notices

The images are not interchangeable. Select the image matching the radio's actual flash capacity and never overwrite the Diamond factory boot-manager partition.
