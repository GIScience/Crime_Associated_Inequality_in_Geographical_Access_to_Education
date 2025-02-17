## Overview

This directory contains Jupyter Notebooks focused on crime-conscious routing and routing analysis. The notebooks aim to compare shorter and safer routes, covering aspects of route creation, visualization, and categorization to ensure crime-conscious travel to the closest school.

### Requirements 

OpenRouteService must be running on localhost. Ensure OpenRouteService is properly set up before running these notebooks. For detailed setup instructions, refer to the [OpenRouteService Setup](ORS/README.md) guide.

### 01 Routing for Young Population

#### Input
- **Preliminary Steps**: Processed the `00_input_200m_centrality_grid.gpkg` file from the [00_zonal_stats_processed_data](../../data/01_input_data/00_zonal_stats_processed_data) directory in QGIS, resulting in the `young_population_grid.gpkg` file saved in the [01_input_data](../../data/01_input_data) directory.
  <details>
  <summary><b>Fields description</b></summary>

  | Fields            | Methodology                                      |
  |-------------------|--------------------------------------------------|
  | `total_population`| Maximum count of people aged 5 to 19             |

  </details>

- **Schools Data**: `schools_osm.gpkg` in the [01_input_data](../../data/01_input_data) directory
- **Dispute Groups**: `dispute_area.geojson` in the [01_input_data](../../data/01_input_data) directory

#### Processing
- **[`01_routing.ipynb`](../03_routing/01_routing.ipynb)**: Develops routes with a strong emphasis on safety and crime awareness. This notebook filters out irrelevant routes and processes route segments for further analysis, saving and retrieving them both separately and together.

#### Output
- **Route Data**: `route_data.csv` files with different weights in the [routing_output](../../data/02_intermediate_output/routing_output) directory
- **Short Routes**: Directory `short_route_0.0` containing short route line segments in CSV format in the [routing_output](../../data/02_intermediate_output/routing_output) directory
- **Crime-Conscious Routes**: Directory `crime_conscious_1.0` containing crime-conscious route line segments in CSV format in the [routing_output](../../data/02_intermediate_output/routing_output) directory

### 02 Route Mapping and Plotting

#### Input
- **Route Data**: `route_data.csv` files from the routing notebook

#### Processing
- **[`02_routeplots.ipynb`](../03_routing/02_routeplots.ipynb)**: Visualizes the outcomes of routing analyses, including comparisons of different routing weights, examination of route similarities, and assessments of crime exposure through various plots.

#### Output
- **Figures**: Visualizations saved in the [03_final_figures](../../data/03_final_figures) directory

### 03 Route Segment Categorization

#### Input
- **Short Routes**: Directory `csv_factor_0.0` with short route data from the routing notebook
- **Crime-Conscious Routes**: Directory `csv_factor_1.0` with crime-conscious route data from the routing notebook
- **Young Population Grid**: `young_population_grid.gpkg` in the [01_input_data](../../data/01_input_data) directory

#### Processing
- **[`03_route_categorization.ipynb`](../03_routing/03_route_categorization.ipynb)**: Categorizes the route segments obtained from the routing notebook. This notebook evaluates the characteristics of these segments concerning their relevance to young populations and their safety features.

#### Output
- **Categorized Segments**: `route_segment_type.gpkg` - Road segments categorized by route type in the [02_intermediate_output](../../data/02_intermediate_output) directory
- **Figures**: Visualizations saved in the [03_final_figures](../../data/03_final_figures) directory