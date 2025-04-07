# Data-Analytics
## Clean and prepare a raw dataset- DAY 1
 ### First we have to install pandas
 pip install pandas # First we have to install pandas
 ### Import the pandas as pd
 import pandas as pd
 ### We have to read the file assigned it as df and to check the first 5 rows of the file
 df = pd.read_csv(r"C:\Users\satya\Downloads\netflix_titles.csv")
 df.head()
 ### Show nulls per column
 print(df.isnull().sum())
 ### Drop rows with nulls
 df = df.dropna()
 ### Drop all the duplicates 
 df = df.drop_duplicates()
 ### Uppercase country and show_id columns
 df['country'] = df['country'].str.upper().replace({'UNITED STATES': 'US', 'SOUTH AFRICA': 'SA'})
 df['type'] = df['type'].replace({'Movie': 'M', 'TV Show': 'TS'})
 ### By this command the date changed as 2021-09-25
 df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')
 ### Change all the columns to Upper case
 df.columns = df.columns.str.upper()
 ### We have to check if all the command is correct and the data is clean according to the need
 print(df.shape) # it tells the dimension of dataframe
 print(df.info()) # give a summary of dataset
 print(df.head()) # Display the first 5 row of the dataframe
 ### We have to check the datatypes of the dataframe by using this command
 print(df.dtypes)
 ### Summary of the dataframe structure and statistical summaries of numeric column  
 print(df.info())
 print(df.describe())
