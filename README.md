# EXNO2DS
# NAME: AHALYA S
# REG.NO: 212223230006
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("titanic_dataset.csv")
df
```

![image](https://github.com/user-attachments/assets/dad8501c-5a4e-4706-8b9b-858c686dade7)

```
df.info()
```
![image](https://github.com/user-attachments/assets/29ee38db-f17c-44cc-80b8-0994de1abef5)

```
df.shape
```
![image](https://github.com/user-attachments/assets/5371a2aa-36ef-45e9-af1e-529bd2791ed2)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/b35327e1-3db1-475a-9c59-0f669be55203)

```
df.shape
```
![image](https://github.com/user-attachments/assets/70d85a9f-4263-4bd6-9849-cb61b7812e70)

# Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/f2174744-330a-4e1a-8bb0-3fdf25949fd0)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d0196c1b-0fce-432a-9dcc-09c14e5b2cd9)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/5a70d6fc-3f28-4ac4-9e58-3bfc2fd78326)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/c6bc2d97-f687-4ceb-bdfd-7bf45ee515eb)

```
df
```
![image](https://github.com/user-attachments/assets/7d7da6fc-a31b-4ebd-b4dc-a0383f418a6c)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/1b3a39dc-90e6-42f8-a13e-58ff56e71748)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/037f3d58-6dc1-43b7-8c01-abbc82b00f4d)

# Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/e4ee4c1d-e68e-4cdc-8ba1-7bd6f860bd7e)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/b9b4f48a-9403-43a2-88fd-0d527762a24c)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/7bc99584-582a-465d-8157-2baa11a7343b)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/5ebb36ca-8261-4dc8-bb6d-c9778d5743ce)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/6500c325-faac-4819-8262-d4aad3d91b32)

# Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/9de90ab1-3265-4e18-a384-6b83006ec4c6)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/4f3975bd-e9ec-44f0-8f2c-91efaa2a269d)

# Co-relation
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/d20380f8-7244-41a8-9f61-94845c2deb50)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/98887a50-10bf-48fc-9418-833244ccaad3)



# RESULT
Exploratory Data Analysis on the given data set successfully.
