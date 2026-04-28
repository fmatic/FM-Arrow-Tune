Changelog

All notable changes to this project will be documented in this file.

[0.5.7] - 2026-04-28

🛠️ Stability & UI Update

Added / Improved

* Activity indicator in plugin panel (Idle / Tuning / Scanning / Waiting / Logging)
* Refined plugin panel UI
* Improved PI stability filtering
* Safer default settings
* Reset-to-defaults groundwork for future version

Fixed

* Launcher Exit now closes correctly
* Wrap-around tuning restored
* UI settings update issues fixed after panel refactor
* Removed unstable settings persistence attempt
* Fixed crash caused by System.Web.Extensions dependency

Notes

* Settings persistence postponed to v0.5.8
* Future implementation will be dependency-free and SDR# safe

⸻

[0.5.6] - 2026-04-21

🚀 Major Release – Live DX Platform

This version transforms FM Arrow Tune from a plugin into a complete real-time DX monitoring system.

⸻

🟢 Added – Launcher

* One-click Local Live mode
* Built-in lightweight web server
* Automatic log synchronization
* System tray integration:
    * Left click → open dashboard
    * Right click → menu
* Live status indicator:
    * 🟢 Live
    * 🟡 Partial
    * 🔴 Waiting / error
* Config persistence (launcher-config.json)

⸻

🌐 Added – Live Dashboard System

* Real-time DX monitoring in browser
* Event banner system
* Improved rendering performance
* Multiple operating modes:
    * Manual
    * Local Live (Launcher)
    * Remote Live (server)

⸻

🧠 Added – DX Intelligence

* Band opening detection with scoring
* Opening trend indicator (↑ ↓ →)
* 10-minute activity timeline (sparkline)
* DX burst detection (rapid activity spikes)
* Improved event prioritization logic

⸻

📡 Improved – FMScan Integration

* Better match selection logic
* Distance-based prioritization
* Improved mismatch detection
* Clearer UI presentation

⸻

⚙️ UX Improvements

* Full START_HERE.txt onboarding guide
* Simplified setup for non-technical users
* Clear separation between Local Live and Remote Live
* Improved dashboard clarity and feedback

⸻

🌍 Remote Live

* Dashboard can be hosted on:
    * Raspberry Pi
    * NAS
    * VPS
* Same functionality as Local Live
* Intended for advanced users and shared setups

⸻

⚠️ Notes

* FMScan files must be downloaded manually (FMList policy)
* Launcher does not require Python or external dependencies
* Remote Live does not add new features (deployment only)

⸻

[0.5.5] - 2026-04-14

Added

* First seen / Last seen tracking for stations
* Hit count per PI across the session
* Improved confidence scoring integration in UI

Changed

* Refactored station aggregation logic
* Unified adjacent detection handling across all views
* Improved FMScan match selection logic

Fixed

* Missing closing bracket in renderUniqueStations()
* Broken rendering of unique station cards
* Incorrect hit counts when adjacent filtering enabled
* Occasional UI inconsistencies in Top stations

Notes

* Stable release after extended real-world FM-DX testing

⸻

[0.5.4] - 2026-04-13

🧠 Core (plugin)

* Improved adjacent-channel duplicate detection (±0.1 MHz logic)
* Quality-based station selection (PI / PS / RT / SNR)
* Enhanced pending + settle logging system
* Improved force-log behavior before frequency changes

📊 Logging

* Added new JSON fields:
    * adjacentDuplicate
    * adjacentReason
* Improved consistency between TXT / CSV / JSON outputs
* Better handling of weak / partial RDS data

⚙️ Architecture

* Extracted settings into FmArrowTuneSettings
* Cleaner separation between UI, logic and logging
* Internal cleanup and improved maintainability

🌐 Dashboard

* Faster loading (lazy FMScan loading)
* Improved FMScan matching logic
* Better confidence scoring behavior
* Improved frequency mismatch detection
* Reduced initial load delay significantly

🐛 Fixes

* Fixed occasional logging inconsistencies during rapid scanning
* Improved handling of unstable frequencies before logging

⸻

[0.5.3] - 2026-04-13

Highlights

* Improved station logging
* Smarter PI/PS/RT stabilization before logging
* Better duplicate filtering
* Adjacent channel detection (100 kHz offset)
* Dashboard upgrades:
    * Confidence scoring
    * DX event detection
    * Improved FMScan lookup logic
    * Better UI clarity and grouping

Standalone dashboard (NEW)

* Works without Python or server
* Manual JSON + CSV loading
* Ideal for lightweight setups and tablets

⸻

[0.5.2] - 2026-04-11

Added

* Optional dashboard-config.json for user location
* Support for user-defined coordinates
* Nearest TX selection for FMScan matches

Improved

* Better handling of multi-transmitter networks
* More accurate FMScan display

⸻

[0.5.1] - 2026-04-10

Fixed

* Frequency offset logging issue (+0.1 MHz)
* Delayed logging caused by pending queue
* Ensured logging BEFORE frequency step

Improved

* Logging accuracy during fast scanning
* More deterministic DX logging

⸻

[0.5.0] - 2026-04-10

🚀 Added

* Live dashboard (optional)
* Confidence scoring system
* DX event detection
* FMScan CSV lookup (manual)
* Station settle time validation
* Extended logging:
    * SNR
    * Peak
    * Noise floor
    * Stereo

⚠️ Notes

* Dashboard optional
* FMScan not bundled (manual download required)

⸻

[0.4.0]

* Initial logging system
* PI-based logging
* Basic auto scan

⸻

[0.3.0]

* Arrow key tuning
* Basic plugin functionality

⸻

[0.1.0]

* Initial release
* Simple keyboard tuning helper
    
