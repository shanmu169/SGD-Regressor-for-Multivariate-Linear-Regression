# SGD-Regressor-for-Multivariate-Linear-Regression

## AIM:
To write a program to predict the price of the house and number of occupants in the house with SGD regressor.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Get the independent variables X and dependent variables Y from the dataset.
2. Convert the dataset into a Pandas DataFrame.
3. Split the dataset into training data (80%) and testing data (20%) using `train_test_split()`.
4. Create a Multiple Linear Regression model using `LinearRegression()` and train it using `fit()`.
5. Predict the house price and rent using `predict()` and display the predicted and actual values.
6. Give new house details to predict and display the house price in lakhs and rent per month.

## Program:
```
Program to implement the multivariate linear regression model for predicting the price of the house and number of occupants in the house with SGD regressor.
Developed by: Shanmuga priya K
RegisterNumber: 25004352 
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

data = {
    'Size': [1000, 1200, 1500, 1800, 2000, 2200, 2500, 2700],
    'Bedrooms': [2, 2, 3, 4, 4, 5, 5, 6],
    'Age': [10, 8, 5, 3, 2, 2, 1, 1],
    'Price': [45, 55, 70, 90, 100, 120, 135, 150],
    'Rent': [15000, 18000, 22000, 28000, 32000, 35000, 40000, 45000]
}

df = pd.DataFrame(data)

X = df[['Size', 'Bedrooms', 'Age']]
Y = df[['Price', 'Rent']]

X_train, X_test, Y_train, Y_test = train_test_split(
    X, Y, test_size=0.2, random_state=42
)

model = LinearRegression()
model.fit(X_train, Y_train)

predictions = model.predict(X_test)

print("Predicted Values:")
print(predictions)

print("\nActual Values:")
print(Y_test.values)

new_house = [[1600, 3, 4]]
prediction = model.predict(new_house)

print("\nPredicted House Price :", prediction[0][0], "Lakhs")
print("Predicted House Rent  :", prediction[0][1], "Rs/month")
```

## Output:
<img width="1782" height="382" alt="image" src="https://github.com/user-attachments/assets/4623db65-7069-4f6a-8fc8-3c132e5d6907" />



## Result:
Thus the program to implement the multivariate linear regression model for predicting the price of the house and number of occupants in the house with SGD regressor is written and verified using python programming.
