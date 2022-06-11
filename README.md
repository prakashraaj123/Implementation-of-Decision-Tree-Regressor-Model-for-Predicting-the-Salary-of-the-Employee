# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program
2. import pandas and the required "Employee.csv" file
3. print data.head(),data.info() and count the values in "left" column
4. import LabelEncoder and transform values in "salary" column
5. assign x values,y values from dataset and import the train_test_split
6. split the dataset into train and test data where test_size=0.2 and random_state=100
7. after splitting dataset , import DecisionTreeClassifier and import metrics
8. finally use dt.predict()
9. Stop the program. 
 
 
 

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by:S.prakash Raaj
RegisterNumber:212220040120  
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
![Decision Tree Regressor Model for Predicting the Salary of the Employee](/datahead.PNG)
![Decision Tree Regressor Model for Predicting the Salary of the Employee](/datahead1.PNG)
![Decision Tree Regressor Model for Predicting the Salary of the Employee](/metrics.PNG)
![Decision Tree Regressor Model for Predicting the Salary of the Employee](/scoremetrics.PNG)
![Decision Tree Regressor Model for Predicting the Salary of the Employee](/predict'.PNG)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
