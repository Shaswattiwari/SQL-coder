# SQL-coder

This repository contains a Python script designed to interact with a SQLite database, utilizing natural language processing (NLP) techniques to generate and execute SQL queries based on user input. The script employs the Hugging Face transformers library and the gemma model for text generation tasks.

## Setup

Before running the script, make sure to install the necessary dependencies. You can install them via pip:

```
!pip3 install -q -U accelerate==0.27.1
!pip3 install -q -U transformers==4.38.0
!pip install gemma
!pip3 install bitsandbytes  sqlparse

```


## Usage
#### Database Connection: 
Ensure that you have a SQLite database file (sql-murder-mystery.db in this case) accessible.

#### Run the Script: 
Execute the provided Python script. This script includes functions for querying the database based on user prompts.

#### Interacting with the Script:

Upon running the script, you will be prompted to input a task in natural language.

The script will generate an SQL query based on your input.

The generated SQL query will be executed on the SQLite database, and the results will be displayed.


## Script Overview
#### get_schema_as_string(database_file): 
This function retrieves the schema of the database and returns it as a string.

#### generate_response(text): 
This function generates an SQL query based on the provided natural language task using the Gemma model from Hugging Face's transformers library.

#### reformat_sql_query(text): 
This function reformats the generated SQL query for better readability.

#### execute_sql_query(database_file, sql_query):
This function executes the SQL query on the specified database file and returns the results.

#### show_table_schema(schema): 
This function displays the schema of the tables in the database.
