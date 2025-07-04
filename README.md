<H3>NAME : Sadhana Shree B</H3>
<H3>REGISTER NO: 212223230177</H3>
<H3>EX. NO.1</H3>
<H3>DATE: 04/04/2025</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:

```
STEP 1: Importing the libraries
import pandas as pd
import numpy as np
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.model_selection import train_test_split
from IPython.display import display  # For table output

# STEP 2: Importing the dataset
dataset = pd.read_csv('/mnt/data/Churn_Modelling.csv')
print("Original Dataset:")
display(dataset.head())

# Drop unnecessary columns
dataset.drop(['RowNumber', 'CustomerId', 'Surname'], axis=1, inplace=True)

# STEP 3: Taking care of missing data
dataset.fillna(dataset.mean(numeric_only=True), inplace=True)

# STEP 4: Encoding categorical data
le = LabelEncoder()
dataset['Geography'] = le.fit_transform(dataset['Geography'])
dataset['Gender'] = le.fit_transform(dataset['Gender'])

print("After encoding 'Geography' and 'Gender':")
display(dataset[['Geography', 'Gender']].head())

# STEP 5: Normalizing the data
X = dataset.drop('Exited', axis=1)  # 'Exited' is the target
y = dataset['Exited']

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

print("First 5 rows after Normalization:")
display(pd.DataFrame(X_scaled, columns=X.columns).head())

# STEP 6: Splitting the data
X_train, X_test, y_train, y_test = train_test_split(X_scaled, y, test_size=0.2, random_state=42)

print("Dataset Shapes:")
print("X_train:", X_train.shape)
print("X_test:", X_test.shape)
print("y_train:", y_train.shape)
print("y_test:", y_test.shape)
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/4b31f512-5b69-4005-8da3-007518ced401)
![image](https://github.com/user-attachments/assets/6baa2d5a-ab18-4b69-bc86-76e42b73a7c1)




## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


