# 📊 Day 2: Multiple Linear Regression

On Day 2 of my Machine Learning journey, I explored **Multiple Linear Regression** — an extension of Simple Linear Regression where we use **two or more independent variables** to predict a single dependent variable.

---

## ✅ What I Learned

- What is Multiple Linear Regression
- When and why we use it
- Formula and meaning of coefficients
- Real-world example using numerical data
- How to build the model using Scikit-learn
- Predicting using user input
- Visualizing Actual vs Predicted values
---

## 📘 Theory

**Multiple Linear Regression** is a supervised learning algorithm used to predict 
a continuous outcome (dependent variable) based on multiple input features (independent variables).

It assumes a linear relationship between the dependent variable and the independent variables.

---

## 🔣 Formula

y = b0 + b1x1 + b2x2 + ... + bn*xn
Where:
- `y` = predicted output (dependent variable)
- `b0` = intercept (bias term)
- `b1, b2, ..., bn` = coefficients (slopes for each independent variable)
- `x1, x2, ..., xn` = independent variables

---

## 📁 Dataset

- **Name**: Advertising Dataset
- **Source**: [Kaggle – Advertising Dataset](https://www.kaggle.com/datasets/ashydv/advertising-dataset)
- **Target Variable**: `Sales`
- **Features Used**:
  - `TV` (advertising budget)
  - `Radio` (advertising budget)
  - `Newspaper` (advertising budget)
