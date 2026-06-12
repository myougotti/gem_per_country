# GEM per Country

This repository hosts the **GEM per Country Power Tracker** web application. The tool allows users to preview and download GeoJSON data for global power plants filtered by country and power plant status. The tool also allows exporting a list of steel and iron plants which identifies large loads on the grid as curated by GEM, the same filters apply.

**Live app:** https://myougotti.github.io/gem_per_country/

## Overview

- **Dataset Picker:** Choose one of two datasets, the Power plants dataset or the Iron and Steel dataset that shows locations of large loads connected to the grid.
- **Country Filtering:** Input a country name to display power plant data for that region
- **Pagination:** The data preview is paginated to show 2000 rows per page.
- **GeoJSON Download:** Export your filtered data as a GeoJSON file.

## Data Source

The power plant data is sourced from [Global Energy Monitor](https://globalenergymonitor.org/) and is made available under the [Creative Commons Attribution 4.0 License](https://globalenergymonitor.org/creative-commons-public-license/).

The repository hosts snapshots of two GEM datasets, which the app loads directly:

- `Global-Integrated-Power-February-2025-update-II.xlsx` — Global Integrated Power Tracker
- `Global-Iron-and-Steel-Tracker-March-2025-V1.xlsx` — Global Iron and Steel Tracker (plant-level data)

### Updating the data

GEM download URLs are version-pinned, so the data is refreshed manually: run the **Update GEM data files** workflow (Actions tab) and provide the download URLs of the new release. The workflow validates that the downloads are real `.xlsx` files before committing them. If column names changed in the new release, `index.html` must be updated to match.

## Getting Started

### Prerequisites

No special dependencies are required for running this application locally.

### Running Locally

1. **Clone the repository:**

   ```bash
   git clone git@github.com:myougotti/gem_per_country.git
   cd gem_per_country
   ```

2. **Open the app:**

   Open `index.html` in your browser, or serve the folder with any static file server, e.g.:

   ```bash
   python -m http.server 8000
   ```

   and visit http://localhost:8000.

The app fetches the Excel datasets from this repository's `main` branch, so an internet connection is required even when running locally.

## Deployment

The app is deployed with GitHub Pages from the root of the `main` branch. Any change pushed to `main` goes live automatically.
