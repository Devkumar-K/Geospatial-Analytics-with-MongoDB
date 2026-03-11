# Spatial Analysis of Japan

This project performs geospatial analysis on various features across Japan, including airports, railway stations, ports, water bodies, and administrative boundaries. It leverages **MongoDB Atlas** for spatial indexing and querying, and **Python** for data processing and visualization.

## Project Overview

The core of this project is the `spatial.ipynb` notebook, which demonstrates:
- Connecting to a MongoDB Atlas cluster.
- Loading GeoJSON-like data from JSON files into MongoDB.
- Creating `2dsphere` spatial indexes for efficient geographic queries.
- Implementing distance calculations using the **Haversine formula**.
- Performing geospatial queries (e.g., finding features within a radius).
- Visualizing spatial data on interactive maps using **Folium**.

## Prerequisites

To run the notebook, you need the following Python libraries installed:

```bash
pip install shapely pymongo folium
```

You also need a **MongoDB Atlas** account and a cluster configured.

## Dataset

The project uses a variety of datasets located in the `dataset/` directory:
- `airp_jpn.json`: Airports
- `rstatp_jpn.json`: Railway stations
- `portp_jpn.json`: Ports
- `inwatera_jpn.json` & `riverl_jpn.json`: Water bodies and rivers
- `polbnda_jpn.json`: Administrative boundaries (Prefectures/Districts)
- `builtupp_jpn.json`: Built-up areas
- And others (roads, ferries, etc.)

## Project Structure

1.  **Installation & Connection**: Initial setup for libraries and MongoDB Atlas connection.
2.  **Data Loading**: Scripts to parse JSON files and upload them to MongoDB with spatial indexing.
3.  **Helper Functions**: Implementation of the Haversine formula and distance helpers.
4.  **CRUD Operations**: Basic database operations on spatial collections.
5.  **Geospatial Queries**:
    *   Finding features within a specific radius using MongoDB's `$geoWithin` and `$centerSphere`.
    *   Manual distance-based filtering and sorting for complex geometries.
6.  **Visualization**: Generating interactive Folium maps to display airports and stations.

## Usage Instructions

1.  **Configure MongoDB**: Update the connection string (`uri`) in the notebook with your Atlas credentials.
2.  **Upload Data**: Run the loading cells to populate your `GEO_DB` database with the provided JSON files.
3.  **Execute Analysis**: Run the query cells to find nearby features relative to specific coordinates (e.g., Tokyo Station, Sapporo).
4.  **View Maps**: The final cells generate an interactive map of Japan with plotted features.
