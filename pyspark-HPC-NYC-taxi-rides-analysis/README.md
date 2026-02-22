# High Performance Computing: NYC Taxi Rides Analysis

## Overview

This project develops a high-performance computing framework using **Apache Spark (PySpark)** to analyze massive datasets of New York City taxi rides (over 41 million records for the year 2024).

The objective is to leverage distributed computing to process large-scale data efficiently and extract key urban mobility insights, including:
- Average speed of taxis in terms of the hour of the day.
- Identification of the most common taxi trips (routing patterns).
- Analysis of financial records (fare amounts, tips, passengers, etc.).

## Project Structure

- `data/` — Large-scale dataset in .csv format (e.g., `taxi_zone_lookup` )  
- `notebook/` — Jupyter Notebooks containing the PySpark implementation (`HPC_NYC_taxi_rides_analysis`)    
- `requirements.txt` — Python and Big Data dependencies  
- `README.md` — Project description and instructions

## Methodology

### 1. Big Data Environment Setup
- Initialization of `SparkSession` and `SparkContext` (configured for in-memory local cluster processing).
- Ingestion of large Parquet files, applying schema inference and malformed row dropping.

### 2. Data Preprocessing & Cleaning
- Conversion of datetime features (`tpep_pickup_datetime`, `tpep_dropoff_datetime`) to UNIX timestamps for mathematical operations.
- Filtering of invalid records (e.g., trips with distance $\le 0$, or identical pickup/dropoff times).
- Removal of physical outliers (e.g., trips under 30 seconds or speeds exceeding 150 km/h).

### 3. Distributed Data Processing
- Utilization of Spark **Resilient Distributed Datasets (RDDs)** and lambda functions for fast transformations (`map`, `filter`).
- Calculation of derived metrics (trip duration in seconds, speed conversion from miles to km/h).
- Aggregation of massive data using `reduceByKey` (e.g., calculating total speed and count of trips per hour).

### 4. Exploratory Data Analysis & Benchmarking
- Analysis of traffic dynamics and economic efficiency (e.g., average income per minute).
- Execution time tracking to benchmark computational performance.
- Comparison of performance between Spark RDDs, DataFrames, and native SQL queries.

### 5. Data Visualization
- Extraction of aggregated results to the driver node using `collect()`.
- Graphical representation of the findings (e.g., Economic efficiency per hour, Average speed by hour) using Python plotting libraries.


## Output

The project produces:

1. A fully documented Jupyter Notebook containing:
   - Big data preprocessing pipelines using PySpark.
   - Computational time measurements for performance evaluation.
   - Comprehensive exploratory data analysis and visual plots.

2. A scalable data pipeline capable of handling and aggregating tens of millions of rows efficiently.