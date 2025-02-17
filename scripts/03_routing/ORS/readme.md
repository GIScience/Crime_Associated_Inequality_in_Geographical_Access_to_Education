# Crime Safety OpenRouteService Setup

## Prerequisites

- Docker installed on your system.
- Custom csv file:
  - Use the [crime_index_street.csv](../../../Data/intermediate_output/crime_index_street.csv) file from the [03_crime_index_road_segments](../../02_street_crime_index/03_crime_index_road_segments.ipynb) notebook.
  - This file contains the OSM ID and its respective crime index value.
- Custom OSM file:
  - Use the [rio_de_janerio.osm.gz](../../../Data/input_data/rio_de_janerio.osm.gz) file, which is the OSM file for Rio de Janeiro.
  - Alternatively, you can download  OSM file from [Geofabrik](https://download.geofabrik.de/) and preprocess it using [Osmconvert](https://wiki.openstreetmap.org/wiki/Osmconvert) or [Osmosis](https://wiki.openstreetmap.org/wiki/Osmosis).


## Installation

1. Change to the directory where you want to install your local OpenRouteService and create the necessary directories:
    ```shell
    mkdir -p ors-docker/config ors-docker/elevation_cache ors-docker/graphs ors-docker/files ors-docker/logs
    ```

2. Download the Docker Compose file:
    ```shell
    wget https://github.com/GIScience/openrouteservice/releases/download/v8.0.0/docker-compose.yml
    ```

3. Start OpenRouteService in the background:
    ```shell
    docker compose up -d
    ```

    This will pull the OpenRouteService Docker image of the selected version and start it up using an example setup and the provided test OSM file for Heidelberg/Germany and surrounding area.

4. Stop the container:
    ```shell
    docker compose down
    ```

5. Copy the following required files to the `ors-docker/files` directory:
    - [crime_index_street.csv](../../../Data/intermediate_output/crime_index_street.csv)
    - [rio_de_janerio.osm.gz](../../../Data/input_data/rio_de_janerio.osm.gz)

6. Modify the `docker-compose.yml` file in the `ors-docker/config` directory by adding the following configuration:
    ```yml
    ors:
      engine:
        source_file: /home/ors/files/rio_de_janerio.osm.gz
        profiles:
          walking:
            enabled: true
            ext_storages:
              csv:
                filepath: /home/ors/files/crime_index_street.csv
    ```

    This configuration enables the walking profile and loads the custom CSV and OSM files.

7. Delete the contents inside the `elevation_cache` and `graphs` directories, to rebuild  everthing:
    ```sh
    rm -rf ors-docker/elevation_cache/*
    rm -rf ors-docker/graphs/*
    ```

8. Start OpenRouteService again:
    ```shell
    docker compose up
    ```

## Verify ORS is Running

Wait for ORS to build graphs; it may take some time if it is a larger region. Verify that ORS is running by executing:
```sh
curl http://localhost:8080/ors/v2/health
```

You should see a response like:
```json
{"status":"ready"}
```