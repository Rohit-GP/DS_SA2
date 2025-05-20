# SKILL-ASSESSMENT  2

# Aim:
To perform data preprocessing and exploratory data analysis (EDA) using various statistical and visualization techniques to identify and treat outliers, and to analyze the distribution and relationships within the dataset.

# Explanation:
Data Science involves deriving valuable insights from structured or unstructured data using scientific techniques, algorithms, and tools. Python, with its powerful libraries such as Pandas, NumPy, and Seaborn, facilitates efficient data manipulation, visualization, and analysis. This task focuses on essential data preprocessing steps, including data cleaning, detecting and removing outliers using Boxplot and IQR methods, and performing univariate and multivariate analysis through Count plots and Distplots, thereby reinforcing practical data science skills.

# Algorithm

1. Perform Data cleaning process wherever necessary

2. Implement Boxplot method to detect outliers

3. Implement IQR method to Remove Outliers 

4. Implement Count plot method for univariate analysis

5. Implement DistPlot method for multivariate analysis

# Coding & Output

Name : Rohit GP

Ref/Reg No : 24900185 / 212224220082

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset (2).csv")
df
```
![image](https://github.com/user-attachments/assets/7815fd90-f5b8-4ac6-91b6-f9eb6d7bfe58)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/809bc8a3-b7c2-4d05-8854-282bd5d7a2a1)
```
df.Cabin.fillna(method='ffill',inplace=True)
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/c528e72e-2b4b-46c0-abb9-e2c5412bd0c2)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/65e43156-1c23-40db-8772-0bce7d2200e9)
```
df.dtypes
```
![image](https://github.com/user-attachments/assets/3f746473-550b-4297-aa94-1966b175b01e)
```
df.columns
```
![image](https://github.com/user-attachments/assets/429ec60b-b3d2-4a92-a969-925b5a7eab4e)
```
tp=df.Pclass.median()
tp
```
![image](https://github.com/user-attachments/assets/def5a39b-a457-418a-95d8-56850025e4ee)
```
df.Pclass.fillna(tp,inplace=True)
df
```
![image](https://github.com/user-attachments/assets/cd2f23ac-d57b-4802-aac0-9930bd23c28a)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/29361ecb-a935-4e09-989b-725c1c705593)
```
df.Cabin.fillna(method='bfill',inplace=True)
df.Embarked.fillna(method='ffill',inplace=True)
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/3eb05506-2212-4d08-ade1-0f37b66dc6c4)
```
sns.boxplot(data=df['Age'])
```
![image](https://github.com/user-attachments/assets/0a9ed5fd-b48b-4ad0-9378-651d623b3f5a)
```
sns.boxenplot(data=df['Age'])
```
![image](https://github.com/user-attachments/assets/4daa8ae6-45e3-4119-a04d-263aed2a868e)
```
q1=np.percentile(df['Age'],25)
q3=np.percentile(df['Age'],75)
iqr=q3-q1
print(iqr)
```
![image](https://github.com/user-attachments/assets/68250153-99d0-4a8f-b9ee-70d8d48c40d8)
```
lb=q1-1.5*iqr
ub=q3+1.5*iqr
print(lb)
print(ub)
```
![image](https://github.com/user-attachments/assets/fe2f3f24-3b1a-4738-9d89-b1dc58c09c8f)
```
df=df[((df['Pclass']>=lb) & (df['Pclass']<=ub))]
df
```
![image](https://github.com/user-attachments/assets/1dadcb6c-67cc-45fc-9879-2770d0dbc2e3)
```
df.dropna(inplace=True)
sns.boxplot(data=df['Age'])
```
![image](https://github.com/user-attachments/assets/0741771f-9084-4c46-a29a-d14b7624e69d)
```
sns.boxenplot(data=df['Age'])
```
![image](https://github.com/user-attachments/assets/9e02ee19-4b67-4354-874c-6442e416a53d)
```
sns.countplot(data=df, x='Gender')
```
![image](https://github.com/user-attachments/assets/c14249a4-d4ca-4079-b090-773c0e40d966)
```
sns.displot(data=df, x='Age', hue='Gender', kde=True)
```
![image](https://github.com/user-attachments/assets/9be72350-846f-42e4-8176-dbd96fb1207d)

# Result :
Basic data cleaning was completed using Pandas and NumPy. Outliers were detected with Boxplots and removed using the IQR method. Count plots and Distplots were used for univariate and multivariate analysis, respectively.
