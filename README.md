# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM :
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required :
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset
5. Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program & Output :
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: ALIYA SHEEMA
RegisterNumber:  212223230011
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
```

![image](https://github.com/user-attachments/assets/9f4056de-94c9-4299-8765-0346da752f96)

```
data.info()
```

![image](https://github.com/user-attachments/assets/60df67a1-0e49-44f5-8ba2-351b94fe9c98)

```
data.isnull().sum()
```

![image](https://github.com/user-attachments/assets/b83a2514-e5c1-4327-870a-2a455aeef1ec)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![image](https://github.com/user-attachments/assets/22f73df5-d49b-45c9-b291-2b7e2fd410d5)

```
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y, test_size=0.2, random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train, y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse
```

![image](https://github.com/user-attachments/assets/52e50662-cab1-4fd7-aa65-4d5290daf9e6)

```
r2=metrics.r2_score(y_test,y_pred)
r2
```

![image](https://github.com/user-attachments/assets/d19c384e-cb3a-4c3b-b013-779c16bf2c69)

```
dt.predict([[5,6]])
```

![image](https://github.com/user-attachments/assets/f6254b43-1425-43d5-86b8-e87bf5d14bd0)


## Result :
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
