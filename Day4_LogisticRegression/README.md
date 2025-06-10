# 📘 Logistic Regression – Theory (Day 3)

## 🔹 What is Logistic Regression?
- Logistic Regression is a **supervised machine learning algorithm** used for **binary classification** problems.
- It predicts the **probability** that a given input belongs to a particular class (0 or 1).
- Despite its name, it's used for **classification**, not regression.

---

## 🔹 When to Use Logistic Regression?
- When your **target variable is categorical** (typically binary).
- Examples:
  - Email: Spam (1) or Not Spam (0)
  - Exam: Pass (1) or Fail (0)
  - Customer: Churn (Yes/No)

---

## 🔹 How Does It Work?
1. Logistic Regression first calculates:
       z = b0 + b1x1 + b2x2 + ... + bn*xn
2. Then applies the **Sigmoid Function**:
       P = 1 / (1 + e^(-z))
3. The output is a probability `P` between 0 and 1.

---

## 🔹 Decision Rule
- If `P > 0.5` → Predict class `1`
- If `P ≤ 0.5` → Predict class `0`

---

## 🔹 Sigmoid Function Graph
- S-shaped curve.
- Converts linear value to range between 0 and 1.
- Used to calculate the probability of the output class.
- ![image](https://github.com/user-attachments/assets/6a223899-afd4-4ec3-a8c9-112d6f6359cc)


---

## 🔹 Linear vs Logistic Regression

| Feature            | Linear Regression         | Logistic Regression             |
|--------------------|---------------------------|----------------------------------|
| Output             | Any real number           | Probability (0 to 1)             |
| Problem Type       | Regression                | Classification                   |
| Function Used      | Linear Function           | Sigmoid Function                 |
| Target Variable    | Continuous                | Categorical                      |

---

## 🔹 Important Terms
- **Probability**: Model output is a probability score.
- **Threshold**: Default is 0.5. You can change it.
- **Sigmoid**: Function that squashes output between 0 and 1.
- **Decision Boundary**: The point at which classification changes (e.g., 0.5).

---


