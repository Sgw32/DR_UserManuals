# Digifiz Replica User Manuals

[![CI](https://github.com/Sgw32/DR_UserManuals/actions/workflows/main.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/main.yml)
[![CI (French)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/french.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/french.yml)
[![CI (German)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/german.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/german.yml)
[![CI (Hungarian)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/hungarian.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/hungarian.yml)
[![CI (Russian)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/russian.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/russian.yml)
[![CI (Spanish)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/spanish.yml/badge.svg)](https://github.com/Sgw32/DR_UserManuals/actions/workflows/spanish.yml)

This repository hosts the LaTeX sources for the official documentation shipped with every Digifiz Replica dashboard.  The manuals cover both hardware generations—the classic Arduino Mega (ATmega2560) cluster and the Digifiz Next ESP32-based units—and are kept in sync with the production firmware and wiring harnesses.

## 📘 What is inside

- **Full installation and configuration guide** explaining wiring, calibration, firmware flashing, and safety notes for each hardware revision.
- **Feature reference** detailing onboard diagnostics, display modes, warning logic, and localization options available in the latest firmware.
- **Appendices for technicians** with connector pinouts, signal tables, sensor compatibility, and troubleshooting flows collected from the community.

The compiled PDF (`DR_DRNext_User_Manual_mk1_mk2.pdf`) is the master document used for customer deliveries.  Each section of the manual lives in the `chapters/` directory, supporting data and macros reside in `preamble/`, while ancillary assets (figures, tables, and scripts) are stored under `figures/` and `anc/`.

Localized builds are published alongside the English edition: French (`_fr`), Russian (`_ru`), Hungarian (`_hu`), German (`_de`), and now Spanish (`_es`).

## 🚗 Hardware overview

Digifiz Replica is a modern replacement for factory VDO clusters in second-generation Volkswagen Group vehicles and now also in classic Audi platforms.  Hundreds of units are already in the field, with active deployments in the USA, Germany, the UK, Italy, Russia, and across the EU.

### Supported vehicles

- **Volkswagen Jetta Mk2 (1984–1992)** — CE1 and CE2 fuse panels
- **Volkswagen Golf Mk2 (1983–1992)** — CE1 and CE2 fuse panels
- **Volkswagen Passat B2 (1984–1992)** — expected compatibility, pending customer confirmation
- **Volkswagen Scirocco 2 (1984–1992)** — requires a contact adapter
- **Audi 80 B2 (1978–1986)** — red and green Digifiz variants
- **Audi 80 Coupé B2 (1980–1988)** — red and green Digifiz variants

### Firmware and tooling requirements

| Hardware generation | Toolchain | Notes |
| --- | --- | --- |
| **Arduino Mega / ATmega2560** | Arduino IDE ≥ 1.8.13 with the board set to **Arduino Mega / ATmega2560**. Use `Ctrl + Shift + U` for USBasp uploads. | Required libraries: `RTClib` (non-Neuron version), `SparkFun EEPROM`, `Adafruit_BusIO`, `MedianFilterLib2`.  `MD_MAX72xx` is obsolete—do not install it. |
| **Digifiz Next (ESP32)** | Espressif ESP-IDF v5.2.1 | Follow the flashing instructions in the manual for OTA and USB-C workflows. |

## 🛠️ Building the manual locally

1. Install a recent TeX distribution (TeX Live 2025 or newer is recommended) that includes `latexmk`, `pdflatex`/`lualatex`, and `biber`.
2. For the automated figure pipeline, also install `inkscape`, `perl`, `sed`, `uconv`, and `ghostscript`.  These utilities enable vector export and watermark generation used in the PDF.
3. Clone this repository and run:

   ```sh
   latexmk DR_DRNext_User_Manual_mk1_mk2
   ```

   The command builds `DR_DRNext_User_Manual_mk1_mk2.pdf` in the repository root.  Clean builds (`latexmk -C`) and alternative engines can be configured in `.latexmkrc`.

If you prefer cloud editing, you can upload the project to Overleaf.  Select the latest TeX Live compiler and ensure shell-escape is enabled for chapters that render SVG figures.

## 🤝 Community and support

- Russian-speaking community: [vk.com/digifiz](https://vk.com/digifiz)
- News and discussions (RU): [t.me/digifiz](https://t.me/digifiz)
- International channels are in preparation; watch the Telegram mirror for updates.

For hardware sales, installation services, or manual feedback, reach out through the community channels or the official store listings.

## 💖 Support the project

- **PayPal:** `sgw32nc@gmail.com`
- **Crypto (ETH / USDT ERC-20):** `0xeDc17cb23241eACe19DF3617291aa7d2d92E62DC`
- **3D printed accessories and models:** [cgtrader.com/sgw32](https://www.cgtrader.com/sgw32)

## 🧾 License

Documentation sources in this repository are released under the [Creative Commons CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) dedication (see `LICENSE`).

Hardware designs and production files for Digifiz Replica remain proprietary and are distributed separately under dedicated agreements.

## ™️ Trademarks

VDO is a trademark of the Continental Corporation.
The Volkswagen logo, the word “Volkswagen,” vehicle names, and advertising slogans are registered trademarks of Volkswagen AG.
AUDI is a trademark of AUDI AG.
AvtoVAZ is a trademark of AvtoVAZ Concern.

Images or references to these marks are provided solely for identification and installation guidance.  Digifiz Replica dashboards—including Digifiz Audi variants—are aftermarket replacements corresponding to the following OEM references: 191 919 065 B / 191 919 019 B / 87001181 / 191 919 005 B / 191919065B / 191919033LR / 616.051.2001 / 6160512001 / 88481435.
