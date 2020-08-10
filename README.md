# Sparkify 

**Song Play Analysis**
## Introduction
This database was designed to **Sparkify** for analytics purposes. The schema was designed to optimize queries on song play analysis through the following collected data:
* Songs data (JSON metadata);
* User activity (JSON logs).

## Data Schema
A star schema was defined with the following structure:

**Fact tables:**  
* `songplays`: records in log data associated with song plays.

**Dimensional tables:** 
* `users`:  users in the app.
* `songs`: songs in music database.
* `artists`: artists in music database.
* `time`: timestamps of records in songplays broken down into specific units.

The fact table **songplays** aggregate data from the different dimensinal tables.
Although the dimensional table have all the data required for the analysis, the fact table will provide the metric of the business process in a fastest way, in this case, **songs played by users analysis**.

## ETL
An ETL pipeline was build to properly ingest this data into the database, with the following data cleaning steps:
1. DROP existing tables
2. CREATE new tables.
3. Insert data into dimensional tables;
4. Insert data from dimensional tables into the fact table **songplays**.

## Files in repository:
* `create_tables.py`: Script to create and drop all tables.

* `sql_queries.py`: Script that contains all sql queries needed in the project.

* `etl.ipynb`: Notebook that reads and processes raw data and loads the output into sparkifydb tables, containing detailed instructions on the ETL process.

* `etl.py`: Script that reads and processes raw data and loads the output into sparkifydb tables.

* `test.ipynb`: Notebook that displays the first few rows of each table to let you check your database.



## Usage 
1. Run `create_tables.py`: This will create a new database called *sparkifydb* with empty tables.
2. Run `etl.py`: This will extract data from raw sources, transform it and load it into different *sparkifydb* tables.
