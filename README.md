# Python Course Summary 

## Introduction

**Python** is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance. Python supports modules and packages, which encourages program modularity and code reuse. The Python interpreter and the extensive standard library are available in source or binary form without charge for all major platforms, and can be freely distributed.

In this summary, the main focus is on Python's data analysis module such as usage of **pandas** library, indexing, slicing, and other data analysis techniques. Other than that, there is also a tutorial of how to read data from local file, database, and read data from calling an API.

In addition to this summary, you can access the materials and modules that has been made by Mr. Samuel Chan about Python for data analysis on this [Github repository](https://github.com/onlyphantom/dataanalysis). You can download all the files from the code button -> Download ZIP. Hopefully this additional material will be helpful for you to learn Python.

## Introduction to Python

### Variable

Variable is a name that refers to a value. The variable itself assigned using `=` operator.

```python
activity = "swimming"
```

From the code above, the variable `activity` is assigned with the value `swimming`. Note that the variable name is case sensitive. Which means, if we try to calling the variable `Activity`, it will not work.

One thing that also must be noted, that `=` and `==` in python is a different thing. `=` is used to assign a value to a variable. `==` is used to compare two values. For more complete explanation of python operators you can refer to [Data Operator Section](#operator).

### Data Type

- [`object`]: store text values
- [`int`]: integer values
- [`datetime`]: date and time values
- [`bool`]: True/False values
- [`float`]: floating point values

In Python data type is important because it determines the behavior of the variable. For example, if we assign a variable with integer value, then we can use the variable to perform mathematical operation. There are also some of function that can only be performed using specific type of data. Such as `.describe()` function for dataframe that will only calculate for numeric data.

### Indexing

Python itself start the index at 0. So, in python we will start the counting at `0` and not at `1`. For example, if we have a list of 5 elements, then the first element is `0`, the second element is `1`, and so on.

```python
x = [1, 2, 3, 4, 5]
```

So, from the x list above, we can access the first element by `x[0]`, where the value of `x[0]` is 1, the value of `x[1]` = 2, and so on.

<div id="operator"></div>

### Data Operator

**Arithmetic Operator**

Arithmetic operators are used to performing mathematical operations like addition, subtraction, multiplication, and division.

| Operator | Description | Syntax |
| --------- | ----------- | ------ |
| +	| Addition: adds two operands |	x + y |
| –	| Subtraction: subtracts two operands |	x – y |
| *	| Multiplication: multiplies two operands | x * y |
| /	| Division (float): divides the first operand by the second | x / y |
| // | Division (floor): divides the first operand by the second | x // y |
| %	| Modulus: returns the remainder when the first operand is divided by the second | x % y |
| ** | Power: Returns first raised to power second | x ** y |

**Comparison Operator**

Comparison of Relational operators compares the values. It either returns True or False according to the condition.

| Operator | Description | Syntax |
| --------- | ----------- | ------ |
| >	| Greater than: True if the left operand is greater than the right | x > y |
| <	| Less than: True if the left operand is less than the right | x < y |
| == | Equal to: True if both operands are equal | x == y |
| != | Not equal to – True if operands are not equal | x != y |
| >= | Greater than or equal to True if the left operand is greater than or equal to the right | x >= y |
| <= | Less than or equal to True if the left operand is less than or equal to the right | x <= y |
| is | x is the same as y | x is y |
| is not | x is not the same as y | x is not y |

**Logical Operator**

Logical operators perform Logical AND, Logical OR, and Logical NOT operations. It is used to combine conditional statements.

| Operator | Description | Syntax |
| --------- | ----------- | ------ |
| and (&) |	Logical AND: True if both the operands are true	| x and y |
| or (|) | Logical OR: True if either of the operands is true | x or y |
| not (~) | Logical NOT: True if the operand is false | not x |

### Python Library

Python is very powerful because there are many libraries and packages that support the Python language. Many libraries and packages are helping python user to do some specific task. Some of the most famous libraries or packages that usually used by Python user are: pandas, numpy, matplotlib, scipy, scikit-learn, and seaborn.

- pandas : specifically for data analysis and data manipulation
- numpy : for data manipulation and data analysis
- matplotlib : for data visualization
- seaborn : for data visualization
- scipy : for data analysis (statistics)
- scikit-learn : for machine learning

In the next chapter, we will specifically talk about the **Pandas** library for data analysis and manipulation in python.

## Pandas Library

Pandas library is famous package that is used for data analysis and manipulation. It provide a way for python user to easily load tabular data and perform data analysis. It is also very easy to use and very powerful.

### Data Frame

One of the most famous function is `pd.DataFrame()` that is used to create a dataframe. The dataframe is a two dimensional array that is indexed by row and column. Or it also can be said as a tabular data like we usually load into microsoft excel.

#### Dataframe Slicing and Subsetting

In the following section, we'll take a closer look at some of the most common slicing and subsetting operations in `pandas`:

- `head()` and `tail()`  
    The `head()` and `tail()` functions return the first or last n rows of the dataframe. 

    ```python
    df.head()
    ```
    or

    ```python
    df.tail()
    ```

    By default, if the `n=` parameter is not specified, `head()` returns the first 5 rows and `tail()` returns the last 5 rows.

- `select_dtypes()`  

    The `select_dtypes()` function returns a subset of the dataframe with only the columns that have the specified data types.

    ```python
    df.select_dtypes(include=['int64'])
    ```

    It means that the function will return a subset of the dataframe with only the columns that have integer data types.

- Using `.drop()` 

    The `.drop()` function is used to drop rows or columns from the dataframe.

    ```python
    df.drop(['column_name'], axis=1)
    ```
    It means that the function will drop the column `column_name` from the dataframe.

- The `[]` operator

    The `[]` operator is used to access the rows or columns of the dataframe.
    
    ```python
    df[['a', 'b']]
    ```

    It means that the function will return a subset of the dataframe with only the columns that have the specified data types.

- `.loc`  

    The `.loc` function is used to select rows or columns from the dataframe. Using .loc, we can select rows or columns by their index name or integer position.

    ```python
    df.loc[0:2, ['A','C']]
    ```
    
    It means that the function will return a subset of the dataframe with only the rows that have index 0, 1, and 2 and the columns that have column names `A` and `C`.

- `.iloc`

    The `.iloc` function is used to select rows or columns from the dataframe. Using .iloc, we can select rows or columns only by their index integer position.

    ```python
    df.iloc[0:2, 0:3]
    ```

    It means that the function will return a subset of the dataframe with only the rows that have index 0, 1, and 2 and the columns that have index 0, 1, and 2. The difference between `.loc` and `.iloc` is that `.loc` is used to select rows or columns by their index name or integer position and `.iloc` is used to select rows or columns only by their index integer position.

- Conditional subsetting

    Conditional subsetting is used to select rows or columns from the dataframe based on some condition.

    ```python
    df[df['A'] > 0]
    ```

    It means that the function will return a subset of the dataframe with only the rows that have `A` column values greater than 0.

### Another Pandas Library Function

- `.describe()`

    The `.describe()` function is used to summarize the dataframe.
    
    ```python
    df.describe()
    ```
    
    It means that the function will return a summary of the dataframe especially for numeric columns. It will shown the count, mean, standard deviation, minimum, maximum, and percentiles of each numeric columns in the dataframe.

- `.info()`

    The `.info()` function is used to show the dataframe information.
    
    ```python
    df.info()
    ```
    
    It means that the function will return a summary of the dataframe. It will show the number of rows, columns, data types, and memory usage of the dataframe.

- `.columns`

    The `.columns` function is used to show the column names of the dataframe.
    
    ```python
    df.columns
    ```
    
    It means that the function will return a list of column names of the dataframe.

- `.shape`

    The `.shape` function is used to show the shape of the dataframe.
    
    ```python
    df.shape
    ```
    
    It means that the function will return a tuple of the number of rows and columns of the dataframe.

- `.value_counts()`

    The `.value_counts()` function is used to show the value counts of the dataframe.
    
    ```python
    df["A"].value_counts()
    ```
    
    It means that the function will return a series of the value counts of the dataframe. It can show how many times each unique value appears in the dataframe.

- `.sort_values()`

    The `.sort_values()` function is used to sort the dataframe.

    ```python
    df.sort_values(by=['A'], ascending=False)
    ```

    It means that the function will return a sorted dataframe based on the values in the column `A`.

- `.groupby()`

    The `.groupby()` function is used to group the dataframe by some column.
    
    ```python
    df.groupby(['A'])
    ```
    
    It means that the function will return a grouped dataframe based on the values in the column `A`.

- `pd.crosstab()`

    The `pd.crosstab()` function is used to show the cross tabulation of the dataframe.
    
    ```python
    pd.crosstab(df['A'], df['B'])
    ```
    
    It means that the function will return a cross tabulation of the dataframe.

- `pd.merge()`

    The `pd.merge()` function is used to merge two dataframe into one dataframe (or usually also known as `join`).
    
    ```python
    pd.merge(df1, df2, on='A')
    ```
    
    It means that the function will return a merged dataframe based on the values in the column `A`.

### Date Data Manipulation

- `pd.to_datetime()`

    The `pd.to_datetime()` function is used to convert the dataframe to datetime format.
    
    ```python
    pd.to_datetime(df['A'])
    ```
    
    It means that the function will return a datetime format of the values in the column `A`.

- `dt.date`

    The `dt.date` function is used to convert the datetime format to date format.
    
    ```python
    df["date"].dt.date
    ```
    
    It means that the function will return a date format of the values in the column `A`.

- `dt.hour`

    The `dt.hour` function is used to show the hour of the datetime format.
    
    ```python
    df["date"].dt.hour
    ```
    
    It means that the function will return the hour of the datetime format.

- `dt.day_name()`

    The `dt.day_name()` function is used to show the day name of the datetime format.
    
    ```python
    df["date"].dt.day_name()
    ```
    
    It means that the function will return the day name of the datetime format.

### String Data Manupulation

-   `pd.Series.str.split()`

    The `pd.Series.str.split()` function is used to split the string in the dataframe.
    
    ```python
    df["A"].str.split(",")
    ```

    The function will return a list of the values in the column `A` split by the comma.

- `pd.Series.str.contains()`

    The `pd.Series.str.contains()` function is used to replace the string in the dataframe.
    
    ```python
    df["A"].str.contains("a")
    ```

    It means that the function will return a boolean of the values in the column `A`. If the string contains the letter `a`, then the boolean will be True. Otherwise, the boolean will be False.

- `pd.Series.str.replace()`

    The `pd.Series.str.replace()` function is used to replace the string in the dataframe.
    
    ```python
    df["A"].str.replace("a", "b")
    ```

    It means that the function will return a string of the values in the column `A`. If the string contains the letter `a`, then the string will be replaced with the letter `b`.

- `pd.Series.str.len()`

    The `pd.Series.str.len()` function is used to show the length of the string in the dataframe.
    
    ```python
    df["A"].str.len()
    ```

    It means that the function will return a series of the length of the values in the column `A`.

- `pd.Series.str.lower()`

    The `pd.Series.str.lower()` function is used to show the lower case of the string in the dataframe.
    
    ```python
    df["A"].str.lower()
    ```

    It means that the function will return a series of the lower case of the values in the column `A`.

- `pd.Series.str.upper()`

    The `pd.Series.str.upper()` function is used to show the upper case of the string in the dataframe.
    
    ```python
    df["A"].str.upper()
    ```

    It means that the function will return a series of the upper case of the values in the column `A`.

- `pd.Series.str.startswith()`

    The `pd.Series.str.startswith()` function is used to show the start with of the string in the dataframe.
    
    ```python
    df["A"].str.startswith("a")
    ```

    It means that the function will return a series of the start with of the values in the column `A`. If the string starts with the letter `a`, then the boolean will be True. Otherwise, the boolean will be False.
    
## Read Data

### Read Data From Local File

There are several ways to read data in python. One of the most used function is read data from local file using pandas library.

```python
df = pd.read_csv("data.csv")
```
    
The function will return a dataframe of the data in the file `data.csv`.

There are also several ways to read another data format using pandas library. Some of the data formats are:
pd.read_excel(), pd.read_json(), pd.read_html(), pd.read_sql(), pd.read_sql_query(), pd.read_hdf(), pd.read_pickle(), pd.read_sas(), pd.read_stata(), pd.read_table(), pd.read_clipboard(), pd.read_fwf(), pd.read_gbq(), pd.read_gbq().

### Read Data From Database
 The other way to import data is from the database. To read the data from the database, we must know what database we used. The explanation below will show how to read data from certain database.

- Sqlite

    To import data from sqlite file, we need to import the sqlite3 and pandas library. The code below will show the way to import data from sqlite file.
    
    ```python
    import sqlite3
    import pandas as pd

    conn = sqlite3.connect("path_to_file") #fill the "path to file" with the path to the file

    albums = pd.read_sql_query("SELECT * FROM table_name", conn)
    ```

- MySql
    
    To import data from mysql, we need to import the pymysql and pandas library. The code below will show the way to import data from mysql.
    
    ```python
    import pymysql
    conn = pymysql.connect(host=host, port=port, user=user, password=password, db=database)

    sales = pd.read_sql_query("SELECT * FROM table_name", conn)
    ```

- Postgresql
        
    To import data from postgresql, we need to import the sqlalchemy and pandas library. The code below will show the way to import data from postgresql.
    
    ```python
    import sqlalchemy

    db_address = f'postgresql+psycopg2://{username}:{password}@{host}:{port}/{database}'
    engine = sqlalchemy.create_engine(db_address)

    sales = pd.read_sql_query("SELECT * FROM table_name", conn)
    ```

### Call Data From API

To call data from API we need to import `requests`, `pandas`, and `json` library. The code below will show the way to call data from API.

```python
import requests
import json

req = requests.get(url) #fill the "url" with the url of the API
req.status_code
```

If the request is successful, the status code will be 200. Otherwise, the status code will be 400. Then, if the status code is 200, we can use the `json.loads()` function to convert the response to a dictionary and use the `pd.DataFrame()` function to convert the dictionary to a dataframe.

```python
text = json.loads(req.text)
face = pd.DataFrame(text)
```

# Source
- [Python](https://www.python.org/doc/essays/blurb/)
- [Data Operator](https://www.geeksforgeeks.org/python-operators/)
