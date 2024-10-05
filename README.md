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
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/5ca73010-d59d-4e33-8bc7-5aef005e38b3)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/bbc45060-b270-4a80-b014-88c73e168aad)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/c651853d-e147-4607-b29d-e9fe0fffb6c5)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/4703dd66-9e80-4982-a1aa-3aafb98030ba)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/9253a3b8-ed51-4a06-9433-a85771ed4154)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/c9fd0b14-caa7-4adb-af4c-862dc7af7c50)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/9fbf8a30-31a2-4c25-9af8-ac56c73f77a5)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/3650837d-11d6-4f13-ac27-62a92256da8c)
```
dt
```
![image](https://github.com/user-attachments/assets/41ad1bd3-22cf-4fb5-959a-744238a3c769)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/96da2388-4454-4c22-9c2a-fe04e9a2f504)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/a370ad8a-9594-4a9b-991f-9db20ae5f83c)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/c2f10fcd-256d-42c3-b1ec-2a3d3ee7b484)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![image](https://github.com/user-attachments/assets/406277ae-7971-4b7d-b2f0-9539c98c7254)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/b3aa893f-0585-47fe-bd65-238176174d9d)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/ec429ad1-a2d1-4f61-83c2-ea7099938d00)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/c8992be8-5065-41e6-8346-8ce4d8b110f6)
```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![image](https://github.com/user-attachments/assets/4a67f5a8-8343-443f-bb84-854c8f4a0551)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/f7094191-aa39-4edf-ac53-32277fb5a35a)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/7d0aa600-650d-42ab-915e-aad6e34e908d)
```
numerical_dt = dt.select_dtypes(include=['number'])
corr = numerical_dt.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/3c668463-b980-4dc9-852c-4d6593a88284)


# RESULT
Hence performing Exploratory Data Analysis on the given data set is successful.
        
