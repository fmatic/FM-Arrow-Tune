# FM Arrow Tune

![Release](https://img.shields.io/github/v/release/fmatic/FM-Arrow-Tune)

SDR# plugin for convenient FM band browsing using arrow keys.

## Screenshot

![FM Arrow Tune](docs/screenshot.png)

# FM Arrow Tune

FM Arrow Tune is an SDR# plugin for convenient FM band browsing with keyboard arrow keys.

It was originally built for remote listening via Splashtop on iPad, where the virtual arrow keys make tuning especially comfortable.

## Features

- Left / Right arrow tuning (step)
- Up / Down band jumps
- Adjustable step and jump sizes
- Optional WFM-only mode
- Band clamp and wrap-around
- Optional Ctrl + Arrow requirement


## Tip

Hold arrow keys to scan through the band. Adjust scan speed in the plugin settings.

## Why this plugin?

I often use SDR# remotely from my iPad through Splashtop. Since Splashtop provides virtual arrow keys, I wanted a simple and comfortable way to browse the FM band by tapping left and right.

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
