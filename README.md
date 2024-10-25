# House Price Prediction Model  

This project implements a **House Price Prediction Model** using **XGBoost (XGBRegressor)**. The goal is to predict the price of houses based on various features, using the **Boston House Price Dataset**.

---

## Overview  
The **Boston House Price Dataset** contains information about houses in the Boston area, with several features describing each property, such as crime rate, number of rooms, and property tax rate. This project leverages **XGBoost**, a powerful gradient boosting algorithm, to predict house prices based on these features.

---

## Dataset Description  
The dataset used is the **Boston House Price Dataset**, which contains the following features:

| Feature  | Description                               |
|----------|-------------------------------------------|
| CRIM     | Per capita crime rate by town            |
| ZN       | Proportion of residential land zoned for lots over 25,000 sq. ft. |
| INDUS    | Proportion of non-retail business acres per town |
| CHAS     | Charles River dummy variable (1 if tract bounds river; 0 otherwise) |
| NOX      | Nitric oxide concentration (parts per 10 million) |
| RM       | Average number of rooms per dwelling     |
| AGE      | Proportion of owner-occupied units built prior to 1940 |
| DIS      | Weighted distances to five Boston employment centers |
| RAD      | Index of accessibility to radial highways |
| TAX      | Full-value property tax rate per $10,000 |
| PTRATIO  | Pupil-teacher ratio by town              |
| B        | Proportion of Black residents by town    |
| LSTAT    | Percentage of lower status population    |
| PRICE    | Target variable: Median value of owner-occupied homes (in $1000s) |

---

## Model Performance  
### Training Data Results:  
- **R-squared Error:** 0.999998  
- **Mean Absolute Error:** 0.0091  

### Testing Data Results:  
- **R-squared Error:** 0.9052  
- **Mean Absolute Error:** 2.0749  

---

## Usage  
Here’s how you can use the model to predict house prices:

```python
# Example usage with test data
input_data = (0.00632, 18.0, 2.31, 0.0, 0.538, 6.575, 65.2, 4.0900, 1.0, 
              296.0, 15.3, 396.90, 4.98)

# Convert the input data to a numpy array for better processing
input_data_as_numpy_array = np.asarray(input_data)

# Reshape the data to make predictions for a single instance
input_data_reshaped = input_data_as_numpy_array.reshape(1, -1)

# Make the prediction using the trained model
predicted_price = model.predict(input_data_reshaped)

print(f"The predicted price of the house is: ${predicted_price[0] * 1000:.2f}")
```
