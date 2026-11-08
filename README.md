# Socioeconomic Disparities in Urban Green Space Accessibility: Tāmaki Makaurau Auckland

This repository contains the spatial analysis workflows, data documentation, and research framework for investigating urban green space equity across Tāmaki Makaurau Auckland. The project applies geographic information systems (GIS) to evaluate how socioeconomic deprivation influences walkable access to public parks and reserves.

---

## 📌 Project Overview

Urban green spaces are critical components of resilient, liveable cities. However, access to these amenities is frequently inequitable. This research utilizes **2023 New Zealand Deprivation (NZDep23)** scores at the Statistical Area 2 (SA2) level alongside pedestrian network data to examine whether lower-income communities experience structural disadvantages in park accessibility.

### Key Objectives:
1. **Map Spatial Distribution:** Assess the geographic relationship between publicly accessible green spaces and 2023 NZDep deprivation scores across Auckland’s urban suburbs.
2. **Network Distance Analysis:** Measure walking catchment accessibility thresholds of **400 metres** (approx. 5 minutes walk) and **800 metres** (approx. 10 minutes walk) using ArcGIS Pro's Network Analyst extension.
3. **Hotspot Clustering:** Identify statistically significant spatial clusters of green space deficit using **Getis-Ord ($Gi^*$)** statistics to determine where structural accessibility disparities concentrate.

---

## 🛠️ Methodology & Tools

* **Software:** ArcGIS Pro (Network Analyst & Spatial Statistics extensions)
* **Spatial Scale:** Statistical Area 2 (SA2) Level (Auckland urban residential context)
* **Data Inputs:**
  * *Green Space Data:* Publicly accessible local parks and reserves sourced from the Auckland Council Open Data Portal.
  * *Socioeconomic Data:* 2023 New Zealand Deprivation (NZDep23) index, published by the **University of Otago**.
  * *Pedestrian Network Data:* Walking routes extracted from OpenStreetMap (OSM), acknowledging network topology verification and completeness considerations.

---

## 🗂️ Repository Structure

```text
├── data/
│   ├── raw/                  # Original datasets (Auckland Council parks, NZDep23, OSM networks)
│   └── processed/            # Cleaned shapefiles, network datasets, and spatial joins
├── maps/                     # Exported map outputs (PNG/PDF formats)
│   ├── 01_study_area_context.pdf
│   ├── 02_green_space_deprivation_overlay.pdf
│   ├── 03_walking_catchments_400_800m.pdf
│   └── 04_getis_ord_hotspot_clusters.pdf
├── docs/                     # Full research proposal and assessment reports
└── README.md
```

---

## 🚀 Getting Started & Replication

To replicate or build upon this spatial analysis pipeline:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/uoa-gis/GIS.git
   ```
2. **Set Up ArcGIS Pro Workspace:**
   * Open ArcGIS Pro and create a new project linked to the local directory.
   * Ensure the coordinate system is set consistently (e.g., NZGD 2000 / New Zealand Transverse Mercator 2000).
3. **Run Network Analysis:**
   * Import the OpenStreetMap pedestrian network into a Network Dataset.
   * Generate service area polygons for 400m and 800m thresholds originating from park entry points.
4. **Execute Hotspot Analysis:**
   * Run the **Optimized Hot Spot Analysis** or **Getis-Ord Gi*** tool on the calculated green space deficit metric per SA2 unit.

---

## Discussion & Future Work

### Spatial Equity Insights
The preliminary integration of 2023 New Zealand Deprivation (NZDep23) scores with 400m and 800m network service areas highlights distinct spatial inequalities in Tāmaki Makaurau Auckland's urban green space provision. Consistent with wider environmental justice literature, our network distance analysis demonstrates that accessibility deficits in high deprivation areas particularly across parts of South Auckland—are heavily driven by street network connectivity and park distribution barriers rather than the total absence of green space. 

### Methodological Considerations & Limitations
* **Network Routing & Crowdsourced Data:** Utilizing OpenStreetMap (OSM) pedestrian networks provides high-resolution coverage, but inherent variations in crowdsourced data completeness require rigorous topology validation.
* **Spatial Scale:** Aggregating analysis at the Statistical Area 2 (SA2) level effectively captures regional neighborhood variation but can mask hyper local disparities or micro-climatic green space access within individual communities.
* **Park Typology:** Restricting the inventory to publicly accessible council reserves ensures a clear focus on public health equity, though it excludes semi-public or institutional open spaces that may supplement local utility.

### Policy Implications & Next Steps
These findings provide empirical spatial evidence to support Auckland Council's open space planning under the *Manaaki Tāmaki Makaurau* strategy. Future iterations of this pipeline will incorporate fine-resolution demographic weighting, multi-modal transit accessibility layers, and temporal usage metrics to further refine urban equity planning across Aotearoa.
