# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import pandas as pd and import the required dataset.<br>
2.Calculate the null values in the dataset.<br>
3.Import the LabelEncoder from sklearn.preprocessing<br>
4.Convert the string values to numeric values.<br>
5.Import train_test_split from sklearn.model_selection.<br>
6.Assign the train and test dataset.<br>
7.Import DecisionTreeRegressor from sklearn.tree.<br>
8.Import metrics from sklearn.metrics.<br>
9.Calculate the MeanSquareError.<br>
10.Apply the metrics to the dataset.<br>
11.Predict the output for the required values.<br>

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: G Venkata Pavan Kumar
RegisterNumber: 212221240013
*/
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x= data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2,random_state = 2)

from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)

from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse

r2= metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
![ML1](https://user-images.githubusercontent.com/94827772/173214269-3da331e3-e1a1-4964-928d-22d7ecc8fa30.png)

![ML2](https://user-images.githubusercontent.com/94827772/173214267-b14c4392-e775-4665-a8cf-60e2850591cc.png)

![ML3](https://user-images.githubusercontent.com/94827772/173214265-22af9af6-b9c3-4d3d-8cad-1011062a9cec.png)

![ML4](https://user-images.githubusercontent.com/94827772/173214264-11a5e9c3-c600-4715-a64d-f7d2704f1443.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
