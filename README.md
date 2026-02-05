# Arkansas Game and Fish Commission (AGFC) Spatial Data Repository

## Overview
This repository contains geospatial data obtained from the Arkansas Game and Fish Commission (AGFC) for use in economic analysis of wildlife resources and land values in Arkansas. Data is used for dissertation research at the University of Arkansas Sam M. Walton College of Business.

- **Data Acquisition Date:** February 2026
- **Coordinate System:** NAD83 UTM Zone 15N (EPSG: 26915)
- **Coverage:** Statewide Arkansas
- **Data Provider:** Arkansas Game and Fish Commission

## Contents

### 1. AGFC Gates and Barriers ([AGFC_GATES_AND_BARRIERS/](AGFC_GATES_AND_BARRIERS/))
**Description:** Point features representing physical barriers and access control points on AGFC properties statewide.

**Feature Types:**
- Gates
- Pipes
- Cables
- Points of Interest (POIs)
- Other physical barriers

**Use Cases:**
- Measuring WMA access control intensity
- Calculating gate density per WMA perimeter
- Analyzing relationship between access restriction and adjacent land values

**Key Attributes:**
- Feature type
- Location coordinates
- Associated WMA (if applicable)

### 2. Outdoor Recreational Facilities ([OUTDOOR_RECREATIONAL_FACILITIES/](OUTDOOR_RECREATIONAL_FACILITIES/))
**Description:** Point features representing built facilities on AGFC properties.

**Facility Types Include:**
- Archery Range
- Bank Fishing
- Boating Access
- Boat Ramps
- Check Station
- Courtesy Dock
- Deer Stand
- Duck Hole
- Firing Range
- Fish Cleaning Station
- Fish Weigh-In Station
- Fishing Jetty/Pier
- Foot Bridge
- Marina
- Observation Blind/Platform/Terrace
- Overlook Arbor
- Park/Picnic Area/Pavilion
- Parking Area
- Playground
- Restroom/Showers
- RV Hookups/Dump Station
- Swimming Area
- Tent Camping/Walk-in Access

**Use Cases:**
- Creating WMA amenity quality indices
- Calculating distance from parcels to nearest boat ramp/parking
- Testing whether facility quality affects adjacent land value premiums
- Analyzing facility-type heterogeneity (boat access vs. parking vs. camping)

**Key Attributes:**
- Facility type
- Facility name
- Associated WMA
- Coordinates

### 3. Outdoor Recreation Access ([OUTDOOR_RECREATION_ACCESS/](OUTDOOR_RECREATION_ACCESS/))
**Description:** Linear features representing roads, trails, and access routes within Wildlife Management Area boundaries.

**Feature Types:**
- State roads
- County roads
- AGFC roads
- Fire lanes
- Mobility-impaired trails
- Boat lanes
- Trails

**Key Attributes:**
- Road/trail type
- Surface type (paved, gravel, dirt)
- Owner (State, County, AGFC)
- Associated WMA
- Access restrictions
- Length
- Information hyperlinks

**Use Cases:**
- Calculating WMA road density (miles per 1,000 acres)
- Measuring WMA "penetrability" (high road density = easier public access)
- Testing hypothesis: Adjacent land value premium is higher for low-access WMAs (quasi-exclusive access)
- Analyzing congestion externalities from public land

### 4. Wildlife Management Areas (WMAs) ([STATE_WILDLIFE_MANAGEMENT/](STATE_WILDLIFE_MANAGEMENT/))
**Description:** Polygon features representing the boundaries of Arkansas Wildlife Management Areas.

**Key Attributes:**
- WMA name
- Acreage
- County location
- Management type (if available)
- Establishment date (if available)
- Management designation (e.g., trophy management area)

**Use Cases:**
- Identifying parcels adjacent to WMAs (spatial join)
- Calculating distance from parcels to WMA boundaries
- Measuring WMA density within radius of parcels
- Difference-in-differences analysis (if establishment dates available)

**Coverage:** All AGFC-managed Wildlife Management Areas statewide

### 5. WMA Management Features ([WMA_MANAGEMENT_FEATURES/](WMA_MANAGEMENT_FEATURES/))
**Description:** Features describing specific management activities and characteristics within Wildlife Management Areas.

**Potential Attributes:**
- Management unit designations
- Habitat management types (timber, prescribed fire, food plots, waterfowl impoundments)
- Management intensity indicators
- Special designation areas (trophy units, restricted access zones)
- Dates of management activities

