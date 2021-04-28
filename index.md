---
name: home
title: Home
date: 2021/01/21
layout: default
test: No one will notice me...
---

   [![NSF-1948806](https://img.shields.io/badge/NSF-1928366-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948806)
##  EarthChem Library Tech Documentation

EarthChem Library (ECL) is a data repository that archives, publishes and makes accessible data and other digital content from geoscience research (analytical data, data syntheses, models, technical reports, etc).

This repository contains all documentations related to ECL infrastructure, software design, and development.

The EarthChem Library consists a set of web applications written in PHP and Javascript, such as Submission, Search, Browse and MyECL. Submission and MyECL are secured applications. There are two methods for user authentication: GeoPass or ORCID. GeoPass is a single-sign-on service maintained by EarthChem.
ECL provides multiple web services for external application integration (REST API, WMS and WFS). The Beta version REST API was implemented and released in February, 2020. Please contact us with any suggestions and questions at info@earthchem.org.

### System Requirements
* Database Server:
  * OS Version: Red Hat Enterprise Linux Server release 6.10 (Santiago)
  * PostgreSQL: version 9.5.3
  * PostGIS: version 2.1
* Application Server:
  * PHP: version 5.4.45
  * OS Version: Red Hat Enterprise Linux Server release 7.5 (Maipo)
  * Apache: version 2.4.6
