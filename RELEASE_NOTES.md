# Diamond Radio ATS Mini 1.0.5 — Build 7

A feature and reliability release with new EXTRA tools, expanded receiver controls, additional FT8 presets, and detailed EiBi transmitter information and maps.

## EXTRA: propagation, forecast, weather, and rain radar

- Added **EXTRA** to the main menu and as an optional Quick-menu action. **VOLUME** is now the first functional main-menu item.
- **PROPAGATION** shows an original world map with your saved or IP-derived QTH, UTC day/night shading, solar indices, and selectable 160/80/60/40/30/20/17/15/12/10 m band conditions.
- **FORECAST** presents three days of NOAA three-hour Kp predictions as knob-selectable daily graphs.
- **WEATHER** shows current conditions and a knob-selectable **NEXT 5 DAYS** view with daily conditions, high/low temperatures, and rain probability.
- **RAIN MAP** combines OpenStreetMap and the latest RainViewer radar around your QTH. It includes QTH-centered zoom 3–7, a zoom badge, an accurate distance scale, full four-tile coverage, and visible refresh progress.
- Rain maps are cached on the radio for fast reopening and offline viewing. Turning the knob updates the zoom display immediately and downloads only the final selected zoom after a short pause.
- Network reliability was improved with dynamic TLS buffers, staged LittleFS downloads, bounded memory use, complete-request retries, clearer error diagnostics, and cached/stale-data fallbacks.

### Using EXTRA

Open **MENU → EXTRA**, then choose a tool. EXTRA needs Wi-Fi with internet access for fresh online data; the rain map can reopen its saved cache offline. Rotate the knob to change the propagation band, forecast day, weather page, or rain-map zoom. Short-press **PROPAGATION**, **FORECAST**, or **RAIN MAP** to refresh/retry. Hold the knob to go back.

## Receiver operation and display

- Added **Settings → FM REGION**:
  - **WORLD**: 87.5–108 MHz (default)
  - **JAPAN**: 76–95 MHz Wide FM
- FM region limits apply to tuning, seek/ATS, presets, band memory, and web control, and persist after restart.
- Fixed SSB audio remaining muted after band/mode changes until bandwidth was adjusted.
- Added **Settings → CALLSIGN**. An entered callsign appears in orange on the boot splash; leaving it empty preserves the standard splash.
- Fixed favorites navigation: rotating now selects a slot without unexpectedly retuning an occupied favorite.
- Fixed cropping of the final **M** in the **MHz** unit on long frequencies.
- The left signal-history RSSI trace is now red; the SNR trace remains yellow.

### Using favorites and Quick FAV TUNE

In the favorites list, rotate to select a slot, short-press an occupied slot to tune it, long-press an empty slot to save the current station, and long-press an occupied slot to delete it.

For tune-as-you-scroll behavior, enable **Settings → QUICK SET → FAV TUNE**, then use **Quick → FAV TUNE** to switch it ON or OFF. Keep it OFF when you want to move safely from an occupied slot to an empty slot before saving.

## Tuning mute, Soft Mute, and NUMPAD

- Added persistent **Settings → TUNE MUTE**, default ON. It suppresses the tuning noise while turning the knob and restores audio shortly after tuning stops.
- Fixed **SOFT MUTE OFF** remaining off after restart and made FM use the selected Soft Mute value instead of a fixed value.
- Added an on-screen 12-key **NUMPAD** for direct frequency entry in the current band and mode.
- Added **Settings → LONG PRESS** to choose whether holding the knob on the radio screen opens **QUICK LIST** or **NUMPAD**.
- NUMPAD can also be added through **Settings → QUICK SET**.

### Using NUMPAD

FM accepts MHz with up to three decimal digits; AM/LSB/USB accept integer kHz. Rotate to select a key and short-press to enter it or confirm **OK**. Long-press deletes a character; long-press with an empty entry cancels. Frequencies outside the current band are rejected. The page closes after 20 seconds without input.

## FT8 presets

- Added **11m CB — 27.245 MHz USB** and **11m CB — 27.265 MHz USB** to the FT8 band chooser.
- Both are available when entering FT8 and through **CHANGE FT8 BAND** in the FT8 hold menu.
- These are community-used CB digital frequencies, not official amateur-band allocations. The established FT8 decoder and DSP behavior are unchanged in this release.

## EiBi transmitter details and offline map

- EiBi schedule updates now also retrieve compact transmitter-site reference data. Normal schedule downloads remain usable if the site reference cannot be downloaded.
- While tuned to an active scheduled station, the radio can show its transmitter site, host country, great-circle distance, and initial bearing from your saved QTH.
- Long location information is arranged in two fitted rows beside the signal-history box without overlapping it.
- Added optional **Settings → QUICK SET → EIBI MAP**. The map works offline and shows your QTH in red, the transmitter in gold, a great-circle route, and station/site/country with distance and bearing.
- Added transmitter-centered **X1/X2/X4/X8** zoom.
- Fixed Quick-menu selection so enabled actions remain selectable when other entries are hidden in AM/SSB.

### Using EIBI MAP

Update the EiBi database using the existing EiBi controls, tune to an active scheduled station with transmitter information, enable **EIBI MAP** in **Settings → QUICK SET**, then open **Quick → EIBI MAP**. Rotate to zoom and press or hold to return. Distance, bearing, and the QTH marker require a saved QTH; a missing QTH does not prevent viewing the transmitter location.

## Updating to v1.0.5

Connect the radio to an internet-enabled Wi-Fi network. Use either:

- **Diamond Dual Boot → OTA UPDATE**, or
- **Diamond Radio → Settings → OTA UPDATE**.

With Diamond Dual Boot v2.0 or newer, Diamond's OTA path updates only the current Diamond slot and verifies the downloaded image. Keep the radio powered and connected throughout the update. Keeping a known-good firmware in the other slot is recommended.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Its built-in updater writes the opposite slot and can overwrite Diamond Radio. Update PUBLIC ATS MINI only through the manager's **PUBLIC ATS MINI - SAFE OTA** path, selecting the same slot where it currently runs.

## Package

- Separate 16 MB and 8 MB ESP32-S3 application images
- OTA metadata with exact image sizes and SHA-256 hashes
- `SHA256SUMS.txt` for download verification
- Upstream MIT license, Diamond freeware notice, and third-party notices

The images are not interchangeable. Select the image matching the radio's actual flash capacity and never overwrite the Diamond factory boot-manager partition.