**Use Cases:**
- Creating habitat quality proxies beyond harvest data
- Testing whether active management (food plots, burns) increases adjacent land values
- Analyzing spillover effects of habitat improvements onto private land
- Distinguishing trophy management units from general harvest areas

## Data Processing Notes

### Projection Information
All datasets are provided in **NAD83 UTM Zone 15N (EPSG: 26915)** with units in meters.

### Quality Considerations
- Data reflects AGFC holdings as of February 2026
- Some attributes may be incomplete or vary by WMA
- Users should verify data currency for time-sensitive applications
- Not suitable for legal boundary determination (per Arkansas Law 15-21-504 2 B)

### Recommended Software
- **R:** `sf`, `terra` packages for spatial operations
- **ArcGIS Pro/Desktop:** Full compatibility
- **QGIS:** Open-source alternative

## Research Applications

### Primary Use: Land Value Hedonic Analysis
Testing how proximity to and quality of public hunting lands affects rural land prices:

- **Adjacency Premium:** Do parcels bordering WMAs command price premiums?
- **Amenity Quality:** Do high-amenity WMAs (boat ramps, parking) create larger premiums than low-amenity WMAs?
- **Access Intensity:** Do WMAs with high road density (congestion) reduce adjacent land values?
- **Facility-Specific Effects:** Does proximity to boat ramps matter more in Delta (waterfowl) vs. Ozarks (deer)?
- **Management Spillovers:** Do actively managed WMAs increase neighboring private land values?

### Policy Applications
- Payment in Lieu of Taxes (PILT) calculations
- Conservation easement valuation
- State Wildlife Action Plan funding priorities
- WMA design optimization (facility placement, access management)

## Data Citation

**Suggested Citation:**

> Arkansas Game and Fish Commission. (2026). Wildlife Management Areas and Recreational Facilities Spatial Data [Shapefiles]. Provided for academic research, February 2026.

## Contact & Data Use

**Primary Researcher:**
Tandem Young
PhD Student, Economics
Sam M. Walton College of Business
University of Arkansas

**Data Provider:**
Ralph Meeker, CWB®
Deer Program Coordinator
Arkansas Game and Fish Commission

### Data Use Agreement
This data is provided for academic research purposes. Users should:
- Acknowledge AGFC as the data source in all publications
- Not redistribute without permission
- Share research findings with AGFC upon completion

## Repository Structure

```
/AGFC/
├── README.md (this file)
├── AGFC_GATES_AND_BARRIERS/
│   ├── AGFC_GATES_AND_BARRIERS.shp
│   ├── AGFC_GATES_AND_BARRIERS.shx
│   ├── AGFC_GATES_AND_BARRIERS.dbf
│   └── AGFC_GATES_AND_BARRIERS.prj
├── OUTDOOR_RECREATIONAL_FACILITIES/
│   ├── OUTDOOR_RECREATIONAL_FACILITIES.shp
│   ├── OUTDOOR_RECREATIONAL_FACILITIES.shx
│   ├── OUTDOOR_RECREATIONAL_FACILITIES.dbf
│   └── OUTDOOR_RECREATIONAL_FACILITIES.prj
├── OUTDOOR_RECREATION_ACCESS/
│   ├── OUTDOOR_RECREATIONAL_ACCESS.shp
│   ├── OUTDOOR_RECREATIONAL_ACCESS.shx
│   ├── OUTDOOR_RECREATIONAL_ACCESS.dbf
│   └── OUTDOOR_RECREATIONAL_ACCESS.prj
├── STATE_WILDLIFE_MANAGEMENT/
│   ├── ST_WILDLIFE_MNGMNT_AGFC.shp
│   ├── ST_WILDLIFE_MNGMNT_AGFC.shx
│   ├── ST_WILDLIFE_MNGMNT_AGFC.dbf
│   └── ST_WILDLIFE_MNGMNT_AGFC.prj
└── WMA_MANAGEMENT_FEATURES/
    ├── WMA_Management_Features.shp
    ├── WMA_Management_Features.shx
    ├── WMA_Management_Features.dbf
    └── WMA_Management_Features.prj
```

## Version History

**v1.0 (February 2026)**
- Initial data acquisition from AGFC
- Standardized projection to NAD83 UTM Zone 15N
- Created repository structure

## Acknowledgments

This research is supported by the University of Arkansas Sam M. Walton College of Business. Special thanks to Ralph Meeker and the Arkansas Game and Fish Commission for providing access to these critical datasets.

## License

Data provided by Arkansas Game and Fish Commission for academic research. Contact AGFC for commercial or redistribution permissions.
