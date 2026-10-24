# 🌐 TrucklineMP Server Player Tracker

A lightweight, automated server-population tracking dashboard for the [TrucklineMP](https://trucklinemp.com) multiplayer modification. This website updates in real-time and builds a historical timeline of player counts completely free of hosting costs.

## 🚀 Live Demo
The tracking website is hosted live using GitHub Pages:
👉 **`https://<YOUR-GITHUB-USERNAME>.github.io/trucklinemp-tracker/`**

---

## 🛠️ How It Works
This project uses a serverless architecture split into two synchronized parts:

1. **The Cloud Scraper (`.github/workflows/update-data.yml`)**
   * An automated background worker powered by **GitHub Actions**.
   * Wakes up every 10 minutes, 24/7.
   * Pulls actual, live player numbers directly from the official TrucklineMP API.
   * Appends the timestamped data directly into a local storage file (`history.json`).

2. **The Frontend Dashboard (`index.html`)**
   * A responsive, dark-themed user interface.
   * Hosted completely free via **GitHub Pages**.
   * Uses **Chart.js** to parse the logs inside `history.json` and render a smooth timeline graph showing peak traffic trends.

---

## 📁 Repository Architecture
* `index.html` — The visual website interface and graphing engine.
* `history.json` — The continuous dataset file where your actual player logs are stored.
* `.github/workflows/update-data.yml` — The automated workflow file that powers the live data collection.

---

## 🔧 Setup & Customisation
If you want to tweak or adjust the time frame of the logging engine, you can edit the `.github/workflows/update-data.yml` file:
* **Change frequency:** Modify the `cron` line (e.g., `*/5 * * * *` will scrape every 5 minutes instead of 10).
* **Track different servers:** Adjust the `jq` JSON mapping filters inside the script step to grab individual server names.

---

*Disclaimer: This is an independent, community-driven project and is not officially affiliated with TrucklineMP.*
