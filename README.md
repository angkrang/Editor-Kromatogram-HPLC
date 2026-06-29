# Editor Kromatogram HPLC

A small, browser-based editor and viewer for HPLC chromatograms (kromatograms). This repository contains an HTML-based frontend to load, view, annotate, and export chromatogram data.

## Features

- Load chromatogram data from CSV (time,intensity) or simple XY formats
- Zoom and pan the plot
- Add annotations or peak markers
- Export annotated view as PNG and download processed CSV
- Pure HTML/CSS/JavaScript — no build step required

## Getting started

Prerequisites

- A modern web browser (Chrome, Firefox, Edge, Safari)

Run locally

- Option 1: Open `index.html` directly in your browser (double-click the file)
- Option 2 (recommended): Serve the folder over a simple HTTP server to avoid file restrictions

  - Python 3
    ```bash
    python -m http.server 8000
    # then open http://localhost:8000 in your browser
    ```

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

If you'd like I can:
- Add a screenshot to the README (attach an image or point to one in the repo)
- Create a `LICENSE` file with MIT text
- Add usage examples or sample CSV files
