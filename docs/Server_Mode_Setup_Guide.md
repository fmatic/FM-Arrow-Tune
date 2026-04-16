📡 FM Arrow Tune – Server Mode Setup Guide

🧭 What is Server Mode?

Server mode allows the dashboard to update automatically in real-time without manually loading files.

Instead of selecting JSON files, the dashboard reads them directly from a web server.

⸻

⚙️ Requirements

To use Server mode, you need:

* A local or remote web server
* Access to your SDR# log files:
    * FMArrowTune_latest.json
    * YYYY-MM-DD/FMArrowTune.json
* A way to automatically copy/update these files

⸻

🏗️ Basic Architecture

```text
SDR# (FM Arrow Tune plugin)
        ↓
Writes JSON logs
        ↓
Auto-copy script (optional but recommended)
        ↓
Web server folder
        ↓
Dashboard (browser)
```

💻 Option 1: Local Server (Windows – easiest)

1. Create a folder example: C:\fm-dashboard\
   Place inside:

* dashboard.html
* FMArrowTune_latest.json
* /YYYY-MM-DD/FMArrowTune.json

2. Start a simple web server

Python (recommended)

cd C:\fm-dashboard
python -m http.server 8000

Then open: http://localhost:8000/dashboard.html

3. Auto-copy logs (optional but important)

Create a .bat script:

```bat

@echo off
set SRC=C:\SDRSharp\Logs
set DEST=C:\fm-dashboard

xcopy "%SRC%\FMArrowTune_latest.json" "%DEST%\" /Y
xcopy "%SRC%\%DATE:~6,4%-%DATE:~3,2%-%DATE:~0,2%\FMArrowTune.json" "%DEST%\%DATE:~6,4%-%DATE:~3,2%-%DATE:~0,2%\" /Y
```
Run it periodically (Task Scheduler).

🍓 Option 2: Raspberry Pi / Linux / NAS

1. Install web server
   ```bash
   sudo apt update
   sudo apt install nginx
   ```

2. Place files

Example: /var/www/html/fm/

Put:

* dashboard.html
* logs

⸻

3. Copy logs automatically

Example script:
```bash
#!/bin/bash

SRC="/home/user/SDRSharp/Logs"
DEST="/var/www/html/fm"

cp "$SRC/FMArrowTune_latest.json" "$DEST/"

TODAY=$(date -u +"%Y-%m-%d")
mkdir -p "$DEST/$TODAY"
cp "$SRC/$TODAY/FMArrowTune.json" "$DEST/$TODAY/"
```
Run via cron:

```bash
* * * * * /home/user/copy_logs.sh
```

☁️ Option 3: Remote Server / VPS

Same idea as Linux, but:

* Upload logs via:
    * scp
    * rsync
    * FTP
* Run sync script on your SDR machine

⸻

📊 FMScan (optional but recommended)

Download with your FMList account from fmscan.org
.CSV format, semicolon
Place CSV files in: /fmscan/

Examples:

* fmscan-tropo.csv
* fmscan-es.csv
* fmscan-ms.csv

⸻

📍 User location (for distance & DX Radar)

Create dashboard-config.json:

```JSON
{
  "userLocation": {
    "name": "Jyväskylä",
    "lat": 62.2426,
    "lon": 25.7473
  }
}
```
🚨 Important Notes

* Server mode will NOT work properly without HTTP serving
    → opening dashboard.html directly (file://) is not enough
* Logs must be:
    * continuously updated
    * accessible via URL
* If unsure → use Standalone mode

⸻

✅ When Server Mode is working correctly

You should see:

* Live updates every ~10 seconds
* Event banner reacting instantly
* Band Opening + Timeline updating
* DX Radar reacting in real time

⸻

💡 Recommended Setup

For most users:

👉 Best combo

* Windows + Python server
* Simple auto-copy script

👉 Advanced

* Raspberry Pi / NAS always running
* Fully automatic logging + dashboard

⸻

🔥 Bonus: Why Server Mode is worth it

* Real-time DX detection
* DX Burst detection becomes meaningful
* Band Opening analysis is continuous
* No manual interaction needed
