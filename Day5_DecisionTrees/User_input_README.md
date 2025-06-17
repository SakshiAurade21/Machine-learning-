
## 🚗 Car Acceptability Prediction (User Input + Decision Tree)

This project predicts car acceptability using **user inputs** and a **Decision Tree Classifier**. It includes data preprocessing, label encoding, model training, and interactive prediction using categorical data.

---

## 📌 Dataset Details

* **Dataset Name:** Car Evaluation Dataset
* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/elikplim/car-evaluation-dataset)
* **Format:** CSV
* **Type:** All **categorical** features
* **Target Column:** `CarAcceptable` (unacc, acc, good, vgood)

### 🔸 Features:

* BuyingPrice
* MaintCost
* NumDoors
* Capacity
* BootSize
* SafetyLevel

---

## 🧠 Project Flow (with Reasoning)

### 1. 🔄 **Reading Data**

```python
data = pd.read_csv("car_evaluation.csv")
```

**Why?**
To load dataset into a DataFrame and start the preprocessing pipeline.

---

### 2. 🏷️ **Renaming Columns**

```python
data.rename(columns={
    "vhigh":'BuyingPrice', "vhigh.1":'MaintCost',
    "2":'NumDoors', "2.1":'Capacity',
    "small":'BootSize', "low":'SafetyLevel',
    "unacc":'CarAcceptable'
}, inplace=True)
```

**Why?**
Original column names were hard to read. Renaming helps make code understandable.

---

### 3. 🧼 **Label Encoding Categorical Columns**

```python
le = LabelEncoder()
data["BuyingPrice"] = le.fit_transform(data["BuyingPrice"])
# Similarly for other columns...
```

**Why Label Encoding?**
ML models can’t process text directly.
We use `LabelEncoder` to convert **categories → numbers** (e.g., low = 1, high = 3).

### 📌 Common Question:

> Why not just use `int()` or `.astype()`?

Because:

* `astype(int)` only works on **numeric strings**, not category names like `"low"` or `"med"`.
* `LabelEncoder()` is designed to handle and **remember mappings** like `"low"` → 0.

---

### 4. ✂️ **Splitting Train & Test Sets**

```python
X = data.drop("CarAcceptable", axis=1)
y = data["CarAcceptable"]
X_train, X_test, y_train, y_test = train_test_split(X, y, train_size=0.8)
```

**Why?**
To train the model on 80% data and test on 20% to check accuracy.

---

### 5. 🌲 **Training Decision Tree Classifier**

```python
model = tree.DecisionTreeClassifier()
model.fit(X_train, y_train)
```

**Why Decision Tree?**

* Simple and interpretable
* Handles categorical data well
* Good for beginner-friendly classification tasks

---

### 6. ⌨️ **User Input & Live Prediction**

```python
BuyingPrice = input("Choose one: high, med, low: ")
# Get other inputs...
```

**Then use:**

```python
le_BuyingPrice.transform([BuyingPrice])[0]
```

**Why?**
To convert user’s **string input** into a **numerical value** (just like in training).

> `[0]` is used to get the number out of the list.

**Final step:**

```python
user_input = [[...transformed_values...]]
prediction = model.predict(user_input)
```

---

### 7. 🌳 **Visualizing Decision Tree**

```python
tree.plot_tree(model)
```

**Why?**
To visualize how the decision tree splits data step-by-step.
It helps in understanding model logic.

> Optional: Can visualize only training tree — not based on single user input.

---

## ✅ Example Output

```bash
BuyingPrice = med
MaintCost = high
...
→ Prediction: acc
```

---

## ❓ Questions Covered (with Solutions)

| ❓ Question                          | ✅ Answer                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| Why encode data?                    | ML models can’t read text — we convert to numbers.                  |
| Why not use `int()` or `.astype()`? | They can’t handle strings like `"low"` — use `LabelEncoder`.        |
| Why `[0]` in `transform()`?         | It returns a list like `[2]`, we need the value `2`.                |
| How to take user input?             | Use `input()`, transform using `.transform()`, predict using model. |
| Can we visualize model?             | Yes, using `plot_tree(model)` after training.                       |
| What is DecisionTree good for?      | Simple, works well for categorical data, easy to interpret.         |

---

## 📝 To-Do Covered

* [x] Load & preprocess data
* [x] Encode categorical features
* [x] Train Decision Tree model
* [x] Take user input and predict
* [x] Explain `[0]`, `LabelEncoder`, and encoding
* [x] Visualize decision tree
* [x] Document everything clearly

