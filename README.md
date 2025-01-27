# Python-Project

## IMPORTING 

import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  

### READ FROM CSV

df = pd.read_csv(r'C:/Users/DELL/Desktop/Python Project/pythonproject.csv')
print(df)

#### COLUMN CHECK
df.columns
##### Head Tells first 5 rows

df.head(5)
###### shape function
df.shape
<!--Tail function-->
df.tail(4)
<!--Sample function-->
df.sample(5)
<!--Columns function-->
df.columns
<!--info function-->
df.info()
<!--describe function-->
df.describe()
a = df.describe(include='all')
<!--loc function-->
a.loc[['top', 'mean']]
<!--iloc function-->
a.iloc[[2, 3, 4]]
<!--smax rows and column function-->
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)
<!--sequencing-->
df[['CustomerId', 'Surname']]
<!--remove duplicate function--> 
df = df.dropna()
<!--duplicate eliminate function-->
df = df.drop_duplicates()
<!--Save dataset-->
df.to_csv('cleaned_data.csv', index=False)
<!--duplicate count function-->
duplicate_count = df.duplicated().sum()
duplicate_count

<!--duplicate row count function-->
duplicate_rows = df[df.duplicated()]
duplicate_rows
<!--averagefunction-->
average_age = df['Age'].mean()
average_age
<!--mode function-->
mode_age = df['Age'].mode()
mode_age.tolist()
<!--plot graph -->
plt.figure(figsize=(6, 4))
plt.bar(['Duplicate Rows'], [duplicate_count], color='lightblue')
plt.title('Count of Duplicate Rows')
plt.ylabel('Number of Duplicates')
plt.show()

<!--Plotiing of graph-->
plt.figure(figsize=(6, 4))
plt.bar(df.columns, null_values, color='lightblue')
plt.title('Count of Null Values per Column')
plt.ylabel('Number of Nulls')
plt.xticks(rotation=90)  
plt.show()

<!-- graph type histogram -->
plt.figure(figsize=(6, 4))
df['Age'].plot(kind='hist', bins=30, color='lightblue', edgecolor='black')
plt.title('Age Distribution')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

<!--graph type box plot-->
plt.figure(figsize=(6, 4))
df['Age'].plot(kind='box', color='lightblue')
plt.title('Age Box Plot')
plt.ylabel('Age')
plt.show()


