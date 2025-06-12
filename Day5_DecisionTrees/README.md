# 🌳 ML Day 5: Decision Tree - Theory

Today I covered the **theory of Decision Trees**, one of the most important ML models used for both **classification** and **regression** tasks.

---

## 📌 What is a Decision Tree?

A **Decision Tree** is a flowchart-like structure that splits data into smaller groups using decision rules.  
Each node represents a feature (attribute), and each leaf node represents an output (class or value).

---

## ✅ Why Use Decision Trees?

- Easy to understand and visualize
- Handles both numerical and categorical data
- No need for scaling or normalization
- Works even with missing values

---

## 🧠 How It Works:

1. Start from the **root node**.
2. Find the best **feature to split** using a metric.
3. Split the data.
4. Repeat for each child node until pure or stopping condition.

---

## 📚 Key Terms

| Term             | Meaning                                     |
|------------------|---------------------------------------------|
| Root Node        | The first/main decision point               |
| Leaf Node        | The final output (class/value)              |
| Internal Node    | Decision node between root and leaf         |
| Split            | Condition to divide the data                |
| Depth            | Number of layers in the tree                |

---

## 🧪 Splitting Criteria

### 📊 For Classification:
- **Gini Impurity**
- **Entropy / Information Gain**

### 🔢 For Regression:
- **Mean Squared Error (MSE)**
- **Mean Absolute Error (MAE)**

---

## ✂️ Overfitting & Pruning

- **Overfitting**: Tree becomes too complex and fits training data too closely.
- **Pruning**: Reduces tree size to generalize better.

Types:
- **Pre-pruning**: Stop tree growth early using max_depth, min_samples_split, etc.
- **Post-pruning**: Cut extra branches after full tree is built.

---

## 👍 Pros & 👎 Cons

| Pros                          | Cons                                      |
|-------------------------------|-------------------------------------------|
| Easy to interpret             | Can overfit easily                        |
| Handles mixed data types      | Unstable to small data changes            |
| No normalization needed       | Can be biased if one feature dominates    |

---

## 🔍 Real-World Examples

- Predicting if a student passes based on marks & attendance
- Will a customer buy based on age & income
- Loan approval based on credit history

