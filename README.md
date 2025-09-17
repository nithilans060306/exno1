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
```python
import numpy as np
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```
## Output
<img width="1074" height="750" alt="image" src="https://github.com/user-attachments/assets/dcb7d705-ef84-497b-bab7-9c1eda5e7326" />

```python
df.head(4)
```

## Output
<img width="1077" height="178" alt="image" src="https://github.com/user-attachments/assets/3c4c5bdd-de59-4838-8284-4591a0f99746" />

```python
df.tail(7)
```

## Output
<img width="1103" height="292" alt="image" src="https://github.com/user-attachments/assets/ad629a8e-4cd2-4bf2-9778-169b95c1aab6" />

```python
df.isnull()
```

## Output
<img width="931" height="759" alt="image" src="https://github.com/user-attachments/assets/f6c7f865-31d6-426e-acf9-b76e4645c2a5" />

```python
df.notnull()
```

## Output
<img width="938" height="768" alt="image" src="https://github.com/user-attachments/assets/4c8e2554-d847-46e6-9342-5749f26d1212" />

```python
df.isnull().sum()
```

## Output
<img width="419" height="342" alt="image" src="https://github.com/user-attachments/assets/3a629bdf-9338-4c98-a9b1-8c5d0cf97aba" />

```python
df.isnull().any()
```

## Output
<img width="426" height="344" alt="image" src="https://github.com/user-attachments/assets/1ee5bd43-e77a-48b7-bbc6-3af3b6479244" />

```python
df.dropna(axis=1)
```

## Output
<img width="551" height="759" alt="image" src="https://github.com/user-attachments/assets/fe2a2022-e815-419d-837a-bcd19f49574a" />

```python
df.dropna(axis=0)
```

## Output
<img width="1130" height="496" alt="image" src="https://github.com/user-attachments/assets/c11081c9-173c-4efd-878a-72f1d99048c5" />

```python
df.fillna(0)
```

## Output
<img width="1125" height="756" alt="image" src="https://github.com/user-attachments/assets/92274f59-0562-46fd-acee-6cf06ced1faf" />

```python
df.fillna(method='ffill')
```

## Output
<img width="1585" height="829" alt="image" src="https://github.com/user-attachments/assets/9e521950-e3ac-4a4d-8b34-6767d2c9b0ff" />

```python
df.bfill()
```

## Output
<img width="1087" height="749" alt="image" src="https://github.com/user-attachments/assets/4b4dc42d-000f-417c-b6da-184b1b90671e" />

```python
df.fillna({'REGNO': 0, 'NAME': 'PRAVEEN'})
```

## Output
<img width="1094" height="760" alt="image" src="https://github.com/user-attachments/assets/2dae20be-e5b6-45fa-8220-01eca4137254" />

```python
iris = pd.read_csv("C:\DS\iris.csv")
iris
```

## Output
<img width="774" height="480" alt="image" src="https://github.com/user-attachments/assets/0eb41135-257d-4690-b6d1-996e0490004c" />

```python
iris.describe()
```

## Output
<img width="636" height="318" alt="image" src="https://github.com/user-attachments/assets/8fd12b05-413e-4c6e-ae69-643d6e030c29" />

```python
import seaborn as sns
sns.boxplot(x="sepal_length", data=iris)
```

## Output
<img width="759" height="623" alt="image" src="https://github.com/user-attachments/assets/0c4bc665-3f84-442e-8bd6-c7a76a674f4d" />

```python
q1 = iris.sepal_width.quantile(0.25)
q3 = iris.sepal_width.quantile(0.75)
iqr = q3 - q1
iqr
```

## Output
<img width="202" height="71" alt="image" src="https://github.com/user-attachments/assets/41be0172-95db-4333-8b72-086162a11624" />

```python
rid = iris[((iris.sepal_width<(q1-1.5*iqr))|(iris.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```

## Output
<img width="444" height="173" alt="image" src="https://github.com/user-attachments/assets/d5dac8d7-47f8-412f-9dcc-9122c72d8101" />

```python
rid = iris[~((iris.sepal_width<(q1-1.5*iqr))|(iris.sepal_width>(q3+1.5*iqr)))]
rid
```

## Output
<img width="748" height="480" alt="image" src="https://github.com/user-attachments/assets/dd819d14-b061-43ae-8f8b-f8d5850a8f6b" />

```python
rid = iris[((iris.sepal_width>(q1-1.5*iqr))&(iris.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```

## Output
<img width="582" height="321" alt="image" src="https://github.com/user-attachments/assets/8232e3db-10ce-4077-99d3-d7d33adacabb" />

```python
import scipy.stats as stats
z = np.abs(stats.zscore(iris.sepal_width))
z
```

## Output
<img width="754" height="760" alt="image" src="https://github.com/user-attachments/assets/b2177ecb-403a-4c4c-84e0-66b9cbaf0fdd" />


# Result
Thus the programs are executed sucessfully
