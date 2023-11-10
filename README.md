# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the libraries and read the data frame using pandas.


2.Calculate the null values present in the dataset and apply label encoder.


3.Determine test and training data set and apply decison tree regression in dataset.


4.Calculate Mean square error,data prediction and r2.

## Program:
```
/*
Developed by: HEMAPRASAD N
RegisterNumber: 212222040054
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
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)


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
  
```


## Output:
data.head()


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/7d2c7db8-a5d5-4705-b3e2-53d2c484c0da)


data.info()


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/6912db9e-d772-45aa-b46e-12bfb457cda7)


isnull() and sum()


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/069ff2ca-a6c1-402b-afd8-734b8cdc5c73)


data.head() for salary


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/d2272561-4219-4011-b8f0-7e3567dfe3fe)


MSE value


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/7b1b398e-fe74-4d55-b6ee-a62ca2ac5ed0)


r2 value


![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/9e8e1eee-2a83-4338-bfb0-79137166f5c5)


data prediction



![image](https://github.com/Hemaprasad-N/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/135933397/3f46d904-3fb8-4e82-8d92-ee4ac12ab54c)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
