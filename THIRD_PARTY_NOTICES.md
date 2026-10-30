# Third-party notices

Diamond Radio ATS Mini is a derivative of the MIT-licensed GNBD/miniradio
receiver firmware, with Diamond-specific modifications by M Khanfar. The
upstream copyright and full MIT permission notice are preserved in `LICENSE`.
Diamond modifications and branding are covered separately by
`DIAMOND_FREEWARE_NOTICE.txt`.

Binary releases must include this file, `LICENSE`, and the accompanying
`THIRD_PARTY_LICENSES` directory. Third-party components remain under their
own licenses; no upstream copyright or permission notice is replaced by
Diamond branding or distribution terms.

## Receiver framework and display port

- GNBD and miniradio contributors: MIT; full text in `LICENSE`.
- ESP32-SI4732 Radio and Max Arnold display port: MIT; notice in
  `THIRD_PARTY_LICENSES/DISPLAY_PORT.txt`.
- SI4732 SSB patch loader: miniradio contributors, MIT. Patch data is derived
  from Silicon Labs AN332 Rev 0.8 and the PU2CLR SI4735 project lineage; see
  the source notices and `THIRD_PARTY_LICENSES/SI4732_PATCH.txt`.

## Bundled components

- LovyanGFX 1.2.29: lovyan03, FreeBSD two-condition license. Its bundled
  license also preserves Adafruit_GFX, Adafruit_ILI9341, and TFT_eSPI notices.
  Full text: `THIRD_PARTY_LICENSES/LOVYANGFX.txt`.
- joltwallet LittleFS 1.23.0: Brian Pugh, MIT. Full text:
  `THIRD_PARTY_LICENSES/JOLTWALLET_LITTLEFS.txt`.
- littlefs: the littlefs authors and Arm Limited, BSD three-condition
  license. Full text: `THIRD_PARTY_LICENSES/LITTLEFS.txt`.
- ESP-IDF 5.5.5 and its linked components: Espressif Systems and respective
  contributors. The framework's Apache License 2.0 text is in
  `THIRD_PARTY_LICENSES/APACHE-2.0.txt`; component notices supplied by the
  installed ESP-IDF release are in `THIRD_PARTY_LICENSES/ESP-IDF-NOTICES.txt`.
- MbedTLS: Apache License 2.0; see `THIRD_PARTY_LICENSES/MBEDTLS.txt` when
  supplied by the ESP-IDF release.
- ft8_lib: Kārlis Goba, MIT. Used for FT8 message packing, candidate search,
  CRC and LDPC decoding. Full text: `THIRD_PARTY_LICENSES/FT8_LIB.txt`.

The on-device Legal page provides the principal upstream MIT notice and
component attribution. These release files provide the longer license texts.
