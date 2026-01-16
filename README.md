# Machine Learning Car Price Prediction

The aim of this project is to introduce to the basic concept behind machine learning.

```
.
├── .gitignore          # Excludes __pycache__, .DS_Store, *.pyc
├── README.md           # Project documentation
├── data.csv            # Training dataset (miles, price)
├── prediction.py       # Predict price from mileage
├── thetas.csv          # Learned theta0 (intercept), theta1 (slope)
└── train.py            # Train linear regression model
```

## Project Overview

Implements simple linear regression from scratch to predict car prices based on mileage using gradient descent. No external ML libraries - pure NumPy math operations

understanding of the following key components:
- Linear regression for predictive modeling
- Gradient descent algorithm for model training
- Data preprocessing and feature engineering
- Model evaluation and performance metrics

## Getting Started

To launch this project, you need follow these steps:

1. Clone the repository to your local machine:

   ```shell
   git clone https://github.com/ychibani/__linear_regression
  
2. Download the packages
   
   ```shell
   python3 -m pip install numpy matplotlib pandas
   
This project includes a sample dataset for car prices that you can use for training and testing your machine learning model. However, the knowledge and skills you gain from this project can be applied to any other dataset, allowing you to make predictions on various types of data.

3. launch the programs :

   ```shell
   python train.py -g
   ```

## Training Parameters

- **Learning rate (α)**: 0.1-0.5 (too high → diverge, too low → slow)
- **Normalization**: Essential for gradient stability
- **MSE**: `1/m * sum((h - y)^2)`

Train the model, print a graph of the gradient descent algorithm, ask the number of time we train the model as an input and calculate the thetas that will be sent in thetas.csv for predictions.py

![testle](https://github.com/ychibani42/__linear_regression/assets/55283897/7f8e6fad-081a-4912-9a09-986c3072f927)

   ```shell
   python predictions.py -g <price or data to predict>
   ```
Ask a mileage or a data input you want to predict with the values given in data.csv, get the thetas from thetas.csv and print a graph, and print a percentage of how relevant is my model, and the prediction

![example](https://github.com/ychibani42/__linear_regression/assets/55283897/3fd5ed06-9f44-4bd1-9d60-de690616b527)


## Algorithm explanation

```
1. Load data.csv (miles, price)
2. Normalize features: x = (miles - min) / (max - min)
3. Initialize: theta0=0, theta1=0
4. Gradient Descent (1000 iterations):
   for i in range(1000):
       h = theta0 + theta1 * x
       theta0 -= alpha * mean(h - y) / m
       theta1 -= alpha * mean((h - y) * x) / m
5. Save thetas.csv
```

| Miles | Predicted Price |
|-------|----------------|
| 50k   | ~$35,000      |
| 100k  | ~$25,000      |
| 150k  | ~$15,000      |
| 200k  | ~$5,000       |

