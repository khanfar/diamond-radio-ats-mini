# Diamond Radio ATS Mini 1.0.7 — Build 8

This release adds ATS Mini support to Diamond's USB **PC Control** and **FT8 Live Map** website tools, including live FM audio FFT bars, a scrolling audio spectrum/waterfall, receiver controls, and a seek fix.

## What's new

### ATS Mini USB PC Control

Control the receiver from a desktop computer while its normal screen and physical controls remain available:

- Tune FM and HF frequencies.
- Select AM, LSB, or USB where applicable.
- Adjust volume, mute, bandwidth, tuning step, AGC/ATT, and BFO.
- Use SEEK UP and SEEK DOWN. Fixed a timing bug that could acknowledge a seek command without moving from the original station.
- Open supported CW, RTTY, FT8 + WF, FT4 + WF, and FT2 + WF decoder pages from the computer.
- View live signal level, frequency, mode, RDS information, decoder text, and station data.

### FM FFT and live website waterfall

- FM stations now have live audio FFT bars in the PC Control FM view.
- The existing PC Control spectrum and scrolling waterfall now support ATS Mini in FM and HF.
- The radio remains audible and tunable while the website display is active.
- Opening a supported waterfall decoder safely transfers the display feed to that session; returning to the radio restores the ordinary website stream.
- No extra wiring or hardware modification is required.

The website waterfall is the computer's live audio-spectrum view. The separate **3D** button for the ATS-25 radio screen is not used on ATS Mini.

### FT8 Live Map integration

FT8 + WF and FT4 + WF can send accepted decodes to the existing Diamond FT8 Live Map page for station details, flags, locators, and map display.

## How to use PC Control

1. Connect the ATS Mini to the computer with a data-capable USB cable.
2. Open **[Diamond Radio PC Control](https://diamondradio.web.app/pc-control.html)** in a desktop browser with Web Serial support, such as Chrome or Edge.
3. Click **CONNECT**, select the ATS Mini USB port, and confirm. Unlike ATS-25, the Mini does not need a PC-connection setting enabled first.
4. On an FM station, open the FM view to see the live FFT bars. The **WATERFALL** card starts automatically after connection.
5. Tune or change controls normally. Click **DISCONNECT** when finished.

## How to use FT8 Live Map

1. On the ATS Mini, open **MENU → DECODER → FT8 + WF** or **FT4 + WF** and start decoding on the desired band.
2. Open **[Diamond FT8 Live Map](https://diamondradio.web.app/ft8.html)** in Chrome or Edge.
3. Click **CONNECT** and select the same ATS Mini USB port.
4. Accepted stations appear in the decode list and on the map as they are received.

## Development status and known browser-close issue

**ATS Mini PC Control and FT8 website integration are still under active development.** A known native-USB/browser issue can make the ATS Mini reboot when the final browser tab that owns its USB connection is closed or reloaded. This can still happen after using DISCONNECT.

For now, keep the original PC Control or FT8 tab open while using the radio. When following a website link, allow it to open in a new tab rather than closing the original. If the radio restarts after a page closes, reconnect normally; the firmware and saved settings remain installed.

We are continuing to investigate this browser/USB behavior using user feedback and hardware testing. Please report reproducible problems through the Diamond Radio community channels.

## Updating to v1.0.7

Connect the radio to an internet-enabled Wi-Fi network and use either:

- **Diamond Dual Boot → OTA UPDATE**, or
- **Diamond Radio → Settings → OTA UPDATE**.

With Diamond Dual Boot v2.0 or newer, Diamond's OTA path updates only the current Diamond slot and verifies the downloaded image's exact size and SHA-256. Keep the radio powered and connected throughout the update. Keeping a known-good firmware in the other slot is recommended.

For manual installation, download the application image matching the radio's actual **16 MB or 8 MB** flash capacity and install it into an application slot using the official Diamond tools. Never overwrite the factory boot-manager partition.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Its built-in updater writes the opposite slot and can overwrite Diamond Radio. Update PUBLIC ATS MINI only through the manager's **PUBLIC ATS MINI - SAFE OTA** path, selecting the same slot where it currently runs.

## Package

- Separate 16 MB and 8 MB ESP32-S3 application images
- OTA metadata with exact image sizes and SHA-256 hashes
- `SHA256SUMS.txt` for download verification
- Upstream MIT license, Diamond freeware notice, and third-party notices

The images are not interchangeable. Select the image matching the radio's actual flash capacity and never overwrite the Diamond factory boot-manager partition.
