# Overview
This folder contains data, which is saved from the [`02_street_crime_index`](../../scripts/02_street_crime_index/) processing and analysis.

## File Descriptions
| File Name                              | Type   | Description                                                   |
|----------------------------------------|--------|---------------------------------------------------------------|
| `crime_counts_per_cisp.csv`            | Tabular| Crime counts for each CISP (police unit) region.       |
| `crime_index_grid.gpkg`                | Vector | Crime data redistributed to 200m grid cells.                  |
| `crime_index_street.csv`               | Tabular| Crime index for OSM road segments.                            |
| `crime_index_street.gpkg`              | Vector | Crime index for OSM road segments with buffered geometry.     |
| `crime_index_zonal_statistics.gpkg`     | Vector | Crime data calculated from zonal statistics analysis on crime data in 200m grid cells. |
| `route_segment_type.gpkg`              | Vector | Categorized route segment lines from the ORS routing.         |