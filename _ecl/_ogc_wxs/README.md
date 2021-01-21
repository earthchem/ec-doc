---
name: ogc_wxs
title: Open Geospatial Consortium (OGC) WxS Services
date: 01/07/2020
layout: default
---

#### Open Geospatial Consortium (OGC) WxS Services

  WxS services provides a live access to EarthChem Library sample within dataset location map, dataset core metadata.

* WFS provides the access to the core metadata of datasets.
  * WFS: https://prod-app.earthchem.org/geoserver/EarthChemLibrary/ows?service=WFS&request=GetCapabilities
  
* WMS provides the distribution map of the sample location of datasets.
  * WMS: https://prod-app.earthchem.org/geoserver/EarthChemLibrary/wms?service=WMS&request=GetCapabilities
  * Demo: https://prod-app.earthchem.org/geoserver/gwc/demo/EarthChemLibrary:ecl_geom?gridSet=EPSG:4326&format=image/jpeg
