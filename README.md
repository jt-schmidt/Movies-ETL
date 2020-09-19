# Movies-ETL

# Overview
Module 8 exploration of ETL using Python/Pandas to extract/transform data from .csv and .json and load to SQL DB.


# Raw Data
It is poor Git repository practice to upload raw datasets.  Instead of uploading raw datasets used for this module, here are the links to obtain:
- Download link for zipped Kaggle dataset:  
  - https://www.kaggle.com/rounakbanik/the-movies-dataset/download
- Download link for wikipedia movies .json dataset:  
  - https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-online/module_8/wikipedia-movies.json
  
# Deliverable 1:  Write an ETL function to read three data files

[ETL_1function_test](/ETL_1function_test.ipynb)
- An ETL function is written to read in the three data files. (10 pt)
- The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
- The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
- The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)

# Deliverable 2: Extract and Transform the Wikipedia Data

[ETL_2clean_wiki_movies](/ETL_2clean_wiki_movies.ipynb)
- The TV shows are filtered out, and the wiki_movies_df DataFrame is created. (3 pt)
- A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs. (5 pt)
- The extraction and transformation of the Wikipedia data in the ETL function does the following:
  - A list comprehension is used to keep columns with non-null values. (3 pt)
  - The non-null box office data is converted to string values using the lambda and join functions. (3 pt)
  - A regular expression is used to match the six elements of "form_one" of the box office data. (2 pt)
  - A regular expression is used to match the three elements of "form_two" of the box office data. (2 pt)
  - The following columns are cleaned in the Wikipedia DataFrame: box office, budget, release date, running time (8 pt)
- The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file. (4 pt)

# Deliverable 3: Extract and Transform the Kaggle Data

[ETL_3clean_kaggle_data](/ETL_3clean_kaggle_data.ipynb)
- The extraction and transformation of the Kaggle metadata using the ETL function does the following:
  - The Kaggle metadata is cleaned. (4 pt)
  - The Wikipedia and Kaggle DataFrames are merged. (3 pt)
  - The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df: (8 pt)
    - Unnecessary columns are dropped.
    - A function is used to fill in the missing Kaggle data.
    - The movies_df DataFrame is filtered to keep specific columns.
    - The movies_df DataFrame columns are renamed.
- The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
  - The ratings counts are cleaned. (3 pt)
  - The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. (4 pt)
  - The empty values in the movies_with_ratings_df DataFrame are filled with “0”. (3 pt)
- The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file. (5 pt)

# Deliverable 4: Create the Movie Database

[ETL_4create_database](/ETL_4create_database.ipynb)
- The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png. (5 pt)
- The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png. (5 pt)
- The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file. (5 pt)
