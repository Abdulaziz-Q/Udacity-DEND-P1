
# Data Modeling with Postgres - DE-Project 1

### Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

### Project Description

In this project, you'll apply what you've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, you will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

### Project files:

1.  `test.ipynb`  displays the first few rows of each table to let you check your database.
2.  `create_tables.py`  drops and creates your tables. 
3.  `etl.ipynb`  reads and processes a single file from  `song_data`  and  `log_data`  and loads the data into the tables. This notebook contains detailed instructions on the ETL process for each of the tables.
4.  `etl.py`  reads and processes files from  `song_data`  and  `log_data`  and loads them into your tables.
5.  `sql_queries.py`  contains all your sql queries.

# Schema for Song Play Analysis

Using the song and log datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

#### Fact Table

1.  **songplays**  - records in log data associated with song plays i.e. records with page  `NextSong`
    -   _songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent_

#### Dimension Tables

2.  **users**  - users in the app
    -   _user_id, first_name, last_name, gender, level_
3.  **songs**  - songs in music database
    -   _song_id, title, artist_id, year, duration_
4.  **artists**  - artists in music database
    -   _artist_id, name, location, latitude, longitude_
5.  **time**  - timestamps of records in  **songplays**  broken down into specific units
    -   _start_time, hour, day, week, month, year, weekday_
