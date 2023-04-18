# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate Exploratory Data Analysis on the given data set.

# EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM
STEP 1: Import the built libraries required to perform EDA and outlier removal.

STEP 2: Read the given csv file.

STEP 3: Convert the file into a dataframe and get information of the data.

STEP 4: Return the objects containing counts of unique values using (value_counts()).

STEP 5: Plot the counts in the form of Histogram or Bar Graph.

STEP 6: Use seaborn the bar graph comparison of data can be viewed.

STEP 7: Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8: Save the final data set into the file.

# CODE
```
# Developed by: Priyadharshini.P
# Registration Number: 212222100039
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("/content/drive/MyDrive/Colab Notebooks/Semester 3/19AI403 _Intro to DS/Exp_3/SuperStore.csv")
df

df.head()

df.info()

df.describe()

df.tail()

df.shape

df.columns

df.isnull().sum()

df.duplicated()

df['Postal Code'] = df['Postal Code'].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

states=df.loc[:,["Segment","Sales"]]
states=df.groupby(by=["Segment"]).sum()
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()

sns.barplot(df["Ship Mode"],df["Sales"],hue=df["Category"])

df.corr()
sns.heatmap(df.corr(),annot=True)

plt.figure(figsize=(10,7))
sns.scatterplot(df['Sub-Category'], df['Sales'], hue=df['Ship Mode'])
plt.xticks(rotation = 90)
```
# OUTPUT
## DATASET
![image](https://user-images.githubusercontent.com/119558093/232683310-e6a0b63c-b15d-4dff-8a95-da13f5813c17.png)

## DATASET HEAD
![image](https://user-images.githubusercontent.com/119558093/232683587-6aa23dc0-a226-4588-bc92-dbcd84bd012a.png)

## DATASET INFO
![image](https://user-images.githubusercontent.com/119558093/232683666-c82abcc1-394d-467e-90e0-29f3dc1b5062.png)

## DATASET DESCRIBE
![image](https://user-images.githubusercontent.com/119558093/232683739-90b4565f-5fb0-4f41-ba56-fc2e5f35ee70.png)

## DATASET TAIL
![image](https://user-images.githubusercontent.com/119558093/232686287-ff08b4b4-9917-43c0-b88e-62efa5db3ca7.png)

## DATASET SHAPE
![image](https://user-images.githubusercontent.com/119558093/232686360-c500a259-7116-417b-9a26-1ba125ec646e.png)


## DATASET COLUMNS
![image](https://user-images.githubusercontent.com/119558093/232684156-233fd55e-98d9-44bd-8402-53ea0b187dcc.png)

## NULL VALUES - PRE CLEANING
![image](https://user-images.githubusercontent.com/119558093/232684332-3639ea3d-6ed5-404b-b3c1-e39f629a5885.png)

## DATASET DUPLICATED
![image](https://user-images.githubusercontent.com/119558093/232684441-65ee0eb9-166b-41b9-91bb-bee20ae7deef.png)

## NULL VALUES - POST CLEANING
![image](https://user-images.githubusercontent.com/119558093/232684515-4bc99f11-f7bd-451d-8aaa-0f9d675ad37a.png)

## MULTIVARIATE ANALYSIS-STATE
![image](https://user-images.githubusercontent.com/119558093/232684730-8f0f929d-bc62-4176-920e-ed7e284acf5f.png)

## MULTIVARIATE ANALYSIS - SEGMENT
![image](https://user-images.githubusercontent.com/119558093/232684950-5a732538-90df-4831-92c5-3f5ef67204bf.png)

## MULTIVARIATE ANALYSIS - SHIP MODE & CATEGORY Vs SALES
![image](https://user-images.githubusercontent.com/119558093/232685303-131a0487-0597-42de-881c-e1a1fc78d24f.png)

## MULTIVARIATE ANALYSIS - HEAT MAP
![image](https://user-images.githubusercontent.com/119558093/232685376-fabbba95-f3d4-44f2-bb1f-08509515a38c.png)

## MULTIVARIATE ANALYSIS - SUB CATEGORY & SHIP MODE VS SALES

![image](https://user-images.githubusercontent.com/119558093/232685936-6b4c6d1c-f17d-4d60-857d-a09ece21b663.png)

# RESULT
The given dataset is read and Multivariate analysis is performed. The inferences are,
Most sales were from the California State Most sales were from Consumer Segment Most sales were from "New York City" Most Sales were shipped on the Same Day and is most from Technology Highest sale was from Machines Sub-category and is shipped in standard class.







