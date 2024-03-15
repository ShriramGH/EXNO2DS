# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: Shriram S
### Register no: 212222240098
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/7bd6594d-e066-461d-abe6-c5df504a1c5d)

```py
df.info()
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/b1f1eb00-c745-47ea-bd4c-84617d7f82e8)

```py
df.shape
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/21c00dd9-c68b-48c7-810c-d5f3b9d92074)

```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/f733f3df-5c48-48e0-98a5-9a9546e7f627)

```py
df.shape
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/53f42b6e-4752-44ce-80a8-10a0ecadc380)

### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/916f3a74-eca0-48d8-a224-5b05bc116e6e)

```py
df["Survived"].value_counts()
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/bc10c55c-7ad1-4d8a-8c76-ac4daf2f88ac)

```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/903bfed6-3391-4f1c-98f0-0212a3e61b60)


```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/b0518152-b397-4811-be78-fda2085e1bfa)

```py
df
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/cf654bdc-fbb7-4a73-9eb1-18fcef0ca1b8)

```py
df.Pclass.unique()
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/9049f2a0-55c2-418b-ac12-4f08234fd980)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/164f8ca0-9aea-4507-bdc2-dbd8dcf75059)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/de9b1322-0955-42f3-ba9e-b9cf54b75813)

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/43122f09-8b4c-4f6a-936a-da769bbfbfa6)

```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/9e6b73b7-3d08-496b-9fbd-6eacbcae34fd)

```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/2f425c58-d496-40c5-9d88-6ff8eb06434c)

```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/3f420179-9f56-4112-b4ff-52f35ab7689e)

### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/b8113ebc-d711-4e68-8821-5a3fa1fb94ac)

```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/3f420179-9f56-4112-b4ff-52f35ab7689e)

# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/3f420179-9f56-4112-b4ff-52f35ab7689e)

```py
sns.pairplot(df)
```
![image](https://github.com/ShriramGH/EXNO2DS/assets/117991122/0847958d-f3d3-464b-886d-c34389f3d8c1)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
