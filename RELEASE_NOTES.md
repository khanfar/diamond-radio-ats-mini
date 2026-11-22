# Diamond Radio ATS Mini 1.0.8 — Build 10

This maintenance update improves the reliability of the ATS Mini online features. It is recommended for all users, especially anyone who has experienced failed EiBi downloads or unavailable weather and propagation information.

## What's new

- **More reliable EiBi downloads** — station schedules should download more consistently.
- **Improved transmitter information** — EiBi transmitter locations and related station details now load more reliably.
- **Improved Extra features** — Propagation, Forecast, and Weather should open and refresh more consistently.
- **Better repeated use** — online features continue working more reliably after previous downloads or refreshes.
- **Existing features retained** — tuning, audio, decoders, maps, waterfalls, favorites, and receiver controls remain unchanged.

No hardware modification or additional settings are required. Connect the radio to an internet-enabled Wi-Fi network and use the features normally.

## How to update

Connect the radio to Wi-Fi and use either:

- **Diamond Dual Boot → OTA UPDATE**, or
- **Diamond Radio → Settings → OTA UPDATE**.

Keep the radio powered and connected throughout the update. With Diamond Dual Boot v2.0 or newer, Diamond's OTA path updates the current Diamond slot while preserving the other slot. Keeping known-good firmware in the other slot is still recommended.

For manual installation, download the application image matching the radio's actual **16 MB or 8 MB** flash capacity and install it into an application slot using the official Diamond tools. Never overwrite the factory boot-manager partition.

**Do not use the OTA button inside PUBLIC ATS MINI when you want to preserve the other slot.** Update PUBLIC ATS MINI only through the manager's **PUBLIC ATS MINI - SAFE OTA** path, selecting the same slot where it currently runs.

## PC Control development notice

ATS Mini PC Control and FT8 website integration remain under active development. The known issue where closing or reloading the final browser tab that owns the Mini USB connection can reboot the radio remains under investigation.

For now, keep the original PC Control or FT8 tab open while using the radio and open other website links in new tabs.

## Package

- Separate 16 MB and 8 MB application images
- OTA update metadata
- `SHA256SUMS.txt` for checking downloads
- License and third-party notices

Older releases remain available. The two firmware images are not interchangeable; choose the image matching the radio's actual flash capacity.
