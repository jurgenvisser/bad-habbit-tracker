# Bad Habbit Tracker

A privacy-first, single-file web app for logging coping behaviors and reviewing patterns over time.

## Tech Stack

- Single static file: `index.html`
- No backend
- No framework/build step required
- Works in modern browsers

## Core Functionality

### 1. Multi-step event logging
Create a new event with:
- Date and time
- One **or multiple** mechanisms in the same event
- Trigger text
- Intensity (0-10)
- Optional context note

Important: if you select 3 mechanisms, the app stores **one event** containing a mechanisms array (not 3 separate log rows).

### 2. Mechanism management
In Settings you can:
- Edit the mechanism list (one per line)
- Use emoji + name format
- Reset to default mechanisms

### 3. Focus Tracker (manual selection)
In Settings you can choose:
- Primary mechanism
- Secondary mechanism (optional)

The Focus Tracker card on the Stats page uses exactly these selections.

### 4. History
- Timeline of logged events
- Filter chips by mechanism
- Combined mechanism display in one row (for multi-mechanism events)
- Delete individual events

### 5. Stats dashboard
- Time-range filters (7/30/90/all)
- Summary metrics:
  - total entries
  - average intensity
  - active days
  - entries/day
  - most frequent mechanism
- Focus Tracker card
- Activity heatmap
- Time-of-day distribution
- Trend chart over time
- Mechanism breakdown cards with detail views
- Streak banner

### 6. Goals
- Add mechanism-specific goals
- Time-unit support (hours/days/weeks)
- Visual goal progress (rings and detail card)

### 7. Language support
UI translations included for:
- English (EN)
- Dutch (NL)
- Spanish (ES)

### 8. Import/Export
#### JSON export
Exports:
- all entries
- app settings
- mechanisms
- focus tracker configuration
- language

#### JSON import
- Replaces current entries
- Restores mechanisms and focus settings from backup when available
- Supports multiple legacy/new structures and normalizes them

#### CSV export
- Flat spreadsheet-friendly output

## Data Model

## Event record (current format)
- `id`
- `dateTime`
- `mechanisms`: array of objects
  - `name`
  - `emoji`
  - `unit`
  - `amount`
- `trigger`
- `intensity`
- `note`
- `timestamp`

Compatibility fields are still handled for older backups.

## Settings snapshot
- `lang`
- `mechanisms`
- `focusSubs`
- `focusTracker.mechanisms` (compatibility path)

## Local Storage

The app stores data in browser `localStorage`:
- `records`
- `badhabbit_settings_v1`
- `goals`

Legacy key migration is included where possible.

## Privacy

- All data stays local in the browser profile by default
- No server-side storage
- No external database
- If local browser storage is cleared, data is lost unless exported

## Run Locally

Open `index.html` directly in a browser.

Examples:
- Double-click `index.html`
- Drag file into Safari/Chrome
- Serve as static file via any local/static host

## Deployment

This app can be hosted on any static hosting provider:
- GitHub Pages
- Cloudflare Pages
- Netlify
- Vercel (static)

## Repository Structure

- `index.html`: complete app (UI, logic, storage, import/export)
- `README.md`: project documentation

