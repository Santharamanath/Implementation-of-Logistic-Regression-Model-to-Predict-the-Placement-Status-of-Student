# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries such as pandas module to read the corresponding csv file.
2. Upload the dataset values and check for any null or duplicated values using .isnull() and .duplicated() function respectively.
3. Import LabelEncoder and encode the corresponding dataset values.
4. Import LogisticRegression from sklearn and apply the model on the dataset using train and test values of x and y and Predict the values of array using the variable y_pred.
5.Calculate the accuracy, confusion and the classification report by importing the required modules such as accuracy_score, confusion_matrix and the classification_report from sklearn.metrics module.
6.Apply new unknown values and print all the acqirred values for accuracy, confusion and the classification report.
## Program:
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: SANTHA RAMANATH M
RegisterNumber:  212223220097
```
import pandas as pd
data=pd.read_csv('Placement_Data.csv')
data.head()


data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis = 1)#removes the specified row or column
data1.head()


data1.isnull().sum()


data1.duplicated().sum()


from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"] = le.fit_transform(data1["gender"])
data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
data1["degree_t"] = le.fit_transform(data1["degree_t"])
data1["workex"] = le.fit_transform(data1["workex"])
data1["specialisation"] = le.fit_transform(data1["specialisation"])
data1["status"] = le.fit_transform(data1["status"])
data1


x=data1.iloc[:,:-1]
x


y=data1["status"]
y


from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size = 0.2,random_state = 0)


from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver = "liblinear")# a library for large
lr.fit(x_train,y_train)
y_pred = lr.predict(x_test)
y_pred
*/
```
## Output:

![316212969-12bb2274-5169-4b9b-987b-781fbb47f0fa](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/8b61269a-4626-484e-a1d9-54f2da9b7ab0)

![316212978-27aad290-0a32-45fa-a264-5245c8480a2b](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/36f6c46f-8248-49cc-986d-73a16ea24a49)

![316212992-8f50e42e-42dd-4fd4-b334-9ba88ebbbf9d](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/d6a44ea7-0dd1-4b4a-b1bc-54966a45d81d)

![316212999-ff4b62be-c03c-4370-898f-8c6cdbb78095](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/0da214d5-6ba3-47d6-b3c3-2fa1a9d99076)

![316213027-267da2db-54e5-425c-921a-4c59b1e7f6ab](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/ac4e38bc-8f27-441b-9f87-77087a1fc0a2)

![316213037-8eaa8827-2756-40a2-8671-44b3bd6a2ce5](https://github.com/Santharamanath/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/149035289/b692df9f-ea78-432d-8f6e-4d7da3c5d2cf)

## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
