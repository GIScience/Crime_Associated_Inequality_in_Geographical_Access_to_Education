# Overview
This folder contains data generated from the [`03_routing`](../../../scripts/03_routing/) processing and analysis scripts.

## File Descriptions

| File Name               | Type   | Description |
|-------------------------|--------|-------------|
| `csv_factor_0.0`        | Folder (.csv files) | Contains tabular files with short route data line segments for each route ID from ORS. |
| `csv_factor_1.0`        | Folder (.csv files) | Contains tabular files with crime-conscious route data line segments for each route ID from ORS. |
| `route_data_*.csv`      | Tabular | Routing data files with varying weights, ranging from 0.1 to 1.0. |

### **Notes**
- The `route_data_*.csv` files represent a collection of  separate Tabular files, each named according to its respective weight factor (e.g., `route_data_factor_0.1.csv`, `route_data_factor_0.2.csv`, ..., `route_data_factor_1.0.csv`).
- The results in both `csv_factor_0.0` and `csv_factor_1.0` folders are generated based on ORS calculations. A few Tabular files are uploaded in each folder as examples.
