# 🌍 MongoDB Geospatial Analysis with Python

This project demonstrates how to perform **geospatial data processing and spatial queries using MongoDB and Python**.
The notebook loads geographic JSON datasets into MongoDB, performs CRUD operations, and executes **distance-based spatial analysis using the Haversine formula and MongoDB geospatial queries**.

The project is implemented using **Python, MongoDB Atlas, and Jupyter Notebook**.

---

# 📌 Project Overview

Geospatial data is widely used in applications such as:

* Navigation systems
* Location-based services
* Logistics optimization
* Urban planning
* Environmental analysis

This project shows how to:

* Store **geographic datasets in MongoDB**
* Perform **CRUD operations**
* Run **geospatial queries**
* Calculate **distances between geographic coordinates**
* Identify **nearby geographic features**

---

# 🛠️ Tech Stack

**Programming Language**

* Python

**Database**

* MongoDB Atlas

**Libraries**

* `pymongo`
* `shapely`
* `math`
* `json`
* `urllib`

**Environment**

* Jupyter Notebook

---

# 📂 Project Structure

```
MongoDB-Geospatial-Analysis
│
├── spatial.ipynb        # Main notebook containing geospatial analysis
├── datasets/            # JSON geospatial datasets (optional)
└── README.md
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/mongodb-geospatial-analysis.git
cd mongodb-geospatial-analysis
```

Install the required Python libraries:

```bash
pip install pymongo
pip install shapely
```

---

# 🔑 MongoDB Setup

1. Create a **MongoDB Atlas cluster**
2. Obtain your **connection URI**
3. Replace credentials in the notebook:

```python
username = "YOUR_USERNAME"
password = "YOUR_PASSWORD"
cluster_url = "YOUR_CLUSTER_URL"
database_name = "YOUR_DATABASE"
```

Example MongoDB connection:

```python
from pymongo.mongo_client import MongoClient
client = MongoClient(uri)
```

---

# 📊 Data Ingestion

The project loads **JSON geospatial datasets** into MongoDB collections.

Example document format:

```json
{
  "name": "Example Location",
  "coordinates": [139.6917, 35.6895],
  "type": "Point"
}
```

Datasets can include:

* Airports
* Railway stations
* Ports
* Rivers and canals
* Built-up areas

---

# 🔍 CRUD Operations

The notebook demonstrates basic MongoDB database operations:

### Create

Insert new geographic features into collections.

### Read

Retrieve geographic data based on filters.

### Update

Modify attributes of existing records.

### Delete

Remove records from collections.

Example:

```python
db["airp_jpn"].insert_one(new_airport)
```

---

# 📍 Geospatial Queries

MongoDB provides powerful **geospatial operators**.

Example query to find nearby features:

```python
query = {
  "coordinates": {
    "$geoWithin": {
      "$centerSphere": [[lon, lat], radius]
    }
  }
}
```

This allows the system to retrieve all features within a given geographic radius.

---

# 📏 Distance Calculation (Haversine Formula)

The project calculates distances between coordinates using the **Haversine formula**, which measures the great-circle distance between two points on Earth.

Formula:

```
a = sin²(Δφ/2) + cos φ1 ⋅ cos φ2 ⋅ sin²(Δλ/2)
c = 2 ⋅ atan2( √a, √(1−a) )
d = R ⋅ c
```

Where:

* `R = 6371 km` (Earth radius)

Example implementation:

```python
def haversine(lon1, lat1, lon2, lat2):
    R = 6371
```

This function is used to compute distances for spatial analysis.

---

# 📌 Example Analyses in the Notebook

The notebook performs several spatial analyses:

### ✈️ Airport Data Operations

* Insert and retrieve airport records

### 📍 Nearby Feature Detection

* Find geographic features within a **50 km radius**

### 🌊 River & Canal Analysis

* Identify nearby LineString features

### 🚆 Nearest Railway Stations

* Compute and list **10 closest railway stations** to a given point

### ⚓ Port Proximity Analysis

* Find ports within a specified distance

### 🏙 Built-up Area Analysis

* Identify nearby populated areas and display population information

---

# ▶️ Running the Project

Start Jupyter Notebook:

```bash
jupyter notebook spatial.ipynb
```

Then run the cells sequentially to:

1. Install dependencies
2. Connect to MongoDB
3. Load JSON data
4. Perform CRUD operations
5. Execute geospatial queries
6. Compute distances using the Haversine formula

---

# 🚀 Possible Improvements

Future enhancements could include:

* Adding **MongoDB geospatial indexes**
* Visualizing locations using **Folium or Plotly maps**
* Building a **Flask / FastAPI API for spatial queries**
* Creating **interactive geospatial dashboards**
* Integrating **real-time GPS datasets**

---

# 📚 Learning Outcomes

Through this project you will learn:

* How to use **MongoDB with Python**
* Handling **NoSQL geospatial data**
* Performing **geospatial queries**
* Implementing **distance calculations**
* Conducting **location-based analytics**

---

# 📜 License

This project is released under the **MIT License**.

---
