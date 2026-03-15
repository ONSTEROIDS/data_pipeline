# Server Monitoring Data Engineering Pipeline

This project demonstrates a simple end-to-end data engineering pipeline built using Azure services to monitor virtual server performance.  
The pipeline ingests server log data, processes it using Databricks, and visualizes the results in a Power BI dashboard.

The goal of the project is to analyze server performance metrics and help identify system health issues such as high CPU usage, downtime, or abnormal network activity.

---

## Architecture

The pipeline follows this flow:

CSV Server Logs  
→ Azure Data Lake Storage  
→ Azure Data Factory Pipeline  
→ Azure Databricks (Data Processing)  
→ Transformed Dataset stored in Azure Data Lake  
→ Power BI Dashboard


## Technologies Used

This project uses the following tools and services:

- Azure Data Lake Storage Gen2  
- Azure Data Factory  
- Azure Databricks  
- Apache Spark / PySpark  
- Power BI  

These tools are commonly used together in modern cloud data engineering pipelines.

---

## Dataset Description

The dataset contains server monitoring information.

Some important fields in the dataset include:

- **Server_ID** – Unique identifier of the server  
- **Hostname** – Name of the server  
- **IP_Address** – Server network address  
- **OS_Type** – Operating system running on the server  
- **Server_Location** – Geographic location of the server  
- **CPU_Utilization** – CPU usage percentage  
- **Memory_Usage** – Memory consumption of the server  
- **Network_Traffic_In_MB** – Incoming network traffic  
- **Network_Traffic_Out_MB** – Outgoing network traffic  
- **Downtime_Hours** – Total downtime recorded for the server  
- **Server_Health_Status** – Health classification (Healthy / Warning / Critical)

This data is used to analyze server performance and identify potential issues.

---

## Data Pipeline Workflow

### 1. Data Ingestion

The raw server log file in CSV format is uploaded to Azure Data Lake Storage.  
Azure Data Factory is used to create a pipeline that reads the file and manages the data ingestion process.

---

### 2. Data Storage

The dataset is stored in Azure Data Lake Storage which acts as the central storage layer for the pipeline.

This allows the data to be accessed by processing tools like Databricks and analytics tools like Power BI.

---

### 3. Data Transformation

Azure Databricks is used to process the server log data using PySpark.

The transformation process includes:

- Reading the raw CSV data from Azure Data Lake
- Cleaning the dataset
- Removing duplicate records
- Validating data values
- Generating performance metrics

The processed dataset is written back to Azure Data Lake as a transformed dataset.

---

### 4. Data Visualization

Power BI connects to the transformed dataset to create an interactive monitoring dashboard.

The dashboard helps visualize server performance and operational metrics.

---

## Power BI Dashboard Insights

The dashboard provides several useful insights such as:

- Server health distribution  
- Average CPU utilization by server  
- Network traffic analysis  
- Downtime per server  
- Overall system availability KPI  


---

## Project Outcome

This project shows how Azure services can be used together to build a basic monitoring pipeline for server performance data.

By processing raw logs and visualizing the results in Power BI, the system provides useful insights that can help improve system reliability and performance.
