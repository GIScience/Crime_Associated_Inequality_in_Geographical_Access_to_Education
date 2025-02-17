# Overview

This folder contains Jupyter Notebooks for analyzing crime data, performing dasymetric mapping, and calculating safety scores on an OSM street network.

## 01 Zonal Statistics

### Input
- **Preliminary Steps**: Several preliminary steps were performed in QGIS on the `00_input_200m_centrality_grid.gpkg` file located in the [00_zonal_stats_processed_data](../../data/01_input_data/00_zonal_stats_processed_data) folder.
- **Resulting File**: The resulting file, `00_zonal_stats_processed_data.gpkg` in the [01_input_data](../../data/01_input_data) folder, contains the following fields and is first used in this notebook:

   <details>
   <summary><b>Fields description</b></summary>
    
   | Fields                                                    | Methodology                                                                 |
   |-----------------------------------------------------------|-----------------------------------------------------------------------------|
   | `Average_building_height`                                 | Average height of buildings                                                 |
   | `Average_household_income`                                | Average household income                                                    |
   | `Cumulative_opportunity_measure_to_access_jobs_in_60_minutes`| Average cumulative opportunity measure to access jobs within 60 minutes     |
   | `Illiteracy_rate`                                         | Average illiteracy rate                                                     |
   | `Normalized_difference_vegetation_index`                  | Average NDVI (Normalized Difference Vegetation Index)                       |
   | `Number_of_CCTV_cameras`                                  | Count of CCTV cameras                                                       |
   | `Number_of_buildings`                                     | Count of buildings                                                          |
   | `Number_of_streetlights`                                  | Count of streetlights                                                       |
   | `OSM_road_network_centrality_by_average_travel_time_in_car`| Average centrality of road network based on travel time by car              |
   | `Perceptual_GeoAI_safety_score_from_street_view_imagery`  | Average safety score from IDW interpolation                                 |
   | `Satellite_nightlight_saturation`                         | Average satellite nightlight radiance                                       |
   | `Travel_time_to_closest_healthcare_facility`              | Average travel time to the closest healthcare facility                      |
   *Note: 200m grid level*
   </details>

### Processing
- **[`01_Zonal_statistics.ipynb`](../02_street_crime_index/01_zonal_statistics.ipynb)**: Performs zonal statistics analysis on crime data. This includes finding the nearest police and military stations, processing CISP data, calculating coverage of urban areas, favelas, buildings, and gang territories, and generating final zonal statistics.

### Output
- **Crime Data**: `crime_index_zonal_statistics.gpkg` saved in [02_intermediate_output](../../data/02_intermediate_output) directory

## 02 Downscaling

### Input
- **Crime Data**: `crime_index_zonal_statistics.gpkg` - crime index variables calculated from zonal statistics notebook

### Processing
- **[`02_downscaling_crime_index.ipynb`](../02_street_crime_index/02_downscaling_crime_index.ipynb)**: Implements downscaling techniques to redistribute crime data from Police unit (CISP) regions to 200m grid cells. The redistribution is influenced by non-CISP data at the grid level.

### Output
- **Redistributed Crime Data**: (`crime_index_grid.gpkg`) Crime data redistributed to 200m grid cells saved in [02_intermediate_output](../../data/02_intermediate_output) directory

## 03 Safety Index for Road Segments

### Input
- **Redistributed Crime Data**: `crime_index_grid.gpkg` crime index on grids from downscaling notebook
- **OSM Data**: `osm_roads.gpkg` and `osm_roads_10m_buffer.gpkg` (same line buffered 10m in QGIS) in [01_input_data](../../data/01_input_data) directory

### Processing
- **[`03_crime_index_road_segments.ipynb`](../02_street_crime_index/03_crime_index_road_segments.ipynb)**: Calculates safety scores for OSM road segments based on crime data.

### Output
- **Crime Index**: (`crime_index_street.csv`) Crime index for OSM road segments saved in [02_intermediate_output](../../data/02_intermediate_output) directory

## Further Steps

For the next processing steps, refer to the [Routing](../03_routing) directory.