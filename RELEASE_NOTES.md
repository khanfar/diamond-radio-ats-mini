# Diamond Radio ATS Mini 1.0.6 — Build 7

A major decoder, waterfall, and quality-of-life release. It adds live FT8/FT4/FT2 waterfall decoders, rebuilt CW/RTTY, PSK31, SSTV and WEFAX, fast standalone-waterfall controls, persistent frequency lock, temperature units, and multiple stability fixes.

## Frequency lock and weather units

### FREQ LOCK

- Added **MENU → FREQ LOCK** and optional **SETTINGS → QUICK SET → FREQ LOCK**.
- The ON/OFF state and current frequency are saved immediately and restored after restart.
- While locked, ordinary rotation and press-and-turn digit tuning cannot change the frequency.
- Rotate right/left to increase/decrease volume instead.
- Hold the knob to open Quick List even when long-press is normally configured for NUMPAD. Short-press still opens the main menu, so both lock controls remain reachable.
- Default is OFF; ordinary unlocked tuning is unchanged.

### TEMP UNIT

- Added **SETTINGS → TEMP UNIT → CELSIUS / FAHRENHEIT**.
- The selection applies to current weather, daily high/low temperatures, and the five-day view.
- Celsius remains the default, and the selection persists after restart.

## Digital and image decoders

Open **MENU → DECODER** and choose from **CW, RTTY, PSK31, FT8, FT8 + WF, FT4 + WF, FT2 + WF, SSTV,** or **WEFAX**.

### FT8 + WF — new live-waterfall decoder

- Added an independent, higher-performance FT8 decoder with a smooth real-time audio waterfall and responsive controls, while preserving the original **FT8** mode as a separate choice.
- Shows decoded stations with country flags, message details, locator, distance, and bearing.
- Includes the station list, detailed station view, offline map, QTH/route markers, band presets, visual noise filter, auto-hop, volume, clear, and exit controls.
- The original FT8 decoder and its established behavior are not replaced.

### FT4 + WF and FT2 + WF

- Added **FT4 + WF** with USB presets, live waterfall, decoding, station list/details/map, flags, auto-hop, palettes, noise filter, and audio-input selection.
- Added **FT2 + WF** with responsive decoding, FT2 USB presets, and the same Diamond station presentation and controls.
- Fixed a problem that could cause a reboot when exiting FT2 + WF. FT8/FT4/FT2 waterfall sessions now enter and exit cleanly.

### Using FT8/FT4/FT2 + WF

1. Choose the desired **+ WF** decoder from **MENU → DECODER**.
2. Select a band preset. The radio tunes the listed frequency in USB automatically.
3. Rotate on the main decoder screen for 100 Hz fine tuning.
4. Short-press a decoded station for its information. Open **STATION LIST** from the hold menu to browse all heard stations.
5. Hold for approximately half a second to open actions: **MAP, STATION LIST, CHANGE BAND, AUTO HOP, WATERFALL COLORS, NOISE FILTER, AUDIO INPUT, VOLUME, CLEAR,** and **EXIT**.
6. In the map, rotate to move between located stations. Short-press to switch between station selection and zoom; rotate to zoom while zoom mode is active. Hold to return to decoding.
7. **AUDIO INPUT → ADC** is the default and uses the radio's existing audio input without extra hardware. **MIC** is optional for suitable INMP441 wiring; ordinary reception should use ADC.

Wi-Fi is paused during these decoder sessions and restored on normal exit. If the radio is powered off during decoding, saved station credentials now authorize Wi-Fi reconnection at the next boot.

### CW, RTTY, and PSK31

- Rebuilt **CW** and **RTTY** for improved reception and added **PSK31**.
- CW automatically tracks the received tone and sending speed.
- RTTY supports 45.45/50/75 baud, 170/450/850 Hz shifts, normal/reverse modes, and unshift-on-space.
- PSK31 includes automatic/manual carrier control, carrier tracking, and squelch.
- Each mode has a live spectrum, signal level, decoder status, and four automatically wrapping/scrolling text lines.
- Fixed spectrum flicker, clipped lower text, row spacing, and bottom-edge layout problems.

Rotate to tune CW/RTTY or adjust the PSK31 carrier. Hold for preset, mode, carrier/squelch, clear-text, volume, back, and exit actions as applicable to the selected decoder.

### SSTV

- Added progressively drawn SSTV images with automatic VIS detection and manual mode selection.
- Supported modes: **Martin M1/M2, Scottie S1/S2/DX, Robot 36/72, B/W 8/12/24/36,** and **PD50/90/120/160/180/240/290**.
- Improved sync recovery to prevent repeated false **SIGNAL LOST** restarts during otherwise decodable Martin M1 reception.
- Rotate to fine-tune in 50 Hz steps. Hold for **SSTV MODE, CLEAR IMAGE, VOLUME, EXIT SSTV,** and **BACK**.

