# ETL (Extract, Transform, Load) of Movies Data

## Project Overview

To create the data pipelines by performing Extract, Transform, Load or ETL process on the raw data which are retrieved from Wikipedia and Kaggle in order to help Britta prepare a clean dataset stored as a SQL database for the hackathon participants.

## Resources

+ **Languages:** Python3, SQL
+ **Software:** Jupyter Notebook
+ **Libraries:** Pandas, NumPy, SQLAlchemy, psycopg2
+ **Database System:** PostgresSQL
+ **Interface:** pgAdmin
+ **Raw Dataset:** in [Resources](https://github.com/asama-w/Movies-ETL/tree/main/Resources) folder
	+ `wikipedia-movies.json`
	+ `movies_metadata.csv`
	+ `ratings.csv`

## Process Descriptions

### 1. Extract
+ The movies data from three raw datasets which are in JSON format (from Wikipedia) and csv files (from Kaggle), respectively, will be read and stored in the DataFrame:
  + Wikipedia (in JSON format): a list of movies from 1990 to 2018.
  + Kaggle (in csv files): one dataset contains a ratings data from MovieLens, which has over 20 million reviews, and another dataset of their movie information.
+ Code (Deliverable 1): [ETL_function_test.ipynb](https://github.com/asama-w/Movies-ETL/blob/main/ETL_function_test.ipynb)

### 2. Transform
+ This is the data cleaning step. Wiki's movie data and Kaggle's movie data will be inspected and cleaned, such as that, the data types are converted to the right type, the text data is parsed to the desired format, the corrupted data is droppped, and etc. The new dataframe that contains movie information as well as its ratings is then created by merging the cleaned dataframes together.
+ Code (Deliverable 2): [ETL_clean_wiki_movies.ipynb](https://github.com/asama-w/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb)
+ Code (Deliverable 3): [ETL_clean_kaggle_data.ipynb](https://github.com/asama-w/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb)

### 3. Load
+ The cleaned data will be imported to the SQL database.
+ Code (Deliverable 4): [ETL_create_database.ipynb](https://github.com/asama-w/Movies-ETL/blob/main/ETL_create_database.ipynb)

The following images show the output screenshots of the row counts of the movies table and ratings table in the SQL database:

<img src= https://github.com/asama-w/Movies-ETL/blob/main/Resources/movies_query.png width="60%" height="60%">

<img src= https://github.com/asama-w/Movies-ETL/blob/main/Resources/ratings_query.png width="60%" height="60%">
