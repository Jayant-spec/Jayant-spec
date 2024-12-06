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

<img width="1099" alt="Screenshot 2024-12-05 at 1 32 50 AM" src="https://github.com/user-attachments/assets/2a31ffd2-7b49-4855-98bc-051c9e267c7c">

---

## Descriptive Analysis

The data extracted from the open source is analyzed, comparing bikeway years of construction with the maximum speed limit. Below are the findings:

- **1986**: Maximum speed limit is 50.
- **1990**: Maximum speed limit is 60.
- **1993**: Maximum speed limit is 50.
- **1994**: Maximum speed limit is 30.

Our purpose is to ingest the data into the AWS platform and reproduce similar results as shown below. The analysis will help understand patterns in speed limits over the years.

<img width="1100" alt="Screenshot 2024-12-05 at 1 33 00 AM" src="https://github.com/user-attachments/assets/fd5a9eab-2c7d-4469-a87d-2e6ae47f025e">

---

## Data Analytical Platform

### Workflow Description

The following steps outline the data processing workflow:

1. **Raw Bucket**: Data ingestion.
2. **Data Brew**: Profiling and cleaning.
3. **Transformed Bucket**: Storing cleaned data.
4. **ETL Pipeline**: Extract, transform, and load processes.
5. **Curated Bucket**: Storing results in system and user folders.

<img width="1073" alt="Screenshot 2024-12-05 at 1 33 08 AM" src="https://github.com/user-attachments/assets/893bc178-983a-4e76-bd2c-68432e127ce6">


---

## Data Storage

Three buckets are created in AWS S3 to store:
1. Raw data.
2. Transformed data.
3. Curated data.

<img width="1106" alt="Screenshot 2024-12-05 at 1 33 19 AM" src="https://github.com/user-attachments/assets/f789af07-07a4-4405-b379-7c246cd5cdea">

---

## Data Ingestion

The extracted Excel data is uploaded directly into the raw bucket using AWS's upload functionality.

<img width="1113" alt="Screenshot 2024-12-05 at 1 33 27 AM" src="https://github.com/user-attachments/assets/50376b8d-3a58-48c2-81ec-7a717e03e404">

---

## Data Profiling

Data profiling ensures data quality and identifies required changes. The profiling process is executed in AWS Glue DataBrew by creating a dataset and running the profiling process. The results are stored in the transformed bucket.

<img width="1093" alt="Screenshot 2024-12-05 at 1 33 41 AM" src="https://github.com/user-attachments/assets/2bd573d8-70b2-464b-9f0b-acaeb80e1cc1">

---

## Data Cleaning

Data cleaning involves:
- Handling missing data.
- Removing duplicates.
- Resolving formatting issues.

Unnecessary columns are deleted, and the cleaned data is stored in the curated bucket.

<img width="1086" alt="Screenshot 2024-12-05 at 1 33 48 AM" src="https://github.com/user-attachments/assets/ca7c28a4-feb8-46c2-a861-3f398d6f7b93">


---

## ETL Pipeline Design

The ETL (Extract, Transform, Load) pipeline design involves:
1. Fetching cleaned data from the transform bucket.
2. Removing unnecessary columns.
3. Grouping years of construction and aggregating maximum speed limits.

The final results are stored in the curated bucket in system and user folders.

<img width="1078" alt="Screenshot 2024-12-05 at 1 33 54 AM" src="https://github.com/user-attachments/assets/3f048f2f-0b6c-4aaa-89d8-c270c5bc5d37">
<img width="1086" alt="Screenshot 2024-12-05 at 1 34 01 AM" src="https://github.com/user-attachments/assets/4058e7dc-87e1-428c-b7d4-a5491783aead">

<img width="1083" alt="Screenshot 2024-12-05 at 1 34 08 AM" src="https://github.com/user-attachments/assets/5fd5528f-6089-41d0-a82a-52cffd64a196">
<img width="1087" alt="Screenshot 2024-12-05 at 1 34 16 AM" src="https://github.com/user-attachments/assets/50a07527-da2c-4a28-96e7-98f2e013100d">
<img width="718" alt="Screenshot 2024-12-05 at 1 34 28 AM" src="https://github.com/user-attachments/assets/069d1536-6ff5-40af-a622-241ea18520af">

---

## Exploratory Analysis

We extended the analysis by adding a new variable, **count of bike lanes**, to study correlations between maximum speed limits and bike lane counts:

- **1986**: 19 bike lanes; maximum speed 50.
- **1990**: 79 bike lanes; maximum speed 60.
- **1993**: 22 bike lanes; maximum speed 50.

Urban planning initiatives might explain spikes in bike lane counts, which potentially reduce accidents (Pucher & Buehler, 2012).

<img width="771" alt="Screenshot 2024-12-05 at 1 34 36 AM" src="https://github.com/user-attachments/assets/5631e0cd-08be-47ab-af58-b34086b4492b">


---

## Pipeline Design for Exploratory Analysis

The pipeline design includes:
1. Grouping years of construction with count aggregation.
2. Demonstrating data division by primary key and join functionality.

<img width="770" alt="Screenshot 2024-12-05 at 1 34 41 AM" src="https://github.com/user-attachments/assets/46c01bb2-2249-4d9b-b0d5-7696cb945617">


---

## Results

The results are stored and visualized as per the design.

<img width="762" alt="Screenshot 2024-12-05 at 1 34 50 AM" src="https://github.com/user-attachments/assets/77318f68-0026-44aa-90eb-01f7ac3b0d18">
<img width="744" alt="Screenshot 2024-12-05 at 1 34 57 AM" src="https://github.com/user-attachments/assets/65b00cad-1d68-4491-b10e-2dd308703cea">
<img width="549" alt="Screenshot 2024-12-05 at 1 35 05 AM" src="https://github.com/user-attachments/assets/ab2a48e8-9135-4f01-a2dd-6ae7ab16b81a">

---

## References

- Pucher, J., & Buehler, R. (2012). City cycling. *Transport Reviews, 33*(1), 9–36. [https://doi.org/10.1080/01441647.2012.725361](https://doi.org/10.1080/01441647.2012.725361)
- Bikeways. City of Vancouver Open Data Portal. (2023, December 25). [https://opendata.vancouver.ca/explore/dataset/bikeways/analyze](https://opendata.vancouver.ca/explore/dataset/bikeways/analyze)




