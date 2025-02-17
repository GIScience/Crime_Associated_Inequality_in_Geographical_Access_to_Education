### Overview

This folder contains data to be used in the [`scripts`](../../scripts/) directory.

The primary file, `00_zonal_stats_processed_data.gpkg`, is a vector layer with 200m grid cells created in QGIS, serving as the initial dataset for processing.

## File Descriptions

| File Name                                          | Type   | Description                                                   |
|----------------------------------------------------|--------|---------------------------------------------------------------|
| `00_zonal_stats_processed_data.gpkg`               | Vector | Polygon layer of 200m grids, processed from the `00_zonal_stats_processed_data` folder. |
| `building_footprints.tif`                          | Raster | Dissolved building footprints polygon data.                             |
| `dispute_area.geojson`                             | Vector | Polygon representing dispute areas.                           |
| `gangs_territories.gpkg`                           | Vector | Polygon boundaries of crime gang territories.                 |
| `isp_crime_cisp.csv`                               | CSV    | Monthly crime data by police unit (CISP).                     |
| `landuse.gpkg`                                     | Vector | Land use polygons, including favela and urban areas.          |
| `military_police_battalions.gpkg`                  | Vector | Points representing military police stations.                 |
| `osm_roads.gpkg`                                   | Vector | OpenStreetMap road data.                                      |
| `osm_roads_10m_buffer.gpkg`                        | Vector | OSM road segments buffered by 10m.                            |
| `pacifying_police_territories.gpkg`                | Vector | Boundaries of pacification police (UPP) territories.          |
| `perceived_crime-safety_GSV.csv`                   | Tabular| Crime safety score for each downloaded street view image      |
| `policestations.gpkg`                              | Vector | Points representing police stations.                          |
| `rio_de_janeiro.osm.gz`                            | OSM    | OSM data for Docker.                                          |
| `schools_osm.gpkg`                                 | Vector | OSM school location points.                                   |
| `young_population_grid.gpkg`                       | Vector | Filtered grid data showing the average number of young people (ages 5 to 19), processed from the `00_zonal_stats_processed_data` folder. |

The data is not included with this repository; however, it can be requested directly from the author.