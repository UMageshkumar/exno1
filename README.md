# NAME:U.Mageshkumar
# REGNO:212224240085
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
import pandas as pd
import numpy as np
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
<img width="1066" height="859" alt="image" src="https://github.com/user-attachments/assets/062263b6-a7e3-4f2e-96a3-22cc89900786" />
```
df.head(4)
```
<img width="973" height="204" alt="image" src="https://github.com/user-attachments/assets/918c1320-e29a-4a29-ac10-18df10958a56" />
```
df.tail(7)
```
<img width="1015" height="327" alt="image" src="https://github.com/user-attachments/assets/8e711bc9-bdbb-4be1-9932-aebba14edf53" />
```
df.isnull()
```
<img width="826" height="857" alt="image" src="https://github.com/user-attachments/assets/16cc3d88-29aa-455e-a3c5-b6aa434e0440" />
```
df.notnull()
```
<img width="809" height="865" alt="image" src="https://github.com/user-attachments/assets/eb465b48-68c4-44eb-99ee-fc2d1d363c79" />
```
df.isnull().sum()
```
<img width="181" height="572" alt="image" src="https://github.com/user-attachments/assets/6c039fe6-dee6-4cc7-97e8-71931b658b9d" />
```
df.isnull().any()
```
<img width="233" height="575" alt="image" src="https://github.com/user-attachments/assets/5898fd22-5a12-4761-88ef-f01daef8b946" />
```
df.dropna(axis=1)
```
<img width="291" height="857" alt="image" src="https://github.com/user-attachments/assets/91baf8cf-2953-485b-ba14-f7ab68cb65b9" />
```
df.dropna(axis=0)
```
<img width="1024" height="567" alt="image" src="https://github.com/user-attachments/assets/5c9b9612-c212-42f3-a7e6-825457bd7776" />
```
df.fillna(0)
```
<img width="1018" height="858" alt="image" src="https://github.com/user-attachments/assets/a5fcd1b0-867a-4062-8230-dc5c90587df8" />
```
df.fillna(method="ffill")
```
<img width="1022" height="859" alt="image" src="https://github.com/user-attachments/assets/c84c20f4-d481-4f09-8498-d1c88d88747f" />
```
df.bfill()
```
<img width="1019" height="855" alt="image" src="https://github.com/user-attachments/assets/55a9af5e-781a-4173-81c4-90fd9f19b8a4" />
```
df.fillna({"REGNO":0 , "NAME":"Magesh"})
```
<img width="1029" height="850" alt="image" src="https://github.com/user-attachments/assets/7f972e2d-06c0-424b-838e-8bc1326b240d" />
```
ir=pd.read_csv("/content/iris.csv")
ir
```

<img width="661" height="509" alt="image" src="https://github.com/user-attachments/assets/83f4e212-6874-4531-be68-9315a6090544" />
```
ir.describe()
```

<img width="589" height="362" alt="image" src="https://github.com/user-attachments/assets/6687508e-4e32-4ed0-9c40-44f88dad3745" />
```
 import seaborn as sns
 sns.boxplot(x="sepal_width",data=ir)
```

<img width="697" height="573" alt="image" src="https://github.com/user-attachments/assets/86b30580-a701-4f31-b243-5f8a289d306a" />
```
 q1=ir.sepal_width.quantile(0.25)
 q3=ir.sepal_width.quantile(0.75)
 iqr=q3-q1
 print(iqr)
```

<img width="59" height="37" alt="image" src="https://github.com/user-attachments/assets/2ae0ca0c-f5fb-473f-ad29-ce5ce4f63145" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```

<img width="196" height="256" alt="image" src="https://github.com/user-attachments/assets/3943bfd7-9eb7-4685-90b7-a5939dc6f30c" />
```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```

<img width="658" height="514" alt="image" src="https://github.com/user-attachments/assets/e0e041e8-d6a3-4ad4-bb62-12b3ee51649f" />
```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```

<img width="202" height="562" alt="image" src="https://github.com/user-attachments/assets/87294cda-ad32-4419-9590-270a60324204" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
```

<img width="671" height="659" alt="image" src="https://github.com/user-attachments/assets/d73d82cd-da6f-489a-aaf3-fb6f01a34e5e" />


```
a=ir[z>3]
a
```

<img width="636" height="97" alt="image" src="https://github.com/user-attachments/assets/76ce59ca-e069-4221-a938-3a4f8450df1f" />


# Result
Thus the programs are executed successfully
