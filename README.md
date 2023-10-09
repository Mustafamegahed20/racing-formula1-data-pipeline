# Formula 1 Racing Data Pipeline
![SI202111130438_news](https://github.com/Mustafamegahed20/racing-formula1-data-pipeline/assets/61358936/4e2abd7f-3068-4124-a014-c7f8e2b5c1d1)
# Summary 
  Design and Orchestrate a Data Pipeline using Databricks and Azure DataFactory to perform analysis and visualization on Formula 1 race results.
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
