# Data Anomaly Generation and Analysis Script

This Python script demonstrates data manipulation, anomaly generation, and visualization using BigQuery and Gemini with built in python notebook. The script is designed to work with event data stored in Google BigQuery.

## Prerequisites

You'll need:
- A Google Cloud project with BigQuery enabled
- Access to the `data-cloud-demo5` project

Create anomalous data:
- Loads event data from BigQuery table `data-cloud-demo5.next25_demo_ds.events_test`
- Creates contextual anomalies for specific user_ids:
  - Groups data by user_id
  - Calculates normal range (mean and standard deviation) for each group
  - Introduces anomalies by modifying bytes_transferred values
  - Focuses on groups with more than 240 records
  - Sets anomaly values 5-10 standard deviations from mean

## Demo

The script is divided into several main sections:

### 1. BigQuery Data Loading
- Loads event data from BigQuery table `data-cloud-demo5.next25_demo_ds.events_test` using built in python library.

### 2. Data Transformation
- Converts timestamp column to datetime64 format
- Creates new temporal features:
  - Year
  - Month
  - Day
  - Hour

### 3. Visualization
- Creates scatter plots of bytes transferred over time
- Generates heatmaps to visualize data distribution
- Identifies anomalous patterns in the data

## Key Features

- Built-in Jupyter notebook compatibility
- Gemini code assist integration
- Visualization recommendations
- Anomaly detection visualization
- BigQuery integration for data storage and retrieval

## Notes

- The script specifically creates anomalies for user_id 50
- Anomaly threshold is set at 1.2e8 bytes transferred
- Visualization includes both scatter plots and heatmaps for better pattern recognition
