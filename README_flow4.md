# Data Anomaly Generation and Analysis Script

This Python script demonstrates data manipulation, anomaly generation, and visualization using BigQuery and Gemini with built in python notebook. The script is designed to work with event data stored in Google BigQuery.

## Key Features

- Built-in Jupyter notebook compatibility
- Gemini code assist integration
- Visualization recommendations
- Anomaly detection visualization
- BigQuery integration for data storage and retrieval

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

## User Flow 4: Python Notebook

### 1. BigQuery Data Loading
- Loads event data from BigQuery table `data-cloud-demo5.next25_demo_ds.events_test` using built in python library
- To use Code Assist prompt `Load  table_id = "data-cloud-demo5.event_test"`: Create a new Code cell -> click Gemini Icon -> Generate Code -> Paste the prompt -> Enter
- Preview table using `df.head(3)`, then clikc the `Suggest charts` icon on the right of the table to see recommended charts

### 2. Data Transformation
- Converts timestamp column to datetime64 format
- Creates new temporal features:
  - Year
  - Month
  - Day
  - Hour
- Use Code Assist prompt `extract all columns, in addition, create new column for year, month, date, hours from data-cloud-demo5.event_test`

### 3. Visualization
- Creates scatter plots of bytes transferred over time
- Generates heatmaps to visualize data distribution
- Identifies anomalous patterns in the data

## Notes

- The script specifically creates anomalies for user_id 50
- Anomaly threshold is set at 1.2e8 bytes transferred
- Visualization includes both scatter plots and heatmaps for better pattern recognition
