---
name: index
title: Home
date: 2021/01/21
layout: default
---

[![NSF-1948806](https://img.shields.io/badge/NSF-1928366-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948806)

# EarthChem Systems

Welcome to the **EarthChem Systems - Technical Documentation**, a collection of web-based tools that enable geochemical data discovery, synthesis, and analysis.

Each application below includes links to its detailed documentation and latest release notes.

---

## 1. PetDB Synthesis Interface

**Purpose:**  
Interactive global interface for exploring and exporting geochemical sample data.  
It supports dynamic filtering by analytical features, and sample features, as well as additional lookups.

**Key Features:**

-   3D globe and polar map projections.
-   Flexible filters for geochemical datasets.
-   Export in CSV or JSON formats via AWS pipeline.
-   Integration with DynamoDB, S3, and OpenSearch.

**Links:**

-   [Documentation](./documentation/synthesis.html)

---

## 2. PetDB API

**Purpose:**  
Provides structured access to PetDB data for programmatic integration.  
Supports filtering, aggregation, and advanced querying across samples, analyses, and citations.

**Key Features:**

-   RESTful Node.js API with Express and OpenSearch.
-   Endpoint access for sample, material, and feature data.
-   JSON response format optimized for research pipelines.
-   Authentication and rate limiting built-in.

**Links:**

-   [Documentation](./documentation/petdb_api.html)
-   [Release Notes](./release_notes/petdb_api.html)

---

## 3. Export Service

**Purpose:**  
Handles all user-initiated export requests across the EarthChem platform.  
Built on Node.js/Express with DynamoDB task tracking, S3 streaming, and email notifications.

**Key Features:**

-   Async queue-based processing for large datasets.
-   File-type support for JSON and CSV.
-   Secure S3 upload with expiring download links.
-   Auto-email notifications when exports complete.

**Links:**

-   [Documentation](./documentation/export_service.html)
-   [Release Notes](./release_notes/export_service.html)

---

## EarthChem Library Tech Documentation

EarthChem Library (ECL) is a data repository that archives, publishes and makes accessible data and other digital content from geoscience research (analytical data, data syntheses, models, technical reports, etc).

This repository contains all documentations related to ECL infrastructure, software design, and development.

The EarthChem Library consists a set of web applications written in PHP and Javascript, such as Submission, Search, Browse and MyECL. Submission and MyECL are secured applications. There are two methods for user authentication: GeoPass or ORCID. GeoPass is a single-sign-on service maintained by EarthChem.
ECL provides multiple web services for external application integration (REST API, WMS and WFS). The Beta version REST API was implemented and released in February, 2020. Please contact us with any suggestions and questions at info@earthchem.org.

### System Requirements

-   Database Server:
    -   OS Version: Red Hat Enterprise Linux Server release 6.10 (Santiago)
    -   PostgreSQL: version 9.5.3
    -   PostGIS: version 2.1
-   Application Server:
    -   PHP: version 5.4.45
    -   OS Version: Red Hat Enterprise Linux Server release 7.5 (Maipo)
    -   Apache: version 2.4.6
