---
name: earthchem_synthesis_search
title: PetDB 2.0 (Earthchem Synthesis)
date: 09/10/2025
layout: default
order: 11
---

### PetDB 2.0 (EarthChem Synthesis) Interface Guide

![PetDB Synthesis](https://img.shields.io/badge/PetDB Search-Docs-green)

#### Overview

The **EarthChem PetDB 2.0 Synthesis Interface** allows researchers to explore, filter, and export global geochemical data. It combines an interactive map with a powerful filtering system and customizable export options for metadata and output variables.

---

#### 1. Getting Started

##### Access

Visit the staging or production site:

-   **Production:** [https://www.earthchem.org/petdb](https://www.earthchem.org/petdb)

##### Initial View

Upon loading, you’ll see:

-   A **3D globe map** displaying all samples.
-   A **filter panel** on the left.
-   A **status bar** below the map showing the number of samples currently displayed.
-   A **view toggle** below the map/table with option to toggle between map and datatable.

---

#### 2. Filtering Data

##### Step 1: Select From Top Level Search Section

1. Option **Analytical Features**.
2. Option **Sample Features**.
3. Option **Additional Features**

##### Step 2: Choose Sample Features

1. Once top level expanded, select a filter to search by.
2. Example: **Sample Features** > **Tectonic Setting** > select **Abyssal Hill**.
3. The dataset reduces (e.g., from ~100k to ~174 samples).

##### Step 3: Optional – Map Polygon Selection

-   On **Map View** a Draw Polygon tool allows drawing polygons to spatially filter samples.
-   Drawing a polygon further reduces the previous filter.

---

#### 3. Exploring the Map

-   **Crosshair icon** – Toggles visibility of sample points.
-   **Earth icon** – Switches to global projection.
-   **North icon** – Switches to North Pole projection.
-   **South icon** – Switches to South Pole projection.
-   **Zoom controls** – Adjust zoom level.
-   **Drag and rotate** – Explore regions interactively.

---

#### 4. Viewing Data in Table Form

1. Click the **Table icon** in the bottom toolbar.
2. The **Table View** displays sample records with columns such as:
    - `Sample`, `Citation`, `Sample Type`, `Analyzed Material`, `Longitude/Latitude`, etc.
3. A summary row shows the dataset size (e.g., 602 samples) and includes:
    - **Preview Export** – Review dataset before exporting.
    - **Gear icon (Data Options)** – Customize metadata and outputs.

---

#### 5. Data Options

The **Data Options** modal has three tabs:

##### Metadata

-   Choose which descriptive metadata fields to include (e.g., `Sample ID`, `Material`, `Location`).

##### Output Variables

-   Select between:
    -   **Default Items** standard set of 68 variables.
    -   **All Available** dependent on the current search, all variables available.
    -   **Custom Selection** of geochemical variables (user's choice)

##### Export Summary

-   Displays current filters, row count, and output format (CSV/JSON/EXCEL).
-   Includes the **Export Results**, **Citation Information** and **User Feedback**.

---

#### 6. Export Workflow

1. Click the **gear icon** → choose **Metadata** or **Output Variables**.
2. Navigate to the **Export Summary** tab.
3. Click **Export Results**.
4. Read and scroll through the **Terms & Conditions** modal.
5. Click **Accept Terms**.
6. Fill in:
    - **Email**
    - **Usage Type:**
    - (Optional) Check “Join EarthChem Mailing List.”
7. Click **Begin Download** to export.
8. You’ll receive a confirmation email with your dataset (in CSV/ZIP format) otherwise the export will be complete in the same browser window (< 10k rows).

---
