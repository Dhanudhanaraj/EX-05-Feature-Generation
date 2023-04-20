# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

Name:D.Dhanumalya

Register Number:212222230030

## Data.csv
```
import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/data.csv")
df1 = df.copy()
df1

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Ord_2'] = le.fit_transform(df['Ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(x ='Ord_2', data = df)

from sklearn.preprocessing import OneHotEncoder
enc = OneHotEncoder()
enc = enc.fit_transform(df[['City']]).toarray()
encoded_colm = pd.DataFrame(enc)
df = pd.concat([df, encoded_colm], axis=1)
df = df.drop(['City'], axis=1)
df

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])
df

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])
df
```
## Encoding Data.csv
```
import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/Encoding Data.csv")
df1 = df.copy()
df1

df.info()

df.isnull().sum()

df = pd.get_dummies(df, columns = ['bin_1','bin_2'])
df

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder, OneHotEncoder
climate = ['Cold','Warm','Hot']
enc = OrdinalEncoder(categories = [climate])
enc.fit_transform(df1[["ord_2"]])

df1['Ord_2'] = enc.fit_transform(df1[["ord_2"]])
df1

df2 = df1.copy()
le = LabelEncoder()
df2['Nom_0'] = le.fit_transform(df2[["nom_0"]])
df2

df3 = df2.copy()
oe = OneHotEncoder()
oe.fit_transform(df3[["bin_1"]])
df3

df4 = df3.copy()
oe = OneHotEncoder()
oe.fit_transform(df4[["bin_2"]])
df4

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['ord_2'] = le.fit_transform(df['ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(x ='ord_2', data = df)
```

## Titanic_dataset.csv
```
import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/titanic_dataset.csv")
df

df.info()

df.isnull().sum()

df['Age']=df['Age'] . fillna(df['Age'].mean())
df['Cabin']=df['Cabin']. fillna(df['Cabin']. mode() [0])
df['Embarked']=df['Embarked'] . fillna(df['Embarked'].mode( )[0])
df.isnull().sum()

from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
df['Sex'] = lc.fit_transform(df['Sex'])
sbn.set(style ="darkgrid")
sbn.countplot(x ='Sex', data = df)

from sklearn.preprocessing import OneHotEncoder
enc= OneHotEncoder()
enc= enc.fit_transform(df[['Name']]).toarray()
encoded_colm = pd.DataFrame(enc)
df= pd.concat([df, encoded_colm], axis=1)
df= df.drop(['Name'], axis=1)
df

df = pd.get_dummies(df, prefix=['Ticket'] ,columns=['Ticket'])
df

df = pd.get_dummies(df, prefix=['Embarked'] ,columns=['Embarked'])
df
```
# OUTPUT

## Data.csv

![31](https://user-images.githubusercontent.com/119218812/233465201-f44d283f-8653-47af-b7f4-641919cc1c0f.png)

![32](https://user-images.githubusercontent.com/119218812/233465243-8250371f-6fdc-4142-bd23-5d13f7475ec7.png)

![33](https://user-images.githubusercontent.com/119218812/233465279-f76c4f41-a8a2-46bb-b279-df9cd1de2417.png)

![34](https://user-images.githubusercontent.com/119218812/233465305-f536bcce-8eb0-4cf1-9c5a-c386b424bf3f.png)

![35](https://user-images.githubusercontent.com/119218812/233465332-30356672-d598-4509-ac6e-71a4c7e08763.png)

![36](https://user-images.githubusercontent.com/119218812/233465358-d70a79e1-2453-4c20-b736-366a27405538.png)


## Encoding Data.csv

![37](https://user-images.githubusercontent.com/119218812/233465401-fe57b4b6-0c39-40c2-9e4a-ad0a5da5662c.png)

![38](https://user-images.githubusercontent.com/119218812/233465430-c1c2edf6-5e38-467f-a0b7-1f8fbfe6643f.png)

![39](https://user-images.githubusercontent.com/119218812/233465468-bd37c4fd-fc39-4bd7-94e4-1a9aa26ab705.png)

![40](https://user-images.githubusercontent.com/119218812/233465499-2ca3e2de-2893-4ef0-abbc-add3121a8327.png)

![41](https://user-images.githubusercontent.com/119218812/233465544-626217a0-e98d-4e3a-ae5c-847a16a513db.png)

![42](https://user-images.githubusercontent.com/119218812/233465604-94189174-4ad5-42e1-8d73-f13b853cd86a.png)

![43](https://user-images.githubusercontent.com/119218812/233465634-2319d4ca-3a4b-4d92-8a5f-c8a2b173491e.png)

![44](https://user-images.githubusercontent.com/119218812/233465670-a22bf8fd-52a5-44c1-88ee-bdb9830d171f.png)

## Titanic_dataset.csv

![45](https://user-images.githubusercontent.com/119218812/233465717-618f9bc5-d6db-4aa7-a0e3-e1218327e07f.png)

![46](https://user-images.githubusercontent.com/119218812/233465741-7a449a3e-4c69-442b-beab-4bd18a95efef.png)

![47](https://user-images.githubusercontent.com/119218812/233465776-a575fd50-eb73-425d-86c7-10a59d95166b.png)

![48](https://user-images.githubusercontent.com/119218812/233465800-45610d93-e785-4c90-9a2f-1e47f4eb9468.png)

![49](https://user-images.githubusercontent.com/119218812/233465827-a5efb4c4-2189-4d3f-92d6-af4d9c7f7a6e.png)

![50](https://user-images.githubusercontent.com/119218812/233465853-2cfedbc2-1e92-47ac-91fc-c94f42a8d150.png)

![51](https://user-images.githubusercontent.com/119218812/233466031-6537991c-6416-4374-a759-835cecec615e.png)

![52](https://user-images.githubusercontent.com/119218812/233466057-09c89ded-6988-4124-9886-82b05ce3b911.png)


# Result

Thus the Feature Generation (also known as feature construction, feature extraction or feature engineering) methods for the given datasets is run successfully.
