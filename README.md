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

<img width="1236" height="443" alt="image" src="https://github.com/user-attachments/assets/8a86296f-2d61-4ea9-85e3-39e7e509dda2" />

```
df.info()
```

<img width="460" height="417" alt="image" src="https://github.com/user-attachments/assets/88da177a-3ba0-4716-a213-7dae60f4cb59" />

```
df.describe()
```

<img width="748" height="325" alt="image" src="https://github.com/user-attachments/assets/71599b2c-f281-4c65-af81-8f6e52dddcde" />

```
df.dtypes
```

<img width="247" height="297" alt="image" src="https://github.com/user-attachments/assets/dbfcde87-9851-4ce6-9415-eda5b9319003" />

```
df.value_counts()
```

<img width="1245" height="551" alt="image" src="https://github.com/user-attachments/assets/0a23e6e5-0a74-48e4-800d-831a7771d3a1" />

```
df['Age'].value_counts()
```

<img width="347" height="270" alt="image" src="https://github.com/user-attachments/assets/32f04161-7cd2-4a53-ad4a-df577a1aefb6" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="666" height="317" alt="image" src="https://github.com/user-attachments/assets/74634b28-4100-4c83-ac06-0cf71feca87d" />

```
df.shape
```

<img width="120" height="40" alt="image" src="https://github.com/user-attachments/assets/fabefe99-53ca-4a85-bf86-7deb89e74dd1" />

```
df.nunique()
```

<img width="212" height="300" alt="image" src="https://github.com/user-attachments/assets/01b8c5ff-370d-4e37-ab49-92d73b6e1340" />

```
sns.countplot(data=df,x='Survived')
```

<img width="812" height="592" alt="image" src="https://github.com/user-attachments/assets/7de6e7b8-6df6-4f58-aa1e-de55c7da064b" />

```
df.Pclass.unique()
```

<img width="297" height="36" alt="image" src="https://github.com/user-attachments/assets/8ab7e69c-a6ad-43f8-be8d-9e64f6e53f0d" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1242" height="462" alt="image" src="https://github.com/user-attachments/assets/adf88cf6-bf8a-4f1d-bdb8-babe7cfe03aa" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```

<img width="969" height="689" alt="image" src="https://github.com/user-attachments/assets/327b5f00-ea17-4085-b4b9-537696ee569a" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="800" height="617" alt="image" src="https://github.com/user-attachments/assets/2320af09-84c0-411d-ac45-c40c462eb4f0" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="785" height="583" alt="image" src="https://github.com/user-attachments/assets/0eae53bb-0645-45d1-ac17-5b7ddf307978" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="972" height="577" alt="image" src="https://github.com/user-attachments/assets/a2362c9f-30b1-4ba4-9f44-9a035f4e192d" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="922" height="580" alt="image" src="https://github.com/user-attachments/assets/ec6c4712-364c-4427-b520-29b5c55ee35b" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1265" height="603" alt="image" src="https://github.com/user-attachments/assets/c0a9fad2-0797-412d-9cee-f0302d14b47d" />

```
sns.pairplot(data=df)
```

<img width="1721" height="1721" alt="image" src="https://github.com/user-attachments/assets/34895eb4-8709-4fc1-a317-97f304d7b86a" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```

<img width="773" height="658" alt="image" src="https://github.com/user-attachments/assets/410cf093-8684-4962-8f85-279605e6b321" />

# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.
