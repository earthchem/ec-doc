---
name: petdb_api
title: PetDB API
date: 09/10/2025
layout: default
order: 1
---

## PetDB API

![v4.5.0](https://img.shields.io/badge/v4.5.0.-release-blue)

### Core Overview

The **PetDB API v4** provides a unified interface for querying, aggregating, and exporting geochemical data.  
Built in **Node.js + Express**, the API connects to **AWS DynamoDB** for task management, **OpenSearch** for dataset querying, and **AWS S3** for export storage.

All routes are designed for high performance, modular scalability, and error resilience to be used by **EarthChem Synthesis**.

The **PetDB API v4** implementation now includes **35 fully realized production features**, delivering:

-   Real-time OpenSearch aggregations
-   Secure export generation via S3 and DynamoDB
-   Geospatial filtering and location services
-   Advanced citation and sample linking
-   Logging and audit trail across all queries

### Functional Features

1. **Unified Vocabulary Endpoints**

    - Provides hierarchical and flat data aggregations for geochemical vocabularies.
    - Implemented `GET /v4/*` endpoints for **geoFeatures**, **taxons**, **variables**, **analysisTypes**, **authors**, and more.
    - Supports nested composite aggregations sourced from **OpenSearch** composite queries.
    - Delivers structured, normalized responses to the client in real time.

2. **GeoFeature Hierarchies**

    - `GET /v4/geoFeatures` returns **type → name** relationships for geological features.
    - Utilizes composite aggregations from OpenSearch fields.

3. **Taxonomy Aggregations**

    - `GET /v4/taxons` exposes hierarchical **sample taxonomy data** (parent/child).
    - Dynamically builds aggregations from `sampleTaxons`.
    - Fully normalized across all available datasets.

4. **Expedition and Author Retrieval**

    - `GET /v4/expeditions` returns expedition names grouped by dataset origin.
    - `GET /v4/authors` lists citation authors (familyName only) for publication filtering.
    - Designed for low-latency, pre-aggregated access to metadata.

5. **Citation Information**

    - Endpoints for **citationTitles**, **publicationYears**, and **journals** allow fast metadata retrieval.
    - Optimized for **keyword search and aggregation filtering**.
    - Supports pagination and client-side auto-suggestions.

6. **Variable and Analysis Type Hierarchies**

    - `GET /v4/variables` and `GET /v4/analysisTypes` support multi-level relationships.
    - Example: AnalysisType → MineralName → MaterialName → InclusionType.
    - Aggregations sourced from nested OpenSearch documents.

7. **Laboratory and Data Source Endpoints**

    - Provides non-hierarchical aggregation for **laboratories** and **dataSources**.
    - Useful for filtering data provenance and processing origins.

8. **Sample Name Retrieval**

    - `GET /v4/sampleNames` returns flattened sample name lists from OpenSearch.
    - Used for cross-index matching and display filtering on UI.

9. **Multi-Vocabulary Suggestions**
    - `GET /v4/` endpoint aggregates **top 10 vocabulary suggestions** across all vocabularies simultaneously.
    - Useful for search auto-complete and smart query prediction.

---

### Citation System Features

11. **Comprehensive Citation Retrieval**

    -   `GET /v4/citations/:id` retrieves complete citation records (authors, journals, year).
    -   Data sourced from OpenSearch and structured in normalized JSON.
    -   Implements caching layer for high-frequency queries.

12. **Citation-Sample Linking**

    -   `GET /v4/citations/:id/samples` connects citations to related sample records.
    -   Enables dataset traceability between literature and sample evidence.

13. **Citation-Method Association**

    -   `GET /v4/citations/:id/methods` provides all analytical methods used in the citation context.
    -   Supports data provenance tracking and analytical reproducibility.

14. **Searchable Citations Endpoint**
    -   `GET /v4/citations?{search}` supports filtered search queries using OpenSearch.
    -   Integrates fuzzy matching and partial search on multiple fields.
    -   Handles pagination and size constraints for performance.

---

### Sample Data System

15. **Sample Metadata Retrieval**

    -   `GET /v4/samples/:id` returns all sample information, fully normalized.
    -   `GET /v4/samples/:id/metadata` exposes associated metadata fields for analysis and export.
    -   OpenSearch scroll queries used for large sample retrievals.

---

### Export System

16. **Export Submission Endpoint**

    -   `GET /v4/exports/submit?{search}` submits export requests to the system.
    -   Adds entries into **DynamoDB** with metadata: timestamp, user email, and query context.
    -   Supports multiple export file types (CSV/JSON).

17. **Export Task Status**

    -   `GET /v4/exports/:taskId` retrieves live status of an export (Pending, Processing, Failed, Succeeded).
    -   Dynamically updated by background processors through DynamoDB streams.

18. **Export Cancellation**
    -   `GET /v4/exports/cancel/:taskId` cancels a pending export task.
    -   Triggers update in DynamoDB to set `status=CANCELLED`.
    -   Sends optional cancellation email notification to requester.

---

### Metrics & Monitoring

19. **System Metrics Endpoint**

    -   `GET /v4/metrics` returns dataset-wide statistics (sample counts, citations, data points).
    -   Optimized for API dashboards and usage visualization.

20. **Export Table Metrics**
    -   `GET /v4/metrics/exports/:taskStatus` lists all exports filtered by task status.
    -   Includes email, IP, export purpose, file location, timestamps, and status history.

---

### Location Services

21. **Location Query Endpoints**

    -   `GET /v4/locations?{search}` returns clustered sample coordinates.
    -   Optimized for use with mapping clients (Mapbox/MapLibre).
    -   Results returned as aggregated cluster GeoJSON.

22. **Sample Location Metadata**

    -   `GET /v4/locations/samples?{search}` retrieves sample metadata including lat/lon and sample IDs.
    -   Supports UI rendering of marker popups and tooltips.

23. **Tile-Based Location Clustering**

    -   `GET /v4/locations/tile?{search}` returns tile-based cluster grids.
    -   Enables efficient display of large-scale datasets in map tiles.

24. **Proximity Search**
    -   `GET /v4/locations/point?{search}` retrieves all samples within a radial distance from given coordinates.
    -   Uses OpenSearch geo-distance queries with precision control.

---

### Search and Filtering Features

25. **Dynamic Search Props**

    -   Supports query parameters:  
        `sampleCollections`, `expeditions`, `authors`, `journals`, `publicationYears`, `sampleNames`, etc.
    -   Enables combined filters via OR (`||`) or range (`2000-2024`) syntax.
    -   Automatically parsed and formatted in Express middleware.

26. **Advanced Filters**

    -   Supports structured filters for complex objects:
        -   `analysisTypes=minerals::[aganthite]`
        -   `taxons=meteorite::[nahklite]`
        -   `geoFeatures=crater::[plum crater]`
    -   Parses nested arrays and dot notation (e.g., `Si.WET → { Si: [“WET”] }`).

27. **Location Filters**
    -   Accepts spatial parameters like `boundingBox`, `precision`, `polygons`, and `size`.
    -   Fully compatible with GeoJSON polygons and multi-bounding-box queries.
    -   Enables dynamic geospatial filtering on client UI.

---

### Reliability and System Architecture

28. **Error Handling & Logging**

    -   All errors logged with context to ECS logs.
    -   Includes structured JSON error responses for API consumers.
    -   Standardized error codes across all v4 endpoints.

29. **Performance Optimizations**

    -   Built-in caching and pagination for composite aggregations.
    -   Scroll API usage for massive data queries (100k+ hits).
    -   Streamed responses for export to S3 without overloading memory.

30. **DynamoDB Integration**

    -   Centralized tracking of exports, tokens, and task statuses.
    -   Uses Point-In-Time Recovery (PITR) and consistent backups.
    -   Queryable by user email for audit and recovery.

31. **OpenSearch Integration**
    -   Core data retrieval via OpenSearch composite aggregations.
    -   Index mappings support nested structures for hierarchical vocabularies.
    -   High-availability configuration with scroll + afterKey for pagination.

---
