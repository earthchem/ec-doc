---
name: earthchem_export_service
title: Earthchem Export Service
date: 09/10/2025
layout: default
order: 12
---

### Export Service

![Export](https://img.shields.io/badge/Export Service-Docs-green)

#### Overview

The Export Service enables users to request, track, and download data exports in **JSON** or **CSV** format.  
It supports queued task processing, progress tracking, error handling, and secure file storage in **AWS S3**.

---

#### Functional Requirements

##### 1. File Types

| Property             | Description                                             |
| -------------------- | ------------------------------------------------------- |
| **Supported Types**  | JSON, CSV                                               |
| **Default Format**   | CSV (data streamed initially as CSV)                    |
| **Alternate Format** | Pass `fileType=json` to receive a JSON array of objects |
| **Max Export Size**  | 80,000 rows (~600k sample data points)                  |

---

##### 2. Task Processing

Each export request creates a **unique task** with a lifecycle managed through task statuses.

| Environment   | Unique Task ID Source                        |
| ------------- | -------------------------------------------- |
| **Synthesis** | Derived from the URL search query parameters |
| **PetDB API** | Derived from the URL search query parameters |

###### Task Statuses

| Status         | Description                                                                         |
| -------------- | ----------------------------------------------------------------------------------- |
| **Pending**    | Task created and queued for processing                                              |
| **Processing** | Task picked up and currently being processed                                        |
| **Failed**     | Task failed due to an error (e.g., validation, access issues) — includes error logs |
| **Succeeded**  | Task completed successfully and export file verified                                |
| **Cancelled**  | Task manually cancelled before completion (optional)                                |

---

##### 3. Task Queue Management

-   FIFO (First-In-First-Out) queue ensures fair task processing.
-   **Parallel processing** supports up to 3 parallel processes without impacting performance.
-   **3 Retry attempts** supported for failed tasks, which are executed consecutively.

---

##### 4. User Notifications & Logging

-   **Real-time progress tracking** via API (progress bar updates coming soon).
-   **Resilience & error handling**: all task transitions are logged with error reasons.
-   **Email notifications** (required for all synthesis exports) on task completion or failure.

---

#### Non-Functional Requirements

##### 1. Security

###### Authentication & Authorization

-   Enforced via **API keys or OAuth**.
-   Only authorized users can initiate or view exports (Synthesis/API).

###### Data Protection

-   Files encrypted before storage.
-   Public access for file retrieval. All export URLs are sent to user via email and handled via browser if small exports (< 10k rows)

###### Audit Logging

-   All exports, status changes, and downloads logged in **DynamoDB**.
-   **Point-in-Time Recovery (PITR)** snapshot of export table every **35 days**.

---

##### 2. Performance

| Metric                    | Notes                                                          |
| ------------------------- | -------------------------------------------------------------- |
| **Concurrent Processing** | Multiple exports processed simultaneously                      |
| **Cancellation**          | Tasks cancellable via UI/API with threaded checks              |
| **API Response Time**     | < 500ms (excluding long-running tasks)                         |
| **Status Check Interval** | Every 10 seconds                                               |
| **Data Fetching**         | Single-pass OpenSearch queries via scroll API                  |
| **Export Speed**          | 40k rows × 2897 columns generated in < 4m20s under normal load |

---

##### 3. Scalability

-   **Horizontal Scaling** — Multiple worker instances for concurrent task handling
-   **Asynchronous Processing** — Decoupled via internal queue system
-   **Cloud Storage** — Exports stored in AWS S3 (no auto-deletion exists yet, all files accesible indefinately)
-   **Rate Limiting** — IP-based throttling with potential per-user limits (planned/not yet implemented)

---

##### 4. Reliability & Fault Tolerance

| Mechanism            | Description                                                                       |
| -------------------- | --------------------------------------------------------------------------------- |
| **Retries**          | Automatic retries for transient OpenSearch/DynamoDB errors                        |
| **Graceful Failure** | Cleared error messages for failed exports / logged internally                     |
| **Auto Cleanup**     | Expired exports deleted after configurable retention window (not yet implemented) |

---
