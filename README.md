## Hi there 👋

I'm **Jayant Singh**, an MBA student at **UCW, Vancouver BC**.  
You can connect with me on [LinkedIn](https://www.linkedin.com/in/jayant-singh-6a3ab5125?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app).

---

## Project Introduction

The project, titled **"Analysis and Implementation of a Data Analytical Platform for Bikeway Infrastructure Using AWS"**, focuses on leveraging cloud-based technologies to analyze and optimize bikeway infrastructure data. Using a dataset sourced from the Vancouver Open Data Portal, the project employs AWS tools to ingest, profile, clean, and transform data into actionable insights. By examining the relationship between bikeway construction years, speed limits, and bike lane counts, the initiative aims to uncover trends that support urban planning and traffic management strategies. 

Through the development of an Extract, Transform, and Load (ETL) pipeline, the project ensures efficient data handling while highlighting correlations in the dataset. This analytical platform not only enhances data visualization and decision-making but also contributes to safer and more sustainable bikeway designs.

---

## Project Objectives

1. **Data Ingestion and Storage**  
   Efficiently ingest bikeway data into AWS storage buckets to organize raw, transformed, and curated datasets.

2. **Data Profiling and Cleaning**  
   Ensure the quality of the dataset by profiling and cleaning, removing redundancies, and resolving formatting issues.

3. **ETL Pipeline Implementation**  
   Design and execute an ETL pipeline to extract, transform, and load data into the curated bucket for analytical purposes.

4. **Trend Analysis**  
   Investigate trends in speed limits, construction years, and bike lane counts to derive actionable insights for urban planners.

5. **Scalable Analytical Platform**  
   Develop a scalable and reusable analytical platform using AWS services to handle similar datasets in the future.

6. **Visualization and Reporting**  
   Generate visualizations to communicate key findings effectively, aiding stakeholders in making informed decisions.

# Analysis and Implementation of a Data Analytical Platform for Bikeway Infrastructure Using AWS - Jayant

## Dataset Description

The dataset has been extracted from the Vancouver Open Data Portal in Excel (.xlsx) format. While multiple options like `.csv` and `.parquet` are available, the Excel format is more suitable for our scenario (Bikeways, 2023).

![Figure 1](#)

---

## Descriptive Analysis

The data extracted from the open source is analyzed, comparing bikeway years of construction with the maximum speed limit. Below are the findings:

- **1986**: Maximum speed limit is 50.
- **1990**: Maximum speed limit is 60.
- **1993**: Maximum speed limit is 50.
- **1994**: Maximum speed limit is 30.

Our purpose is to ingest the data into the AWS platform and reproduce similar results as shown below. The analysis will help understand patterns in speed limits over the years.

![Figure 2](#)

---

## Data Analytical Platform

### Workflow Description

The following steps outline the data processing workflow:

1. **Raw Bucket**: Data ingestion.
2. **Data Brew**: Profiling and cleaning.
3. **Transformed Bucket**: Storing cleaned data.
4. **ETL Pipeline**: Extract, transform, and load processes.
5. **Curated Bucket**: Storing results in system and user folders.

![Figure 3](#)

---

## Data Storage

Three buckets are created in AWS S3 to store:
1. Raw data.
2. Transformed data.
3. Curated data.

---

## Data Ingestion

The extracted Excel data is uploaded directly into the raw bucket using AWS's upload functionality.

![Figure 4](#)

---

## Data Profiling

Data profiling ensures data quality and identifies required changes. The profiling process is executed in AWS Glue DataBrew by creating a dataset and running the profiling process. The results are stored in the transformed bucket.

![Figure 5](#)

---

## Data Cleaning

Data cleaning involves:
- Handling missing data.
- Removing duplicates.
- Resolving formatting issues.

Unnecessary columns are deleted, and the cleaned data is stored in the curated bucket.

![Figure 6](#)

---

## ETL Pipeline Design

The ETL (Extract, Transform, Load) pipeline design involves:
1. Fetching cleaned data from the transform bucket.
2. Removing unnecessary columns.
3. Grouping years of construction and aggregating maximum speed limits.

The final results are stored in the curated bucket in system and user folders.

![Figure 7](#)
![Figure 8](#)

---

## Exploratory Analysis

We extended the analysis by adding a new variable, **count of bike lanes**, to study correlations between maximum speed limits and bike lane counts:

- **1986**: 19 bike lanes; maximum speed 50.
- **1990**: 79 bike lanes; maximum speed 60.
- **1993**: 22 bike lanes; maximum speed 50.

Urban planning initiatives might explain spikes in bike lane counts, which potentially reduce accidents (Pucher & Buehler, 2012).

![Figure 12](#)

---

## Pipeline Design for Exploratory Analysis

The pipeline design includes:
1. Grouping years of construction with count aggregation.
2. Demonstrating data division by primary key and join functionality.

![Figure 14](#)

---

## Results

The results are stored and visualized as per the design.

![Figure 15](#)

---

## References

- Pucher, J., & Buehler, R. (2012). City cycling. *Transport Reviews, 33*(1), 9–36. [https://doi.org/10.1080/01441647.2012.725361](https://doi.org/10.1080/01441647.2012.725361)
- Bikeways. City of Vancouver Open Data Portal. (2023, December 25). [https://opendata.vancouver.ca/explore/dataset/bikeways/analyze](https://opendata.vancouver.ca/explore/dataset/bikeways/analyze)


