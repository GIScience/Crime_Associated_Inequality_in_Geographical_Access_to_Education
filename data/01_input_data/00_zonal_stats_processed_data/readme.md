### Overview

The file `input_200m_centrality_grid.gpkg` contains input data at a 200m resolution with OSM road network centrality measured by average travel time in a car.

After performing spatial analysis to process all fields in QGIS, the data is stored in the [`01_input_data`](../../01_input_data/) directory. This allows the data to be used in the [`scripts`](../../../scripts/), which is a main part of this repository.

## File Descriptions 

| File Name                                          | Type    | Description                                                                 |
|----------------------------------------------------|---------|-----------------------------------------------------------------------------|
| `00_input_200m_centrality_grid.gpkg`               | Vector  | Input data at 200m resolution with OSM road network centrality by average travel time in a car. |
| `access_to_job_60_min_CMAT60.tif`                  | Raster  | Cumulative measure of job accessibility within a 60-minute travel time.     |
| `analphabetic.tif`                                 | Raster  | Illiteracy rate data.                                                       |
| `average_income.tif`                               | Raster  | Average income data.                                                        |
| `building_height.tif`                              | Raster  | Average building height data.                                               |
| `building_points.gpkg`                             | Vector  | Building centroids represented as points.                                   |
| `cisp_regions.gpkg`                                | Vector  | Police unit polygons.                                                       |
| `mapillary_CCTV_points.gpkg`                       | Vector  | Locations of CCTV camera points.                                            |
| `mapillary_street_light_poles.gpkg`                | Vector  | Locations of street light points.                                           |
| `ndvi.tif`                                         | Raster  | NDVI (Normalized Difference Vegetation Index) data.                         |
| `perceptual_safety_score_LDW.tif`                  | Raster  | Perceptual safety score data derived from street view images and interpolated. |
| `satellite_nightlight_saturation.tif`              | Raster  | Satellite nightlight saturation data.                                       |
| `travel_time_to_health_care_facility_TMIST.tif`    | Raster  | Travel time to the nearest healthcare facility.                             |
| `young_population.tif`                             | Raster  | Young population data (aged 5 to 19).                                       |


<!-- ## Output

- The two output files are stored in the [`01_input_data`](../../01_input_data/) directory.

  - [young_population_grid.gpkg:](../young_population_grid.gpkg) Derived from young_population.tif, this file contains the field:

        'total_population'

  
  - [00_zonal_stats_processed_data.gpkg:](../00_zonal_stats_processed_data.gpkg) This file, derived from all other files, contains the following fields:


        `Average_building_height`,
        `Average_household_income`,
        `Cumulative_opportunity_measure_to_access_jobs_in_60_minutes`,
        `Illiteracy_rate`,
        `Normalized_difference_vegetation_index`,
        `Number_of_CCTV_cameras`,
        `Number_of_buildings`,
        `Number_of_streetlights`,
        `OSM_road_network_centrality_by_average_travel_time_in_car`,
        `Perceptual_GeoAI_safety_score_from_street_view_imagery`,
        `Satellite_nightlight_saturation`,
        `Travel_time_to_closest_healthcare_facility`, -->
