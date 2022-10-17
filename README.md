
# Project: Data Modeling with Postgres

## Description

As a data engineer I am doing an assignment for the startup Sparkify. Indeed, Sparkify wants to have a precise idea about its music data in order to propose in the future a better music streaming application. To carry out this project I had to create a Postgres database with tables designed to optimize the queries on the analysis of the playback of songs and an ETL pipeline.

## How to run 

1) You have to start a new terminal session and write : python create_tables.py
This will allow you to create the sparkifydb database needed for running other parts of the project.

2) Now in the terminal session write : python etl.py
This is nececessary for inserting/process the entire datasets into each table.

3) Run test.ipynb
For checking the database 

## An explanation of the files in the repository

*In the "data" repository :* 
- "song_data" is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song.
- "log_data" contains activity logs from a music streaming app based on specified configurations.

*create_table.py :* contains functions which drops and creates the tables.

*etl.ipynb :* reads and processes **a single file** from song_data and log_data and loads the data into the tables.
 
*etl.py :* reads and processes files from song_data and log_data and loads them into the tables.

*sql_queries.py :* contains all the sql queries.

*test.ipynb :* displays the first few rows of each table to let you check the database.


## Justification of my database schema

I created a star schema optimized for queries on song play analysis. In fact, primarily read optimized, star schemas will deliver good performance over large data sets.



## Note

I have a problem in part 5 of etl.ipynb. 
Here is the error message:
---------------------------------------------------------------------------
DataError                                 Traceback (most recent call last)
<ipython-input-30-2dc4f5c5decc> in <module>()
     20                      row.userAgent)
     21 
---> 22     cur.execute(songplay_table_insert, songplay_data)
     23     conn.commit()

DataError: invalid input syntax for integer: "free"
LINE 4:                                'free',


As I had to hand in this project today I didn't have time to ask a mentor to unblock me. 
I think it's related to the type of my variable "level" but I put it in varchar and still gets this error. When i replace "level" values with integer data like 0 instead of "free" error dissapear but it's not what we want. 
I still completed the following parts to finish the project and I hope that my work is enough to validate it. 