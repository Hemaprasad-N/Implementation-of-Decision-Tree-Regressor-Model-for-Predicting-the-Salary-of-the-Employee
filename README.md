# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries
2. Read the data frame using pandas
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column inoreder to convert into numerical values.
5. Determine training and test data set.
6. Apply decision tree regression on to the dataframe.
7. Get the values of Mean square error, r2 and data prediction.

## Program:
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: HEMAPRASAD.N
RegisterNumber:  212222040054
*/

import pandas as pd
data=pd.read_csv("/content/Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])

## Output:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](sam.png)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/7d2c7db8-a5d5-4705-b3e2-53d2c484c0da)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/6912db9e-d772-45aa-b46e-12bfb457cda7)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/069ff2ca-a6c1-402b-afd8-734b8cdc5c73)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/d2272561-4219-4011-b8f0-7e3567dfe3fe)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/7b1b398e-fe74-4d55-b6ee-a62ca2ac5ed0)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/9e8e1eee-2a83-4338-bfb0-79137166f5c5)
![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/3f46d904-3fb8-4e82-8d92-ee4ac12ab54c)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
