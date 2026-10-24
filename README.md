# Watershed Delineation of Soan River Basin using GIS

**Prepared by:** Aiman Afzal, Atiqa Pervez

## 📌 Project Overview
This project demonstrates a complete DEM-based hydrological modeling workflow to delineate the watershed boundary of the Soan River Basin, Pakistan. The Soan River is a major tributary of the Indus River and drains the Potohar Plateau. Understanding its hydrology is critical due to regional challenges with flooding, soil erosion, and rapid urban expansion near Islamabad and Rawalpindi.

**Objective:** To delineate the watershed boundary, generate drainage patterns, and understand surface water flow behavior using spatial analysis tools.

## 🛠️ Data & Tools
*   **Software:** ArcGIS Desktop 10.5 (Spatial Analyst & Hydrology Tools)
*   **Data Source:** USGS / SRTM Digital Elevation Model (DEM)
*   **Resolution:** 30 meters
*   **Coordinate System:** WGS 84 (reprojected to PCS for accurate area calculation)

## ⚙️ Methodology (Workflow)
The hydrological model was executed using the ArcGIS Spatial Analyst toolbox. The workflow included:
1.  **DEM Preparation:** Clipping and reprojecting the raw DEM.
2.  **Sink Filling:** Using the `Fill` tool to remove artificial depressions that block water flow.
3.  **Flow Direction & Accumulation:** Calculating the steepest descent path and identifying areas of high runoff.
4.  **Stream Definition:** Applying a Raster Calculator conditional expression (`Flow Accumulation > 20,000`) to extract the main drainage network.
5.  **Pour Point Selection:** Defining the outlet and using the `Snap Pour Point` tool to align it with the highest flow accumulation cell.
6.  **Watershed Delineation:** Tracing all upstream contributing cells using the `Watershed` tool.
7.  **Vectorization & Analysis:** Converting the watershed raster to a polygon, calculating the total area, and running `Zonal Statistics` to extract elevation data.

## 📊 Key Results
*   **Total Watershed Area:** 942.37 km² (942,372,434.64 sq meters)
*   **Elevation Range:** Minimum 269.5 m, Maximum 587.5 m
*   **Mean Elevation:** 395.43 m

> *"The analysis successfully demonstrated that watershed boundaries follow terrain rather than administrative limits, providing quantitative insights for flood risk assessment and water resource planning."*

## 🖼️ Visuals

### Final Result
**Final Watershed Delineation Map:**
![Final Map](./images/04_final_output/final_map.png)

### Workflow Gallery
**1. Data Preparation (DEM Processing):**
<img width="596" height="429" alt="raw_dem" src="https://github.com/user-attachments/assets/22925128-8fbe-4dc2-afb5-a4493549f5d2" />
<img width="636" height="424" alt="filled_dem" src="https://github.com/user-attachments/assets/40b72b9a-c45e-4ddf-95bd-3dba6ececc0b" />
<img width="615" height="434" alt="projected_dem" src="https://github.com/user-attachments/assets/84753462-bc6e-4c10-9064-dc21c46e99b3" />

**2. Flow Analysis:**
<img width="496" height="383" alt="flow_direction" src="https://github.com/user-attachments/assets/c3f704b6-509a-41d4-b3b6-fc8f3e568024" />
<img width="496" height="383" alt="flow_direction_zoomed" src="https://github.com/user-attachments/assets/c405df8d-2b75-4db9-9955-c6138eabcd5c" />
<img width="496" height="399" alt="flow_accumulation" src="https://github.com/user-attachments/assets/00cd4a1b-88ff-4c43-869c-76e64ac6ff2b" />

**3. Stream and Watershed Delineation:**
<img width="589" height="564" alt="pour_point" src="https://github.com/user-attachments/assets/ee78cd35-09e2-499a-b903-f44efc0c3f52" />
<img width="1246" height="760" alt="stream_definition" src="https://github.com/user-attachments/assets/0ff70ca9-6ddd-4ba7-b09e-47d7ebd87bc4" />
<img width="2225" height="1212" alt="watershed_output" src="https://github.com/user-attachments/assets/7b7b0b50-b33b-4ec2-92bf-22690200d524" />

## 📁 Presentation & Documentation
*Due to file size and proprietary software constraints, the raw ArcMap `.mxd` files and geodatabases are not included in this repository. The complete step-by-step workflow, intermediate tool outputs, and results are fully documented in the attached presentation.*

👉 **[Click here to view the full project presentation (PDF)](./Watershed_Delineation_Soan_River.pdf)**
