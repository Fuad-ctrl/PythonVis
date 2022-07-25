import numpy as np #  useful for many scientific computing in Python
import pandas as pd # primary data structure library

import requests

url = 'https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork/Data%20Files/Canada.xlsx'
r = requests.get(url)
open('Canada.xlsx', 'wb').write(r.content)
df = pd.read_excel('Canada.xlsx', sheet_name='Canada by Citizenship', skiprows=range(20),
    skipfooter=2)
#print(df.head())
#print(df.info(verbose=False))
#print((df.columns))
#print((df.index))
#print(type(df.columns))
#print(type(df.index))
#To get the index and columns as lists, we can use the tolist() method.
#print(df.columns.tolist())
#print(df.index.tolist())
#To view the dimensions of the dataframe, we use the shape instance variable of it.
# size of dataframe (rows, columns)
#print(df.shape)
#(195, 43)
#Let's clean the data set to remove a few unnecessary columns. We can use pandas drop() method as follows:
# in pandas axis=0 represents rows (default) and axis=1 represents columns.
df.drop(['AREA','REG','DEV','Type','Coverage'], axis=1, inplace=True)
#print(df.head(2))

#Let's rename the columns so that they make sense. We can use rename() method by passing in a dictionary of old and new names as follows:
df.rename(columns={'OdName':'Country', 'AreaName':'Continent', 'RegName':'Region'}, inplace=True)
print(df.columns)
#We will also add a 'Total' column that sums up the total immigrants by country over the entire period 1980 - 2013, as follows:
df['Total'] = df.sum(axis=1)
#print(df.isnull().sum())
print(df.describe())
