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

# Ingestion piplines 
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/694f155a-4be6-48fe-8498-d4b2b6e4ba55)

# Transformation piplines 
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/5627a995-2011-4a33-b698-c4307796b046)

# Pipline Process
![image](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/0d6ab2af-e514-4688-81a9-1b3e239d9ab2)

# Results
### Dominant Divers
![dominant_drivers](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/d1b09865-25c6-4b80-9b1b-115b59a8bb11)

### Dominant Teams
![dominant_teams](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/c2ea3164-b0d9-4559-a018-df02c35c9c89)



    
