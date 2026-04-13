# FM Arrow Tune (DX Data Tool)

![Release](https://img.shields.io/github/v/release/fmatic/FM-Arrow-Tune)

SDR# plugin for FM DX logging, signal analysis and real-time monitoring — now with optional live dashboard support.

---

## 📸 Screenshot

![FM Arrow Tune Dashboard](docs/screenshot.png)

---
🌐 **Live Demo**  
Experience the dashboard in action:  
👉 https://vadelma.online/live/dashboard.html

> ⚠️ Live demo uses real-time data — content may change continuously.

## 🚀 Features

- keyboard-driven FM tuning and scanning
- hold-to-scan and auto scan
- PI-first logging
- optional Radiotext capture
- signal metrics:
  - SNR
  - Peak
  - Noise Floor
  - Stereo / Mono
- TXT / CSV / JSON logging
- daily log folders
- invalid PI filtering
- station settle time (prevents early false RDS logging)
- optional live dashboard
- optional FMScan / FMLIST enrichment
- confidence score
- DX event detection

👉 This is no longer just a tuning helper — it's a compact DX analysis tool.

---

## ⚡ Quick Start

1. Download the latest release  
2. Extract ZIP  
3. Copy plugin into SDR# Plugins folder  
4. Start SDR#  
5. Enable **FM Arrow Tune**

Optional:

6. Open `dashboard.html` to view logs visually
7. Dashboard requires HTTP server

---

## ⌨️ Keyboard Shortcuts

- Left / Right = step tuning  
- Up / Down = jump tuning  
- Hold arrow = continuous scan  
- F8 = auto scan up  
- F7 = auto scan down  
- Esc = stop scanning  

---

## 📊 Dashboard (optional)

Starting with **v0.5.0**, FM Arrow Tune includes a live dashboard.

### Features

- Last Station panel
- daily log viewer
- unique PI list
- Best DX today
- Top stations
- confidence score
- DX event banner
- FMScan lookup (optional)

👉 The dashboard is **fully optional**  
👉 The plugin works normally without it

---

## 📁 Folder Structure

```text
live/
  dashboard.html
  FMArrowTune_latest.json
  index.json
  2026-04-10/
    FMArrowTune.json
```

📡 FMScan / FMLIST Support (optional)

No station database is bundled.

Users can manually download CSV files from FMScan:
	•	https://fmscan.org/

Place them here:

``` text
live/
  fmscan/
    fmscan-tropo.csv
    fmscan-es.csv
    fmscan-ms.csv
```

Lookup priority (Auto mode)
- Tropo
- Sporadic E
- Meteor Scatter

👉 FMScan data is used as enrichment only, not as absolute truth.

## Optional dashboard location config

The dashboard can optionally use a small JSON config file to improve FMScan matching.
When multiple FMScan entries share the same PI code, the dashboard can prefer the **nearest transmitter** based on user-defined coordinates.
If no config file is present, the dashboard falls back to the first available FMScan match.

### File
Create this file next to `dashboard.html`:

```text
dashboard-config.json

{
  "userLocation": {
    "name": "Jyväskylä",
    "lat": 62.2426,
    "lon": 25.7473
  }
}
```

Behavior
	•	If coordinates are configured:
	•	dashboard selects the nearest matching TX site
	•	If no coordinates are configured:
	•	dashboard uses the default FMScan fallback match

This is especially useful for stations and networks where the same PI code is used by multiple transmitters.

⸻

⚙️ Recommended Defaults
 - Scan speed: 120 ms
 - Auto dwell: 1200 ms
 - Station settle time: 1000 ms

⸻

🧠 How it evolved

Originally built for simple keyboard tuning (especially for remote SDR use via iPad + Splashtop),
FM Arrow Tune has grown into a full DX workflow tool:

scan → detect → validate → log → analyze

⸻

📦 Release

🚀 Version 0.5.3 highlights
	•	Adjacent channel detection
	•	Improved logging accuracy
	•	Confidence scoring system
	•	Standalone dashboard mode


🆕 0.5.2 - 2026-04-11

Added

- Optional `dashboard-config.json` for user location
- Support for user-defined coordinates in dashboard
- Nearest TX selection for FMScan matches sharing the same PI code

Improved

- Dashboard now prefers the closest transmitter when location is configured
- Better handling of multi-transmitter network stations
- More accurate and user-friendly FMScan station display

Notes

- Dashboard location config is optional
- If no location config is present, dashboard falls back to the first FMScan match

🆕 v0.5.1 – Logging stability fix

This update improves DX logging accuracy during scanning.
	•	Fixed frequency / PI mismatch issue
	•	Prevented RDS carry-over between frequencies
	•	Added frequency stability validation before logging

➡️ Result: cleaner logs and more reliable DX data

---

Version: v0.5.0

Highlights
- 🔥 Live dashboard
- 📊 Signal metrics logging
- ⏱️ Station settle time
- 🧠 Confidence scoring
- 📡 DX event detection
- 🌍 FMScan enrichment (optional)

⸻

📜 License

MIT
