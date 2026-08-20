# Changelog

## 0.0.30 – 2026-08-20

### Changed

- **Migrated to Docker BuildKit** – Dockerfile now uses an explicit base image (`ghcr.io/home-assistant/base:2026.08`) instead of `FROM $BUILD_FROM`.  
  This is required for compatibility with Home Assistant OS 2026.04 and newer. [2][18]
- **Configuration format updated** – `config.json` replaced by `config.yaml` to align with current Home Assistant app documentation. [18]
- Adjusted Dockerfile labels and build arguments to match the new app build process. [2]

### Fixed

- Fixed add-on installation failure on Home Assistant OS 2026.04+ where builds failed with  
  `ERROR: failed to build: base name ($BUILD_FROM) should not be blank`.

### Notes

- Minimum required Home Assistant OS version: **2026.04** (recommended: **2026.08** or newer).
- Existing configuration options remain unchanged; the update is backward compatible from a user perspective.

## 0.0.29
- Updated noah-mqtt to version [`0.0.29`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.29)

## 0.0.28
- Updated noah-mqtt to version [`0.0.28`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.28)

## 0.0.27
- Updated noah-mqtt to version [`0.0.27`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.27)

## 0.0.26
- Updated noah-mqtt to version [`0.0.26`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.26)

## 0.0.25
- Updated noah-mqtt to version [`0.0.25`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.25)

## 0.0.24
- Updated noah-mqtt to version [`0.0.24`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.24)

## 0.0.23
- Updated noah-mqtt to version [`0.0.23`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.23)

## 0.0.22
- Updated noah-mqtt to version [`0.0.22`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.22)

## 0.0.21
- Updated noah-mqtt to version [`0.0.21`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.21)

## 0.0.20
- Updated noah-mqtt to version [`0.0.20`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.20)

## 0.0.19
- Updated noah-mqtt to version [`0.0.19`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.19)

## 0.0.18
- Updated noah-mqtt to version [`0.0.18`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.18)

## 0.0.17
- Updated noah-mqtt to version [`0.0.17`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.17)

## 0.0.16
- Updated noah-mqtt to version [`0.0.16`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.16)

## 0.0.15
- Updated noah-mqtt to version [`0.0.15`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.15)

## 0.0.14
- Updated noah-mqtt to version [`0.0.14`](https://github.com/mtrossbach/noah-mqtt/releases/tag/v0.0.14)
