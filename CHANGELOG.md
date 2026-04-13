# Changelog

All notable changes to this project will be documented in this file.

---

## [0.5.4] - 2026-04-13

### 🧠 Core (plugin)
- Improved adjacent-channel duplicate detection (±0.1 MHz logic)
- Quality-based station selection (PI / PS / RT / SNR)
- Enhanced pending + settle logging system for more stable DX logs
- Improved force-log behavior before frequency changes

### 📊 Logging
- Added new JSON fields:
  - `adjacentDuplicate`
  - `adjacentReason`
- Improved consistency between TXT / CSV / JSON outputs
- Better handling of weak / partial RDS data

### ⚙️ Architecture
- Extracted settings into `FmArrowTuneSettings`
- Cleaner separation between UI, logic and logging
- Internal cleanup and improved maintainability

### 🌐 Dashboard
- Faster loading (lazy FMScan loading)
- Improved FMScan matching logic
- Better confidence scoring behavior
- Improved frequency mismatch detection
- Reduced initial load delay significantly

### 🐛 Fixes
- Fixed occasional logging inconsistencies during rapid scanning
- Improved handling of unstable frequencies before logging

[0.5.3] - 2026-04-13

Highlights

- Improved station logging
- Smarter PI/PS/RT stabilization before logging
- Better duplicate filtering
- Cleaner log output overall
- Adjacent channel detection
- Detects 100 kHz offset duplicates
- Marks them with ADJ
- Keeps correct frequency as primary
- Dashboard upgrades
- New confidence scoring system
- DX event detection
-  Improved FMScan lookup logic
-  Better UI clarity and station grouping

- Standalone dashboard (NEW)
- Works without Python or server
- Load JSON + CSV files manually
- Perfect for tablets and lightweight setups

Dashboard modes:

1. Server mode

python -m http.server 8000

2. Standalone mode
- Open dashboard.html
- Load log files manually

[0.5.2] - 2026-04-11

### Added
- Optional `dashboard-config.json` for user location
- Support for user-defined coordinates in dashboard
- Nearest TX selection for FMScan matches sharing the same PI code

### Improved
- Dashboard now prefers the closest transmitter when location is configured
- Better handling of multi-transmitter network stations
- More accurate and user-friendly FMScan station display

### Notes
- Dashboard location config is optional
- If no location config is present, dashboard falls back to the first FMScan match

## [0.5.1] - 2026-04-10 - HotFix

### 🛠 Fixed
- Fixed frequency offset logging issue where stations were logged at incorrect frequencies (+0.1 MHz)
- Fixed delayed logging behavior caused by pending queue committing after frequency change
- Ensured station is logged BEFORE frequency step during scan

### ⚡ Improved
- Logging accuracy significantly improved during fast scanning
- Pending queue now works reliably without mixing station/frequency data
- More deterministic DX logging behavior

### 🧪 Notes
- This is a hotfix release for 0.5.0
- Recommended update for all users using auto scan or keyboard tuning

### [0.5.1] - 2026-04-10

#### Fixed
- Prevented frequency/PI mismatch during scanning
- Improved logging stability when switching frequencies
- Added frequency stability validation before committing log entries

#### Improved
- More reliable DX logging during fast scan conditions

## [0.5.0] - 2026-04-10

### 🚀 Added

- Live dashboard support (optional)
  - real-time log viewer
  - last station panel
  - unique PI listing
  - best DX / top stations views
- Confidence score system
  - PI, PS, RT and SNR based scoring
  - classification: high / medium / low confidence
- DX event detection
  - highlights new or strong DX events
- FMScan / FMLIST CSV lookup (optional)
  - manual user-provided data only
  - propagation modes: Tropo / Sporadic E / Meteor Scatter
  - auto mode fallback order: Tropo → ES → MS
- Station settle time (pre-log validation)
  - prevents false early RDS detections
- Extended logging data
  - SNR
  - Peak level
  - Noise floor
  - Stereo / Mono

---

### 🔧 Improved

- Logging reliability significantly improved
  - reduced false PI entries
  - better RDS stabilization handling
- UI clarity in plugin panel
  - improved labels and descriptions
  - added help box with shortcuts
- Dashboard rendering and layout
  - responsive grid
  - improved readability for long RT text
- FMScan matching logic
  - suppression of invalid / suspicious PI codes
  - smarter matching prioritization

---

### 🛠 Fixed

- early incorrect PI logging (e.g. 0001 / 0100 cases)
- dashboard rendering issues on certain layouts
- numeric control alignment glitches in plugin UI
- scan control inconsistencies

---

### ⚠️ Notes

- Dashboard is fully optional and not required for plugin operation
- FMScan data is not bundled due to licensing restrictions
- Users must download FMScan CSV files manually
- FMScan data is used for enrichment only, not as authoritative source

---

## [0.4.0]

### Added
- Initial logging system
- PI-based logging
- basic auto scan

---

## [0.3.0]

### Added
- Arrow key tuning
- basic plugin functionality

---

## [0.1.0]

### Initial release
- Simple keyboard tuning helper
