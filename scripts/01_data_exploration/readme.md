## Overview

This folder contains Jupyter Notebooks for analyzing, exploring, and acquiring various input data.

The repository includes the following files:

1. **ACLED Data**:
   - **`armed_conflict_location_and_event_project_map_south_america.ipynb`**: Downloads, explores, and saves data from the Armed Conflict Location & Event Data Project (ACLED) related to armed violence in South America. The processed data is saved in the intermediate output folder, organized by different armed violence events. [*]

2. **Fogo Cruzado Data**:
   - **`fogo_cruzado_data.ipynb`**: Analyzes data from the Fogo Cruzado data portal, focusing on 'shootings' point locations. Results are saved in the intermediate output folder. [*]

3. **ISP Crime Data**:
   - **`isp_data.ipynb`**: Processes and visualizes crime data from the ISP Dados platform, including monthly historical statistics by police station area.

4. **Mapillary Data**:
   - **`mapillary_point_data.ipynb`**: Explores Mapillary data, extracting 'street light' and 'CCTV camera' point locations from their API. The results are saved in the intermediate output folder. [*]

5. **Google Street View Images Prediction**:
   - **`process_GSV_images.ipynb`**: Analyzes CSV data of safety scores from Google Street View images predictions and maps them as actual points.


[*] Indicates that the notebook requires an API key for accessing its respective dataset.

## Further Steps

For additional analysis and processing, refer to the [02_street_crime_index](../02_street_crime_index) directory.
