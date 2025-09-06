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
~~~
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
~~~
<img width="882" height="637" alt="image" src="https://github.com/user-attachments/assets/20c623f6-6b2d-403c-a978-efd213b677f2" />

~~~
df.head()
~~~

<img width="847" height="168" alt="image" src="https://github.com/user-attachments/assets/636bac8f-f477-4666-8ef7-6a30281727d7" />

~~~
df.tail()
~~~

<img width="835" height="167" alt="image" src="https://github.com/user-attachments/assets/e7f4ac71-aac4-4bc3-b618-8b64d3cbb86c" />

~~~
df.isnull()
~~~

<img width="804" height="639" alt="image" src="https://github.com/user-attachments/assets/7ef7ba36-fdfa-4dad-916b-dd8d1038681b" />

~~~
df.notnull()
~~~

<img width="686" height="634" alt="image" src="https://github.com/user-attachments/assets/cd34c50f-ce49-4b21-9403-7dc05a577090" />

~~~
df.isnull().sum()
~~~

<img width="282" height="396" alt="image" src="https://github.com/user-attachments/assets/ee386da0-cdba-42f4-9305-1e35bb5fa5f6" />

~~~
df.isnull().any()
~~~

<img width="282" height="416" alt="image" src="https://github.com/user-attachments/assets/506e8c39-87f5-4d78-94d8-e512fe13dc16" />

~~~
df.dropna(axis=0)
~~~

<img width="839" height="412" alt="image" src="https://github.com/user-attachments/assets/775e354f-6d68-4016-8051-d3a147139494" />

~~~
df.dropna(axis=1)
~~~

<img width="394" height="635" alt="image" src="https://github.com/user-attachments/assets/2b21f206-f21b-4df6-94a2-03ed60ed86cc" />

~~~
df.fillna(5)
~~~

<img width="949" height="630" alt="image" src="https://github.com/user-attachments/assets/fe0e7a69-30f7-4100-92db-18433a072da6" />

~~~
df.fillna(method="ffill")
~~~

<img width="1019" height="665" alt="image" src="https://github.com/user-attachments/assets/fd11a430-8c40-48d0-8303-da6a4eda3768" />

~~~
df.fillna(method="bfill")
~~~

<img width="1019" height="665" alt="image" src="https://github.com/user-attachments/assets/a6f7532a-795d-4f8b-913d-3af31adf7a7d" />

~~~
df.fillna({'GENDER':"MALE","NAME":"SRI","ADDRESS":"POONAMALLEE","M1":98,"M2":87,"M3":76,"M4":92,"TOTAL":250,"AVG":99})
~~~

<img width="949" height="624" alt="image" src="https://github.com/user-attachments/assets/619f0752-412d-4420-a968-1e9de0535bd1" />

~~~
import pandas as pd
import seaborn as sns
ir=pd.read_csv("iris.csv")
ir
~~~

<img width="617" height="382" alt="image" src="https://github.com/user-attachments/assets/e97d7e2b-7f48-484c-b61c-8894782e008e" />

~~~
ir.describe()
~~~

<img width="655" height="280" alt="image" src="https://github.com/user-attachments/assets/76ec41c4-38d5-45d1-8343-fa6ec3c64e7f" />

~~~
sns.boxplot(x="sepal_width",data=ir)
~~~

<img width="609" height="454" alt="image" src="https://github.com/user-attachments/assets/bca77a39-f88c-4065-b953-760c5f239c2a" />

~~~
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
~~~

<img width="594" height="154" alt="image" src="https://github.com/user-attachments/assets/c945faff-6fdf-47f3-9de6-170a3a9fbf5f" />

~~~
df=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
df["sepal_width"]
~~~

<img width="278" height="384" alt="image" src="https://github.com/user-attachments/assets/d595ee4a-ad6d-4282-82f1-6ec46b66e9d3" />

~~~
z=np.abs(stats.zscore(ir["sepal_width"]))
z
~~~

<img width="782" height="483" alt="image" src="https://github.com/user-attachments/assets/8eb55927-80f4-4ba6-a0a7-9babe066d082" />

~~~
ir1=ir[z<3]
ir1
~~~

<img width="687" height="352" alt="image" src="https://github.com/user-attachments/assets/1b23eac5-92e6-4fbc-8396-d5bde211ca0d" />











# Result
Thus the given code successfully performed data cleaning and saved the clean data to a file.
          
