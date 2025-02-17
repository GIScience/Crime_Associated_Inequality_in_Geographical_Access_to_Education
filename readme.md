# Crime-Associated Inequality in Physical Access to Education: Insights from the Municipality of Rio de Janeiro

[![DOI](https://zenodo.org/badge/934192679.svg)](https://doi.org/10.5281/zenodo.14884889)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Abstract

**Background**: Education is a fundamental right, supported by initiatives like Education for All (EFA) and the Millennium Development Goals (MDGs). Despite progress, full educational access remains challenging, particularly in highly criminal areas.

**Methods**: This paper examines the impact of crime on school access in the municipality of Rio de Janeiro. Using ancillary data and geospatial artificial intelligence (GeoAI), we downscaled official police crime records to street level. By considering different levels of crime tolerance in school path choices, we simulated how crime can force students to walk longer distances to avoid violence.

**Findings**: Our findings indicate a 48.60% average increase in travel time to the closest school for students whose shortest routes intersect with high-crime areas. This adjustment reduces mean crime exposure by 44.10% and maximum exposure by 81.94%. Both individual crime risk aversion and no-go areas of criminal disputes significantly (p ≤ 0.05) impacted educational access. Estimating street-level crime exposure was challenging due to spatial bias in official and crowdsourced crime reporting.

**Interpretation**: These methods and insights are crucial for improving educational access in high-crime areas, providing a better understanding of barriers to equitable education, and being applicable to other cities and accessibility studies for various societal needs.


<!-- 
Education is a fundamental right, supported by initiatives like Education for All (EFA) and the Millennium Development Goals (MDGs). Despite progress, full educational access remains challenging, particularly in highly criminal areas. This paper examines the impact of crime on school access in the municipality of Rio de Janeiro. Using ancillary data and geospatial artificial intelligence (GeoAI), we downscaled official police crime records to street level. By considering different levels of crime tolerance in school path choices, we simulated how crime can force students to walk longer distances to avoid violence. Our findings indicate a 48.60% average increase in travel time to the closest school for students whose shortest routes intersect with high-crime areas. This adjustment reduces mean crime exposure by 44.10% and maximum exposure by 81.94%. Both individual crime risk aversion and no-go areas of criminal disputes significantly (p ≤ 0.05) impacted educational access. Estimating street-level crime exposure was challenging due to spatial bias in official and crowdsourced crime reporting. These methods and insights are crucial for improving educational access in high-crime areas, providing a better understanding of barriers to equitable education, and being applicable to other cities and accessibility studies for various societal needs. -->


## Getting Started

Follow these steps to set up the project on your local machine:

## Getting Started

1. **Clone the Repository:**
   ```bash
   git clone https://gitlab.gistools.geog.uni-heidelberg.de/rmuthusamy/safety-routing.git
   ```
2. **Create the Environment:**
   ```bash
    conda env create -f environment.yml
    ```

3. **Activate the Environment:**
   ```bash
    conda activate crime_routing
    ```

## Data Folder Structure

The project's data folder structure is organized as follows:
- **[01_input_data](/data/01_input_data):** Contains necessary input data and processed zonal statistics data for the project.
- **[02_intermediate_output](/data/02_intermediate_output):** Saves the output from the script processing and analysis.
- **[03_final_figures](/data/03_final_figures):** Contains the final figures generated from the analysis.

## Scripts Folder Structure

The scripts folder contains notebooks for different stages of the project. Run them sequentially based on their file names:
- **[01_data_exploration](/scripts/01_data_exploration):** Notebooks for data acquisition and exploration.
- **[02_street_crime_index](/scripts/02_street_crime_index):** Notebooks for crime data analysis and crime safety level mapping.
- **[03_routing](/scripts/03_routing):** Notebooks for routing to the nearest schools based on crime levels using ORS.

## Data and Privacy

This project utilizes openly-available data and crowdsourced data platforms. All data used in this study is anonymized and aggregated to ensure privacy and confidentiality. The data sources include:

- Publicly available crime records from police databases.
- Crowdsourced data on urban shootings.
- Geographic data for mapping and analysis.

We adhere to strict data privacy guidelines and ensure that no personally identifiable information (PII) is used or disclosed in any part of this project.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.