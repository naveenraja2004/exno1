# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
```
Name:N.R.NAVEEN RAJA
Reg no:212222230093
```
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/hashish9275/exno1/assets/118707521/b129df30-9832-4188-963d-88ea5bc58e3a)
```
print(df.head(7))
```
![image](https://github.com/hashish9275/exno1/assets/118707521/a25cb59c-8597-43e6-b4bb-884075b25902)
```
print(df.tail(2))
```
![image](https://github.com/hashish9275/exno1/assets/118707521/0add0105-9e68-4872-9ee4-7878f5950fc7)
```
df.info()
```
![image](https://github.com/hashish9275/exno1/assets/118707521/d72d7d32-8e0e-4cf3-a726-1018f5deeb10)
```
print(df.describe())
```
![image](https://github.com/hashish9275/exno1/assets/118707521/92dd426b-9a12-4551-84b9-e30078e57a81)
```
df.isnull().sum()
```
![image](https://github.com/hashish9275/exno1/assets/118707521/ed82bf76-1266-44e6-acb7-32b20e8e839e)
```
df.nunique()
```
![image](https://github.com/hashish9275/exno1/assets/118707521/fafa6bf5-425b-4a93-b6c6-b029f15a5243)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/hashish9275/exno1/assets/118707521/d94488f9-70a6-4965-8ae5-7c5634184b99)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/hashish9275/exno1/assets/118707521/b9933b43-020c-48d2-bef1-d40b4a181046)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/hashish9275/exno1/assets/118707521/f099b1b4-59ff-40ea-a60e-839022de76c7)
![image](https://github.com/hashish9275/exno1/assets/118707521/a4ad0cd2-d929-4716-911f-3a55167cb35e)

```
import pandas as pd            
import seaborn as sns      
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/hashish9275/exno1/assets/118707521/1055ef38-673d-4476-b720-28ff64476390)
```
sns.boxplot(data=af)
```
![image](https://github.com/hashish9275/exno1/assets/118707521/57b0ea94-bd2c-4598-abca-39a9d3607ede)
```
sns.scatterplot(data=af)
```
![image](https://github.com/hashish9275/exno1/assets/118707521/c55538c5-fd97-4067-8a91-26fd613ccd25)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/hashish9275/exno1/assets/118707521/c4b58d8d-7c79-49cf-861c-c7990a126ca4)
```
af.dropna()
```
![image](https://github.com/hashish9275/exno1/assets/118707521/41dc61f8-ecfb-4670-bbf4-7c030234945a)
```
sns.boxplot(data=af)
```
![image](https://github.com/hashish9275/exno1/assets/118707521/d943d50a-4cef-4ef0-a515-029d075b160b)
```
sns.scatterplot(data=af)
```
![image](https://github.com/hashish9275/exno1/assets/118707521/eab6ca5c-137f-4887-a095-b2acc3edd953)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]         
df=pd.DataFrame(data)            
df    
```
![image](https://github.com/hashish9275/exno1/assets/118707521/ec69416c-7eb5-45f2-86f2-b283f8b60d2d)
```
import numpy as np    
from scipy import stats     
z=np.abs(stats.zscore(df))   
z     
```
![image](https://github.com/hashish9275/exno1/assets/118707521/a31a4ff3-6f61-4f4a-93f2-e8893d8f8b55)
