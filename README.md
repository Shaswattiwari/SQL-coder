# SQL-coder
This Python script serves as a SQL query generator for a SQLite database. It utilizes the Hugging Face transformers library to generate SQL queries based on user input and executes them against the specified SQLite database.



Installation
bash
Copy code
pip install -q -U accelerate==0.27.1
pip install -q -U transformers==4.38.0
pip install gemma
pip install bitsandbytes
pip install sqlparse
Usage
Import Required Libraries:

python
Copy code
import sqlite3
from tabulate import tabulate
import transformers
from transformers import AutoTokenizer, AutoModelForCausalLM
from transformers import GemmaTokenizer
import re
from transformers import pipeline
import torch
import sqlparse
Initialize Database Connection:

Specify the path to your SQLite database file.

python
Copy code
database_file = 'path/to/your/database.db'
Generate SQL Query:

Call the generate_response function with the desired SQL query prompt.

python
Copy code
sql_query = generate_response('Prompt for the SQL query')
Execute SQL Query:

Execute the generated SQL query against the database.

python
Copy code
results = execute_sql_query(database_file, sql_query)
print(results)
Display Schema:

Display the schema of the tables in the database.

python
Copy code
schema = get_schema_as_string(database_file)
show_table_schema(schema)
Functions
generate_response(text): Generates a SQL query based on the provided prompt using the Hugging Face transformers library.
execute_sql_query(database_file, sql_query): Executes the SQL query against the SQLite database and returns the results.
get_schema_as_string(database_file): Retrieves the schema of the tables in the SQLite database as a string.
show_table_schema(schema): Displays the schema of the tables in the database.
Example
python
Copy code
# Generate SQL query
sql_query = generate_response('Prompt for the SQL query')

# Execute SQL query
results = execute_sql_query(database_file, sql_query)
print(results)
Note
Ensure that you have the necessary permissions to execute SQL queries against the SQLite database and that the database file path is correctly specified.
