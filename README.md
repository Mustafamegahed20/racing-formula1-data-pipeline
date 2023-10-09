# Formula 1 Racing Data Pipeline
![SI202111130438_news](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/4e2abd7f-3068-4124-a014-c7f8e2b5c1d1)
# Summary 
  Design and Orchestrate a Data Pipeline using Databricks and Azure DataFactory to perform analysis and visualization on Formula 1 race results.
  
# Project Requirements
### Data Ingestion Requirements:
- Ingest All 8 files into the data lake.
- Ingested data must have audit columns.
- Ingested data must be stored in columnar format (i.e., Parquet).
- Ingestion logic must be able to handle incremental load (Results, PitStopes, LapTimes, Qualifying).

### Data Transformation Requirements:
- Join the key information required for reporting to create a new table.
- Transformed tables must have audit columns.
- Transformed data must be stored in columnar format (i.e., Parquet).
- Transformation logic must be able to handle incremental load.

### Reporting Requirements:
- Drivers Standings.
- Constructors Standings.
  
### Analysis Requirements:
- Dominant Drivers.
- Dominant Teams.
- Visualize the outputs.
- Create Databricks Dashboards. 

### Scheduling Requirements:
- Scheduled to run every Sunday 10PM.
- Scheduling Requirements.
- Ability to monitor pipelines.
- Ability to re-run failed pipelines.
- Ability to set-up alerts on failures.

# Tools

- [Python](https://www.python.org/)
- [PySpark](https://spark.apache.org/docs/latest/api/python/)
- [Azure Databricks](https://azure.microsoft.com/en-us/products/databricks/)
- [Azure Data Factory (ADF)](https://azure.microsoft.com/en-us/products/data-factory)
- [Azure Data Lake Storage Gen2 (ADLS)](https://azure.microsoft.com/en-us/solutions/data-lake/)
- [Delta Lake](https://learn.microsoft.com/en-us/azure/databricks/delta/)
  
# Data Source 

  Data for all Formula 1 races since the 1950s is sourced from the Ergast Developer API, an open-source API available at [Ergast Developer API](http://ergast.com/mrd/). The database's structure is visually represented in  ER Diagram, and a detailed explanation can 
  be found in [Database User Guide](http://ergast.com/docs/f1db_user_guide.txt)
  ![ERDiagram](http://ergast.com/images/ergast_db.png)

### Types of files and data used in the project are listed below:

| Data Type       | File Type               | 
|-----------------|-------------------------|
| Circuits        | CSV                     | 
| Races           | CSV                     | 
| Constructors    | JSON (Single-line)      | 
| Results         | JSON (Single-line)      | 
| Drivers         | JSON (Nested)           | 
| Pitstops        | JSON (Multi-line)       |
| Lap Time        | CSV (Split)             |
| Qualifying      | JSON (Multi-line)       | 

# Data Pipeline
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/17f37438-3505-499a-85a0-1de79fa79ab3)

# Architecture

The solution used in this project is based on the ["Modern analytics architecture with Azure Databricks"](https://learn.microsoft.com/en-us/azure/architecture/solution-ideas/articles/azure-databricks-modern-analytics-architecture) from the Azure Architecture Center:
<p align="center">
  <img src="https://learn.microsoft.com/en-us/azure/architecture/solution-ideas/media/azure-databricks-modern-analytics-architecture-diagram.png" width="70%" height="70%" />
</p>

# Project Steps 
### 1- Create Azure storage and Databrick workspace. Ensure you enable ADLS Gen 2 and create 3 containers , corresponding to 3 layers of Modern analytics architecture with Azure Databricks data pipeline model: Bronze, Silver and Gold.
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/e3583976-69df-4646-a044-42d9c53ca0ae)
### 2-Ingest the Data By mounting Databricks to ADLS and loading source data to the raw container and then make some basic transfomation using pyspark and databricks and ingest it to the processed container and make data pipline of this using azure data factory
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/694f155a-4be6-48fe-8498-d4b2b6e4ba55)
### 3- Now we have all processed files in Parquet format with proper schema. The next step is to build a presentation layer to extract data based on business requirements.making data piplines by azure data factory
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/5627a995-2011-4a33-b698-c4307796b046)
### 4. A process pipeline has been devised to execute two distinct sub-pipelines for the ingestion and transformation of Formula 1 Racing data. This structure is designed to orchestrate the overall workflow efficiently. Additionally, triggers have been implemented to initiate and automate the execution of these sub-pipelines.
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/0d6ab2af-e514-4688-81a9-1b3e239d9ab2)


### 5. Make visualization using databricks 
#### Dominant Divers
![dominant_drivers](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/d1b09865-25c6-4b80-9b1b-115b59a8bb11)
#### Dominant Teams
![dominant_teams](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/c2ea3164-b0d9-4559-a018-df02c35c9c89)
