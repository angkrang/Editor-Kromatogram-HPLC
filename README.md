# Editor Kromatogram HPLC

A small, browser-based editor and viewer for HPLC chromatograms (kromatograms). This repository contains an HTML-based frontend to load, view, annotate, and export chromatogram data.

## Features

- Load chromatogram data from CSV (time,intensity) or simple XY formats
- Zoom and pan the plot
- Add annotations or peak markers
- Export annotated view as PNG and download processed CSV
- Pure HTML/CSS/JavaScript — no build step required

## Getting started (improved)

This section provides step-by-step, practical instructions to run the app locally, load data, and troubleshoot common issues.

Prerequisites

- A modern web browser (Chrome, Firefox, Edge, Safari)
- Optional: VS Code (with Live Server extension) or Node.js/Python if you prefer serving files via a local HTTP server

Repository layout (important files)

- `index.html` — the main app entry (open this in your browser)
- `css/` — styles (if present)
- `js/` or `app.js` — application logic (if present)
- `samples/` — example CSV files (if present)

Run locally (recommended approaches)

1. Open the app directly
   - Double-click `index.html` to open it in your browser. Note: some browsers restrict reading local files from the file:// protocol. If the app cannot read local CSV files this way, use one of the server options below.

2. Serve via a simple HTTP server (recommended)

- Python 3 (works on Windows/macOS/Linux)

  ```bash
  # run this from the repository root
  python -m http.server 8000
  # then open http://localhost:8000 in your browser
  ```

- Node (http-server)

  ```bash
  # install once or run with npx
  npx http-server -p 8000
  # open http://127.0.0.1:8000
  ```

- VS Code Live Server

  - Open the repository folder in VS Code
  - Install the Live Server extension
  - Right-click `index.html` -> "Open with Live Server"

Deploy to GitHub Pages (quick)

- Option A (main branch /docs): put build (or files) into the `docs/` folder on `main` and enable Pages in repository settings.
- Option B (gh-pages): push the repository to a `gh-pages` branch and enable Pages.

Loading data

- Supported input: CSV with two numeric columns (time/retention_time and intensity). A header row is allowed but not required.
- Example CSV (comma-separated):

  time,intensity
  0.00,0.12
  0.10,0.35
  0.20,0.80

- How to open files in the app:
  - Use the file menu / "Open" button (if present).
  - Drag and drop a CSV file onto the app window.
  - If using a server, you can also provide a sample CSV URL and the app will fetch it.

User interactions (typical)

- Zoom: mouse wheel or pinch-to-zoom on touch devices
- Pan: click-and-drag (or two-finger drag on touch)
- Add annotation/peak marker: click (or tap) on the plot — the UI will prompt for an optional label
- Export: use the Export or Download buttons to save current view as PNG or download the processed CSV

Common issues & troubleshooting

- Blank screen or file won't load
  - If the app cannot read files when opened via file://, run a local HTTP server (see above).
  - Open the browser Developer Tools (F12) and check the Console for errors.

- CSV not parsed correctly
  - Ensure the file uses comma (,) or the delimiter supported by the app. Remove extra columns or non-numeric rows.
  - Confirm numeric format (use `.` as decimal separator) and no thousands separators.

- Browser blocks fetching remote CSV
  - If fetching a CSV from a remote URL, CORS may block access. Serve the CSV from the same origin (or enable CORS on the server).

Tips for development

- Open Developer Tools (F12) to inspect console logs and network requests while testing
- Use small sample CSV files while debugging to speed up load/parse times

Usage

1. Open the app in your browser.
2. Click "Open" or drag-and-drop a CSV file containing two columns: time (or retention time) and intensity (signal).
3. Use mouse/touch to zoom and pan the plot.
4. Click on the plot to add an annotation/peak marker.
5. Export the current view as PNG or download the annotated CSV.

File format

- CSV should contain two numeric columns, e.g.:

  time,intensity
  0.00,0.12
  0.10,0.35
  0.20,0.80

Contributing

Contributions are welcome. Please:

1. Open an issue to discuss major changes or bugs.
2. Fork the repository and create a pull request with a clear description of your changes.

Code style

- Keep changes small and focused
- Include comments for non-obvious logic

License

This project is provided under the MIT License. See `LICENSE` for details (or let me know if you want a different license).

Author

- angkrang — https://github.com/angkrang

Acknowledgements

- Built with plain HTML/CSS/JavaScript. If this project uses any third-party libraries (e.g., charting libraries), mention them here with links.

---
