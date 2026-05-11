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

# Coding and Output

```
import numpy as np
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data
```

<img width="1915" height="986" alt="image" src="https://github.com/user-attachments/assets/55440bf4-5cc6-4668-bf7c-3c6a4327bbe8" />

```
data.head(4)
```
<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/dae75e32-dc79-4d8d-be7e-cad3d08a4967" />

```
data.tail(7)
```
<img width="1918" height="990" alt="image" src="https://github.com/user-attachments/assets/789706fb-84fd-40aa-bb7c-d326b7889537" />

```
data.isnull()
```
<img width="1918" height="987" alt="image" src="https://github.com/user-attachments/assets/dfbcff26-3594-41f9-8fb5-ff8d0912df5c" />
```
data.notnull()
```
<img width="1918" height="992" alt="image" src="https://github.com/user-attachments/assets/2ce6891f-91af-4671-bdba-436972b22d1a" />

```
 data.isnull().sum() 
```
 <img width="1906" height="987" alt="image" src="https://github.com/user-attachments/assets/a014fe97-7af4-4ffe-bf80-3758cad99728" />

 ```
data.dropna(axis=1)
```
<img width="1913" height="986" alt="image" src="https://github.com/user-attachments/assets/01620f7e-7ade-4b25-8de9-a5fb9839c7e4" />
```
data.dropna(axis=0)
```

<img width="1918" height="985" alt="image" src="https://github.com/user-attachments/assets/700662dc-29c2-4ec4-8e91-dd91a6f0c8aa" />

```
data.fillna(0)
```
<img width="1918" height="987" alt="image" src="https://github.com/user-attachments/assets/e5a89a80-2dde-4d77-86fa-95d7a64cd0c3" />

```
data.fillna(method="ffill")
```
<img width="1918" height="983" alt="image" src="https://github.com/user-attachments/assets/d54168ce-178a-4214-a332-afa3f3b7831f" />

```
data.bfill()
```
<img width="1917" height="990" alt="image" src="https://github.com/user-attachments/assets/aa4417a8-2b0e-403e-98b9-d71950559eaf" />

```
ir=pd.read_csv("/content/iris.csv")
ir
```
<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/eff00db5-3fa4-42b6-9a63-5d72e802ce91" />

```
ir.describe()
```
<img width="1918" height="983" alt="image" src="https://github.com/user-attachments/assets/7d073781-a814-4229-a93e-35da31c1221d" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```

<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/118787c6-12dc-4453-a160-d5a9c1df9c4e" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)

```
<img width="1917" height="1001" alt="image" src="https://github.com/user-attachments/assets/4f0d78c8-2a2b-4730-9489-808599cd1512" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/86c43fe5-d4ac-4a6d-85b2-c5b3c9a7b58f" />
```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="1918" height="985" alt="image" src="https://github.com/user-attachments/assets/82a55772-11fc-4098-9f28-3794b7047eef" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z 

```
<img width="1918" height="990" alt="image" src="https://github.com/user-attachments/assets/ae192edb-89ef-4cbb-aef4-47efe5a4b7e2" />

# Result

Thus the programs are executed successfully.
