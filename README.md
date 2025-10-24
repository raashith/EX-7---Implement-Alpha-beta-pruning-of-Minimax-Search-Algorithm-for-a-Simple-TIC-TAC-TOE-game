# EX 7 Implementation of Decision Tree Regressor Model for Predicting the Salary of the Employee
## DATE:
## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the data.

2.Preprocessing the data.

3.split the data into training and testing sets.

4.Train the Decision Tree Regressor.

5.Evaluate the models Performance.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: RAASHITH RUHULLA R 
RegisterNumber:  2305002018
*/
```
```
import pandas as pd
data=pd.read_csv("/content/Salary_EX7.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
x.head()
y=data["Salary"]

from sklearn.model_selection import train_test_split
xtrain,xtest,ytrain,ytest=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(xtrain,ytrain)
y_pred=dt.predict(xtest)

from sklearn import metrics
mse=metrics.mean_squared_error(ytest,y_pred)
mse

r2=metrics.r2_score(ytest,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
![Screenshot 2024-10-17 103647](https://github.com/user-attachments/assets/4e211138-0aec-413a-af80-7614145f150d)<p>
![Screenshot 2024-10-17 103359](https://github.com/user-attachments/assets/e65374a7-b546-4ce8-ac37-3bb633254a04)
![Screenshot 2024-10-17 103427](https://github.com/user-attachments/assets/2ff52bae-b1d8-4337-a5df-9d81a0f05f36)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.

