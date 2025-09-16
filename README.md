# EXNO2DS
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
<img width="1769" height="524" alt="image" src="https://github.com/user-attachments/assets/066e9f1c-c188-4089-954b-b6797f64d107" />

```
df.info()
```
<img width="1773" height="428" alt="image" src="https://github.com/user-attachments/assets/ed61f7ba-fe46-4692-8dc7-ed9d71820602" />

```
df.describe()
```
<img width="1773" height="370" alt="image" src="https://github.com/user-attachments/assets/9a74d424-11dd-41a0-b3b4-9a9d3a43b056" />

```
df.dtypes
```
<img width="1772" height="568" alt="image" src="https://github.com/user-attachments/assets/87c762f9-3271-4293-aab0-c0152f812ddc" />

```
df.value_counts()
```
<img width="1774" height="606" alt="image" src="https://github.com/user-attachments/assets/6a90d6f8-9a21-464b-b340-ec2664e03ada" />

```
df['Age'].value_counts()
```
<img width="1771" height="605" alt="image" src="https://github.com/user-attachments/assets/4ce359b5-2662-4b7e-8ee6-1aa09af7aebc" />

```
df.shape
```
<img width="1773" height="38" alt="image" src="https://github.com/user-attachments/assets/3489c56c-cdd6-4d48-bca9-7965a5f273af" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="1771" height="368" alt="image" src="https://github.com/user-attachments/assets/07325b9e-c84d-4fa7-9da7-e9eebcec7318" />

```
df.nunique()
```
<img width="1773" height="532" alt="image" src="https://github.com/user-attachments/assets/7c4ddc73-f4b9-45a7-9713-60059ce0e899" />

```
sns.countplot(data=df,x="Survived")
```
<img width="1771" height="574" alt="image" src="https://github.com/user-attachments/assets/f5e449c7-a6f8-4377-8f85-b6ccba2c8660" />

```
df.Pclass.unique()
```
<img width="1771" height="37" alt="image" src="https://github.com/user-attachments/assets/dbb348a5-79fe-4816-8d3f-9a478428bf33" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1770" height="562" alt="image" src="https://github.com/user-attachments/assets/4ac211d8-f5c8-4633-b41a-e7090ae58d44" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1772" height="650" alt="image" src="https://github.com/user-attachments/assets/53054602-c0b4-49a2-8ea3-00e97739cc05" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="1767" height="612" alt="image" src="https://github.com/user-attachments/assets/82586bd0-00cc-4502-9840-f9d835774c4e" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="1769" height="575" alt="image" src="https://github.com/user-attachments/assets/0ee0e9de-4a42-4cc4-8769-c3070b1ca69c" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1773" height="577" alt="image" src="https://github.com/user-attachments/assets/77f5e005-2b8c-411f-91b5-ea999fcaad32" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1768" height="553" alt="image" src="https://github.com/user-attachments/assets/8f3e3848-404c-411b-a64e-24c7a0b9918f" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1767" height="651" alt="image" src="https://github.com/user-attachments/assets/748fccec-e734-479d-b6fa-55c742c3f0da" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="1770" height="559" alt="image" src="https://github.com/user-attachments/assets/22a9f4ef-15eb-436c-b21f-71cf73c3f8d1" />

# RESULT

Thus exploratory data analysis on the given data set has been executed successfully
