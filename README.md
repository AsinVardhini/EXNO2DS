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
dt=pd.read_csv("titanic_dataset.csv")
dt
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/b43db971-1be9-4e52-8b77-9b90fc5f6059)

```
dt.info()
```
## OUTPUT:

![image](https://github.com/user-attachments/assets/59fa9cff-5679-44c7-aea2-a1a97c304c80)

```
dt.shape
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/2eee392c-0733-4d87-88d8-769ab371f388)

```
dt
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/4a921a3c-b74d-4da4-a21c-1e1a2825168d)

```
dt.describe()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/fbbe93e0-d4ec-4905-9fbc-92a77d95640b)

```
dt.nunique()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/7aa236c6-68ff-4f7c-abf7-bf2e79167cda)
```
dt["Survived"].value_counts()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/5effde66-cde5-40b4-8b4c-d6ef71abfd54)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/5071e3e6-bd14-4348-a117-3818b1d99993)

```
sns.countplot(data=dt,x="Survived")
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/5d345bc0-5fde-438c-9098-278a880db84a)

```
dt.Pclass.unique()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/3b85841a-b477-4ee3-963d-03182b261e0d)

```
dt.rename(columns={"Sex":"Gender"},inplace=True)
dt
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/4329851d-9701-447d-8c60-176c7bb3c5e2)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/0087e552-b16e-430a-9d23-f580747d1f8c)

```
sns.catplot(x="Survived",hue='Gender',data=dt,kind='count')
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/c47aed5f-3146-45a8-8b24-fe009f21bef9)

```
dt.boxplot(column="Age",by="Survived")
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/3b5eede0-02ec-4dc5-b9d3-5e30ba6ed6c7)

```
sns.scatterplot(data=dt,x="Age",y="Fare",hue="Survived")
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/d08017c5-bf4b-48c0-8a1e-4a38a13d2261)

```
sns.jointplot(data=dt,x="Age",y="Fare",hue="Survived")
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/5b263ba3-347e-43c5-9145-3291be6e4106)

```
sns.catplot(x="Gender",col="Survived",hue="Pclass",kind="count",data=dt)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/609dbb7a-a1e2-4288-8531-e14c7ac47545)

```
numeric_dt=dt.select_dtypes(exclude=[object])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/43122f86-d462-4abb-90e4-a0393438e21e)

```
sns.pairplot(dt)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/ac54f30e-dcc6-4af7-9c71-22983f1e076b)



















# RESULT
        Thus, the program is executed successfully.
