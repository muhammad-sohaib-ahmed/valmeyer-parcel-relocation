# valmeyer-parcel-relocation
Spatial analysis and web map publication evaluating parcel relocation data for Valmeyer, Illinois.
# Moving Valmeyer: Spatial Analysis & Parcel Relocation 📍

[![ArcGIS Online Web Map](https://img.shields.io/badge/ArcGIS%20Online-Interactive%20Web%20Map-blue?style=for-the-badge&logo=arcgis)](https://ucd-cpe.maps.arcgis.com/apps/mapviewer/index.html?webmap=584a25135bc5433a932bc624eeda160e)

## Overview
Following the catastrophic Mississippi River flooding of 1993, the town of Valmeyer, Illinois, was relocated to higher ground on nearby bluffs[cite: 3]. This GIS project evaluates terrain elevation, slope suitability, and relocation distance for the newly developed upland site while digitizing complete infrastructure networks and deploying an interactive web application[cite: 3].

## Interactive Web Map
🔗 **[Launch the Live ArcGIS Online Web Map](https://ucd-cpe.maps.arcgis.com/apps/mapviewer/index.html?webmap=584a25135bc5433a932bc624eeda160e)**

![Moving Valmeyer Final Web Map](Screenshot%202026-08-07%20171713.jpg)

---

## Technical Workflow & Tools
* **GIS Software:** ArcGIS Pro, ArcGIS Online[cite: 3]
* **Spatial Techniques:** Zonal Statistics, Feature Digitizing (Snapping), Relational Attribute Joins, Coordinate Transformation[cite: 3]
* **Scripting / Logic:** Python 3 (Calculate Field attribute transfer)[cite: 3]

---

## Datasets Used
* **Vector Data:** `old_valmeyer_parcels` (historic flood-prone site), `new_valmeyer_parcels` (upland development site), `New_Valmeyer_Roads` (digitized road centerlines)[cite: 3].
* **Raster Data:** 10m Digital Elevation Model (`valmeyer_dem_10m`), derived Slope raster (`Slope_valmey1`), Euclidean distance raster (`EucDist_old_1`)[cite: 3].
* **Basemaps:** Esri World Topographic Map / World Hillshade[cite: 3].

---

## Methodology
1. **Zonal Summary Aggregation:** Executed *Zonal Statistics as Table* across DEM, slope, and distance rasters against parcel zones (`PARCEL_NUM`)[cite: 3].
2. **Tabular Joins & Attribute Transfer:** Joined summary tables to vector parcels, populated 7 custom fields (`min_elev`, `max_elev`, `mean_elev`, `min_slope`, `max_slope`, `mean_slope`, `move_dist`) via Python expressions, and removed joins to maintain standalone data integrity[cite: 3].
3. **Infrastructure Digitization:** Digitized road centerlines (`New_Valmeyer_Roads`) within the project File Geodatabase using point, end, and intersection snapping[cite: 3].
4. **Cartography & Publishing:** Styled new parcels by mean elevation using 5-class Natural Breaks (Jenks), projected to WGS 1984 Web Mercator, and published interactive vector feature layers to ArcGIS Online[cite: 3].

---

## Key Findings
* **Flood Resilience:** New parcels sit on an elevated bluff ranging between **202m and 243m** above sea level, placing the entire community safely above historic Mississippi River flood stages[cite: 3].
* **Topographic Suitability:** Most residential parcels occupy gentle slopes ($<15^\circ$), with steeper slopes ($>20^\circ$) naturally bounding the development footprint[cite: 3].
* **Relocation Footprint:** The new townsite is situated approximately **2,000m to 2,600m east** of the original flood zone[cite: 3].

---
*📄 Detailed analysis and geoprocessing steps are available in the [Moving Valmeyer Spatial Analysis Documentation (PDF)](Moving%20Valmeyer%20Spatial%20Analysis.pdf).*[cite: 3]
