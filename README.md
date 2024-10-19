# Import necessary libraries

Import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split

from sklearn.linear_model import Linear Regression

2

from sklearn.metrics import mean_squared_error, r2 score

# Sample dataset: House prices based on square footage, bedrooms, and bathrooms

data = {

'Square Footage': [1500, 1800, 2400, 3000, 3500, 4000, 4500, 5000), 'Bedrooms': [3, 3, 4, 4, 5, 5, 5, 6], 'Bathrooms': [2, 2, 3, 3, 4, 4, 4, 5], 'Price': [300000, 350000, 500000, 600000, 700000, 750000, 800000, 1000000]

#Convert data into a DataFrame df = pd.DataFrame(data)

#Features (X) and target variable (y) X = df[['SquareFootage', 'Bedrooms', 'Bathrooms']] y = df['Price"]

#Split the dataset into training and testing sets (80% train, 20% test)

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

#Create a Linear Regression model model Linear Regression()

#Train the model on the training data model.fit(X_train, y_train)

# Predict house prices on the test data
y_pred model.predict(X_test)

# Evaluate the model's performance

mse = mean_squared_error(y_test, y_pred)

r2=r2_score(y_test, y pred).

# Print evaluation metrics

print(f"Mean Squared Error: (mse:.2f}")

print(f"R-squared: (r2:.2f]")


#Example prediction

new_house = np.array([[3000, 4, 3]])

predicted_price model.predict(new_house)

print(f"Predicted price for a house with 3000 sqft, 4 bedrooms, and 3 bathrooms: $(predicted_price[0]:..2f]")

#Visualization of actual vs predicted prices

plt.figure(figsize=(10, 6))

plt.scatter(y_test, y_pred, color='blue')

plt.plot([min(y_test), max(y_test)], [min(y_test), max(y_test)], color='red', linestyle='--')

plt.xlabel('Actual Prices')

plt.ylabel('Predicted Prices')

plt.title('Actual vs Predicted House Prices')

plt.grid()

plt.show()
