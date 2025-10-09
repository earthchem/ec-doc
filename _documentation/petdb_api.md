---
name: petdb_api
title: PetDB API
date: 09/10/2025
layout: default
order: 10
---

### PetDB API

![PetDB API](https://img.shields.io/badge/PetDB API-Docs-green)

#### Summary of Key Improvements

-   **Full composite aggregation support** for hierarchical vocabularies.
-   **DynamoDB-backed exports** with cancel/resume functionality.
-   **Expanded search props** for complex queries including geospatial (bounding boxes, polygons, ranges).
-   **Deprecated legacy endpoints** replaced with modularized REST routes.

**NOTE:** For working examples please visit our [public postman](https://www.postman.com/planetary-resonance-888424/workspace/earthchem-astromat/collection/7873202-c1fb1b60-645a-4b50-a355-5d4a92bb655d?action=share&source=copy-link&creator=7873202)

---

##### 1. Vocabulary Endpoints

Provide structured, hierarchical aggregations of metadata across PetDB and Astromat datasets.

| Method | Endpoint                | Description                                                                                |
| ------ | ----------------------- | ------------------------------------------------------------------------------------------ |
| GET    | `/v4/geoFeatures`       | Retrieves nested geoFeature hierarchy (type → name)                                        |
| GET    | `/v4/taxons`            | Retrieves hierarchical taxon structure (parent-child)                                      |
| GET    | `/v4/sampleCollections` | Lists sample collections (type → name)                                                     |
| GET    | `/v4/expeditions`       | Lists expeditions (Astromat: `sample.expeditions`; EarthChem: `sampleExpeditions`)         |
| GET    | `/v4/authors`           | Returns author list (`citation.authors.familyName`)                                        |
| GET    | `/v4/publicationYears`  | Lists all citation publication years                                                       |
| GET    | `/v4/citationTitles`    | Lists all citation titles                                                                  |
| GET    | `/v4/journals`          | Returns journal list (`citation.containerTitle`)                                           |
| GET    | `/v4/variables`         | Returns variable group and variable hierarchy                                              |
| GET    | `/v4/analysisTypes`     | Lists analysis types (hierarchy includes MineralName, AnalysisMaterialName, InclusionType) |
| GET    | `/v4/laboratories`      | Lists laboratories                                                                         |
| GET    | `/v4/dataSources`       | Lists data sources                                                                         |
| GET    | `/v4/sampleNames`       | Lists sample names (rootParent)                                                            |
| GET    | `/v4/`                  | Retrieves top 10 suggestions from all vocabularies                                         |

---

##### 2. Citation Endpoints

Enable citation retrieval and linking to associated samples and methods.

| Method | Endpoint                    | Description                                   |
| ------ | --------------------------- | --------------------------------------------- |
| GET    | `/v4/citations/:id`         | Retrieve detailed citation metadata           |
| GET    | `/v4/citations/:id/samples` | Retrieve samples linked to citation           |
| GET    | `/v4/citations/:id/methods` | Retrieve methods linked to citation           |
| GET    | `/v4/citations?{search}`    | Search citations by provided query parameters |

---

##### 3. Sample Endpoints

Provide full sample-level access and search functionality.

| Method | Endpoint                   | Description                   |
| ------ | -------------------------- | ----------------------------- |
| GET    | `/v4/samples/:id`          | Retrieve detailed sample info |
| GET    | `/v4/samples/:id/metadata` | Retrieve full sample metadata |

---

##### 4. Export Endpoints

Enable submission, monitoring, and cancellation of data exports.

| Method | Endpoint                      | Description                                                      |
| ------ | ----------------------------- | ---------------------------------------------------------------- |
| GET    | `/v4/exports/submit?{search}` | Initiates export request (logs to DynamoDB with timestamp/email) |
| GET    | `/v4/exports/:taskId`         | Retrieves export task status                                     |
| GET    | `/v4/exports/cancel/:taskId`  | Cancels export (updates DynamoDB record to CANCELLED)            |

---

##### 5. Metrics Endpoints

Provide system-wide metrics for monitoring dataset usage and exports.

| Method | Endpoint      | Description                                           |
| ------ | ------------- | ----------------------------------------------------- |
| GET    | `/v4/metrics` | Returns counts for citations, samples, and dataPoints |

---

##### 6. Location Endpoints

Deliver sample-level geospatial queries for visualization and analysis.

| Method | Endpoint                         | Description                                         |
| ------ | -------------------------------- | --------------------------------------------------- |
| GET    | `/v4/locations?{search}`         | Returns clustered lat/lon for samples               |
| GET    | `/v4/locations/samples?{search}` | Returns full sample metadata and coordinates        |
| GET    | `/v4/locations/tile?{search}`    | Returns tile-clustered location data                |
| GET    | `/v4/locations/point?{search}`   | Returns samples within a radius of provided lat/lon |

---

##### 7. Authorization Endpoints

Handle API token lifecycle for secure export and user operations.

| Method | Endpoint                           | Description                                   |
| ------ | ---------------------------------- | --------------------------------------------- |
| POST   | `/v4/auth/token?{search}`          | Issues new token for authorized export access |
| GET    | `/v4/auth/token/validate?{search}` | Validates an issued token                     |
| DELETE | `/v4/auth/token/revoke?{search}`   | Revokes a token                               |

---

##### 8. Deprecated Endpoints

These are superseded by version 4 routes and should be avoided.

-   `/sampleData/results` — **DEPRECATED**
-   `/sampleData/batchIds` — **DEPRECATED**
-   `/sampleData/sampleCodes` — **DEPRECATED**
-   `/sampleData/exports` — **DEPRECATED**
-   `/Citation` — **DEPRECATED**

---

##### 9. Search Props and Query Parameters

###### Basic Filters

| Prop               | Example                 | Notes                              |
| ------------------ | ----------------------- | ---------------------------------- |
| `expeditions`      | `ABP0002`               |                                    |
| `authors`          | `Smith,J`               | `<Family Name>, <Initials>` format |
| `citationTitles`   | `MARE VOLCANIC GLASSES` | Partial match supported            |
| `journals`         | `Science Advances`      | —                                  |
| `publicationYears` | `2000` or `2000-2024`   | Supports single years and ranges   |
| `sampleNames`      | `LUNA 16`               | -                                  |
| `laboratories`     | `NYU`                   | —                                  |
| `dataSources`      | `METBUL`                | —                                  |

###### Advanced Filters

| Prop            | Example                 | Notes                            |
| --------------- | ----------------------- | -------------------------------- |
| `analysisTypes` | `minerals::[aganthite]` | Displays as “Analyzed Materials” |
| `geoFeatures`   | `crater::[plum crater]` | —                                |
| `taxons`        | `meteorite::[nahklite]` | Displays as “Sample Type”        |
| `variables`     | `MAJ::[FeO]`            | —                                |

###### Location Filters

| Prop          | Example                                               | Notes                             |
| ------------- | ----------------------------------------------------- | --------------------------------- |
| `boundingBox` | `topLeft::[-55.48,17.38] bottomRight::[56.37,-14.46]` | Supports multiple bounding boxes  |
| `precision`   | `4`                                                   | Range 0–12                        |
| `polygons`    | Multi-vertex polygon array                            | Supports multiple polygons        |
| `size`        | `100`                                                 | Range 0–9,999 (aggregation limit) |

---
