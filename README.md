# FM Arrow Tune (DX Data Tool)

![Release](https://img.shields.io/github/v/release/fmatic/FM-Arrow-Tune)

FM Arrow Tune (DX Data Tool)

SDR# plugin for FM DX logging, signal analysis and real-time monitoring — now with optional live dashboard support.

Screenshot

FM Arrow Tune has evolved from a keyboard tuning helper into a full DX Data Tool for SDR#.

Originally built for fast keyboard tuning, it now provides:

Features
	•	keyboard-driven FM tuning and scanning
	•	hold-to-scan and auto scan
	•	PI-first logging
	•	optional Radiotext capture
	•	signal metrics:
	•	SNR
	•	Peak
	•	Noise Floor
	•	Stereo / Mono
	•	TXT / CSV / JSON logging
	•	daily log folders
	•	invalid PI filtering
	•	station settle time to reduce false early RDS logging
	•	optional live dashboard
	•	optional FMScan / FMLIST enrichment
	•	confidence score and DX event detection

This is not just a tuning plugin anymore — it is a compact DX monitoring system.

Quick Start
	1.	Download the latest release
	2.	Extract the ZIP archive
	3.	Copy SDRSharp.Plugin.FmArrowTune into your SDR# plugins folder
	4.	Start SDR#
	5.	Enable FM Arrow Tune

Optional:
	6.	Place dashboard.html into your live log folder to use the dashboard

Keyboard Shortcuts
	•	Left / Right = step tuning
	•	Up / Down = jump tuning
	•	Hold arrow = continuous scan
	•	F8 = auto scan up
	•	F7 = auto scan down
	•	Esc = stop scanning

Dashboard (optional)

Starting with v0.5.0, FM Arrow Tune includes support for a live dashboard.

The dashboard can show:
	•	Last Station
	•	daily logs
	•	unique PI list
	•	Best DX today
	•	Top stations
	•	confidence score
	•	DX event banner
	•	optional FMScan enrichment

The dashboard is fully optional.
The plugin works normally without it.

Example folder structure

live/
  dashboard.html
  FMArrowTune_latest.json
  index.json
  2026-04-10/
    FMArrowTune.json

FMScan / FMLIST support (optional)

FMScan/FMLIST CSV support is optional and user-controlled.

No station database is bundled.
No automatic download is included.

Users can manually place supported CSV files here:

live/
  fmscan/
    fmscan-tropo.csv
    fmscan-es.csv
    fmscan-ms.csv

Auto mode lookup priority:
	1.	Tropo
	2.	Sporadic E
	3.	Meteor Scatter

FMScan data is used as enrichment only, not as absolute truth.

Recommended defaults
	•	Scan speed: 120 ms
	•	Auto dwell: 1200 ms
	•	Station settle time: 1000 ms

Why this plugin?

I often use SDR# remotely from my iPad through Splashtop. Since Splashtop provides virtual arrow keys, I wanted a simple and comfortable way to browse the FM band by tapping left and right.

Over time, the project grew into a more complete DX workflow:
scan → detect → log → analyze.

Never stop the madness!

Status

Current release: v0.5.0

Highlights in v0.5.0
	•	new optional live dashboard
	•	signal metrics logging
	•	station settle time
	•	improved invalid PI filtering
	•	confidence score
	•	DX event detection
	•	optional FMScan / FMLIST enrichment

License

MIT
:::
