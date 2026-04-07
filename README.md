# FM Arrow Tune (DX Data Tool)

![Release](https://img.shields.io/github/v/release/fmatic/FM-Arrow-Tune)

SDR# plugin for FM DX logging, signal analysis and real-time monitoring with dashboard support.

## Screenshot

![FM Arrow Tune](docs/screenshot.png)

FM Arrow Tune has evolved into a full DX Data Tool for SDR#.

Originally built for fast keyboard tuning, it now provides:

## Features

- PI-first logging (even before PS/RDS completes)
- Radiotext capture (optional)
- Signal metrics (SNR, Peak, Noise Floor)
- Stereo / Mono detection
- Smart auto-scan with pause/stop logic
- CSV + JSON logging
- Daily log folders
- Live dashboard (local or hosted)

This is not just a tuning plugin anymore — it's a DX monitoring system. 

## Tip

Hold arrow keys to scan through the band. Adjust scan speed in the plugin settings.

## Why this plugin?

I often use SDR# remotely from my iPad through Splashtop. Since Splashtop provides virtual arrow keys, I wanted a simple and comfortable way to browse the FM band by tapping left and right.

Never stop the madness!

## Installation

1. Download the latest release from the Releases page.
2. Extract the ZIP archive.
3. Copy `SDRSharp.Plugin.FmArrowTune` folder to your SDR# plugins folder.
4. Start SDR#

## Status

Current release: **v0.3.0**
- Hold-to-scan (press and hold arrow keys)
- Adjustable scan speed (ms)
- Improved tuning responsiveness



v0.2.0
- Added Up/Down band jumps
- Improved band navigation workflow

v0.1.0 This is the first public version. More features may follow, such as:
- Up / Down band jumps
- Hold-to-scan
- Faster navigation options



## Roadmap

This project is actively evolving. Planned features are listed below.

### v0.2.0 (Released)
- [x] Up / Down arrow band jumps (configurable)
- [x] Preparation for multi-band support

### v0.3.0 (Released)
- [x] Hold-to-scan (press and hold Left/Right)
- [x] Adjustable scan speed

### v0.4.0
- Scan + logging
- Save scan results to TXT (frequency, PI, station)

### v0.5.0
- Multi-band support (AM, FM, VHF/UHF, LPD)
- Band-aware step sizes

### v0.6.0
- Advanced logging and grouping
- Station grouping by PI code (multi-frequency detection)

### v1.0.0
- Stable, full-featured release
- Polished UI and configuration