### WEFAX

- Added progressively drawn grayscale WEFAX reception with IOC 576, automatic phasing, calibrated black/white levels, stop-tone detection, and manual start.
- Supports **120/90/60 LPM** line speeds.
- Rotate to fine-tune in 50 Hz steps. Hold for **START NOW, STOP, LINE SPEED, CLEAR IMAGE, VOLUME, EXIT WEFAX,** and **BACK**.

## Live audio waterfall

The old muted signal-strength sweep has been replaced by a real-time audio waterfall. The current station remains audible and tunable while the waterfall is running.

### Open and control the standalone waterfall

- **Double-click the knob on the normal radio screen** to open it immediately.
- It is also available through **MENU → WATERFALL**.
- A single click on the radio screen still opens the menu after a short double-click detection interval.
- Rotate normally to tune the receiver.
- **Hold once:** enter color mode. Rotate to change the palette and watch the existing waterfall recolor immediately.
- **Hold again:** enter full-screen tuning mode. The bottom information/help area disappears and the waterfall expands to the bottom of the display. Rotate to tune.
- **Hold again:** enter full-screen color mode and rotate to change colors.
- **Hold once more:** return to the normal waterfall layout.
- **Single-click in any waterfall mode:** exit to the radio.

### Waterfall settings

- **SETTINGS → WF SPEED:** **SLOW (160 ms/row)** or **FAST (48 ms/row)**. This controls the standalone and compact display waterfalls, not decoder protocol timing.
- **SETTINGS → WF COLOR:** seven persistent shared palettes: **DIAMOND, PHOSPHOR, AMBER, ICE, BLUE, VIOLET,** and **SUNSET**.
- The same palette is used by the standalone waterfall, compact SIGNAL BOX waterfall, and FT8/FT4/FT2 + WF displays.
- Fixed waterfall startup failures, unstable in-page headers, and radio/menu flicker or ghosting after exit.

## Main-screen SIGNAL BOX waterfall

- Added **SETTINGS → SIGNAL BOX → GRAPH / WATERFALL**.
- **GRAPH** preserves the red RSSI and yellow SNR history display.
- **WATERFALL** places a live audio waterfall inside the left signal box while retaining the normal radio page and controls.
- WF SPEED and WF COLOR also control this compact view.
- Fixed incorrect compact-waterfall appearance after powering on directly into FM.

## EXTRA and rain-map reliability

- Added **EXTRA → EXIT** for a direct return to the radio.
- Leaving RAIN MAP stops unnecessary download activity and prevents stale screen updates.
- Fixed persistent radio/menu flicker and ghost shadows after leaving RAIN MAP.
- Rain caching, QTH-centered zoom, offline reopening, propagation, forecast, and weather behavior remain available as in v1.0.5.

## Receiver coverage and other fixes

- Extended **CB** and **SW ALL** upper coverage to include **27.455 MHz**.
- Existing bands, tuning steps, decoder presets, and modulation behavior remain unchanged.
- Saved Wi-Fi station credentials now trigger reconnection after reboot even if power was removed while a decoder had temporarily paused Wi-Fi.
- Improved decoder and waterfall stability, including reliable exit and re-entry.

## Updating to v1.0.6

Connect the radio to an internet-enabled Wi-Fi network. Use either:

- **Diamond Dual Boot → OTA UPDATE**, or
- **Diamond Radio → Settings → OTA UPDATE**.

With Diamond Dual Boot v2.0 or newer, Diamond's OTA path updates only the current Diamond slot and verifies the downloaded image's exact size and SHA-256. Keep the radio powered and connected throughout the update. Keeping a known-good firmware in the other slot is recommended.

For manual installation, download the application image matching the radio's actual **16 MB or 8 MB** flash capacity and install it into an application slot using the official Diamond tools. Never overwrite the factory boot-manager partition.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Its built-in updater writes the opposite slot and can overwrite Diamond Radio. Update PUBLIC ATS MINI only through the manager's **PUBLIC ATS MINI - SAFE OTA** path, selecting the same slot where it currently runs.

## Package

- Separate 16 MB and 8 MB ESP32-S3 application images
- OTA metadata with exact image sizes and SHA-256 hashes
- `SHA256SUMS.txt` for download verification
- Upstream MIT license, Diamond freeware notice, and updated third-party notices

The images are not interchangeable. Select the image matching the radio's actual flash capacity and never overwrite the Diamond factory boot-manager partition.
