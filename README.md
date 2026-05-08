# Bad Habbit Tracker

A privacy-first, single-file web app for logging coping behaviors.

## Overview

This app is built as one `index.html` file (no backend required). It runs fully in the browser and stores data locally on your device.

## Key Features

- Multi-language UI: English, Dutch, Spanish
- Log events with:
  - Date/time
  - One or multiple mechanisms per event
  - Trigger
  - Intensity (0-10)
  - Optional note
- History view with filters and delete
- Statistics dashboard with:
  - Summary cards
  - Activity heatmap
  - Time-of-day distribution
  - Trend chart
  - Per-mechanism breakdown
- Configurable Focus Tracker (choose the mechanisms to track)
- Mechanism list editor in Settings
- Import/Export JSON backups
- Export CSV

## Data & Privacy

- Data is stored in browser `localStorage`
- No cloud sync by default
- No server/database is required
- Your data stays on the device/browser profile unless you export it

## Storage Keys

- `records` (entries)
- `badhabbit_settings_v1` (language, mechanisms, focus tracker settings)
- `goals` (goal tracking)

Legacy keys are migrated automatically when possible.

## Entry Model

Each event can contain multiple mechanisms in one record:

- `id`
- `dateTime`
- `mechanisms` (array)
- `trigger`
- `intensity`
- `note`
- `timestamp`

The app also keeps compatibility fields for older backups.

## Import/Export

### JSON export
Exports all entries plus settings, including:
- custom mechanisms
- focus tracker selection
- language

### JSON import
Supports multiple backup structures and tries to normalize old/new formats.
Import replaces current entries.

### CSV export
Exports a flat table for spreadsheet use.

## Running the App

Open `index.html` in any modern browser:

- macOS: double-click or open in Safari/Chrome
- iPhone/iPad: host it (for example GitHub Pages / Cloudflare Pages) and open via URL

## Deployment

Because it is a single static HTML file, you can deploy to any static host:

- GitHub Pages
- Cloudflare Pages
- Netlify
- Vercel (static)

## Notes

- This project currently uses only `index.html`.
- If you clear browser storage, local data is removed unless previously exported.
