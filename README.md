# Ex-04-Multivariate-Analysis

# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
STEP 1
Import the built libraries required to perform EDA and outlier removal.

STEP 2
Read the given csv file

STEP 3
Convert the file into a dataframe and get information of the data.

STEP 4
Return the objects containing counts of unique values using (value_counts()).

STEP 5
Plot the counts in the form of Histogram or Bar Graph.

STEP 6
Use seaborn the bar graph comparison of data can be viewed.

STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8
Save the final data set into the file

# PROGRAM
```
Name : SWETHA.S
Register Number : 212221220054

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```

# OUTPUT
# DATA
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/2d6e4edd-e263-4ada-8a06-61a41e9f8d5a)
# Data.info
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/93c9100f-a007-4fb1-97b3-6b3ad9ef6823)
# Data.describe
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/f89cd6bc-eb87-4f3a-a720-5a051a30aeb0)
# Checking the null values and Cleaning it
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/ebde548b-2858-4188-aa22-e3b26adb5de5)
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/880a277d-de99-4e75-b919-be8afdbd3d35)
# DATA TYPES
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/a8ee7eb6-4c3e-4d81-8f71-6daccdd18df3)
# SCATTER PLOT
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/2105465d-6f29-41bc-92dc-0b2fa09f7c28)
# BAR PLOT
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/406978b5-1a6f-483b-beb1-804e3e7f8480)
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/3e87dfd5-8d46-4f28-ba9e-15f5715deeb6)
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/d4d4b87b-12fa-4e13-8e21-e9db33acf402)
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/8d033447-dff5-4181-9587-891772abbf68)
# CORRELATION COEFFICIENT INTERPRETATION
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/bc446c7b-67da-4447-848b-8ec68aeeb73d)
# HEATMAP
![image](https://github.com/swethasurendar/Ex-04-Multivariate-Analysis/assets/133625914/08f89b09-7939-4c09-b750-b0a2e1311da3)
# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.

