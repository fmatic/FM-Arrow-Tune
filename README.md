# FM Arrow Tune

![Release](https://img.shields.io/github/v/release/fmatic/FM-Arrow-Tune)

SDR# plugin for convenient FM band browsing using arrow keys.

## Screenshot

![FM Arrow Tune](docs/screenshot.png)

# FM Arrow Tune

FM Arrow Tune is an SDR# plugin for convenient FM band browsing with keyboard arrow keys.

It was originally built for remote listening via Splashtop on iPad, where the virtual arrow keys make tuning especially comfortable.

## Features

- Left / Right arrow tuning
- Adjustable step size
- Optional WFM-only mode
- Optional FM band clamp (87.5–108.0 MHz)
- Optional wrap-around tuning
- Optional Ctrl + Arrow requirement

## Why this plugin?

I often use SDR# remotely from my iPad through Splashtop. Since Splashtop provides virtual arrow keys, I wanted a simple and comfortable way to browse the FM band by tapping left and right.

## Installation

1. Download the latest release from the Releases page.
2. Extract the ZIP archive.
3. Copy `SDRSharp.Plugin.FmArrowTune.dll` to your SDR# plugins folder.
4. Add the plugin entry to `Plugins.xml`.
5. Start SDR#

## Usage

•	Left / Right: tune down / up by the selected step
	•	Only in WFM mode: restricts operation to WFM
	•	Clamp to 87.5–108.0 MHz: prevents tuning outside the FM broadcast band
	•	Wrap 108.0 -> 87.5 / 87.5 -> 108.0: wraps tuning around the FM band edges
	•	Require Ctrl + Arrow: prevents accidental tuning when using arrow keys for other purposes
	•	Step (kHz): sets the tuning step
<add key="FmArrowTune" value="SDRSharp.FmArrowTune.FmArrowTunePlugin, SDRSharp.Plugin.FmArrowTune" />
