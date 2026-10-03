# Live Telemetry Dashboard :D

A live telemetry ingestion and dashboard package designed for UTSM vehicle and dyno testing. Built with FastAPI. Works with local hardware provisioning for ESP32-WROVER LTE relays.

### Important Components and stuff

**Live Car Dashboard (/live)**: Real-time gauges, charts (last 120 samples), interactive Leaflet GPS mapping, and recent telemetry logs.   

**Dyno Test Dashboard (/dyno):** Compares vehicle electrical input power/energy against dyno output power/energy to compute live and run efficiency.   

**Local Setup Portal (/setup):** Localhost-restricted web UI and automated coordinator to compile and flash WROVER/A7670 relay firmware with Cloudflare tunnel credentials.  

### Run Commands
git switch master
git pull
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt

$env:UTSM_TELEMETRY_API_KEY = "SAME_KEY_USED_BY_THE_WROVER"
python -m uvicorn live_dashboard.app:app --host 0.0.0.0 --port 8000
