# Machine Learning Specialization - Week 1 Notes

# What is Machine Learning?

Machine Learning (ML) is a subset of Artificial Intelligence (AI) that enables computers to learn patterns from data and make predictions or decisions without being explicitly programmed.

The performance of a machine learning model largely depends on the quality of the data.

Applications of Machine Learning:

* Spam Detection
* Recommendation Systems
* Speech Recognition
* Self-driving Cars
* Medical Diagnosis

---

# Types of Machine Learning

## 1. Supervised Learning

Supervised learning learns a mapping from input variables (**X**) to output variables (**Y**) using labeled data.

### Applications

* House Price Prediction
* Email Spam Detection
* Medical Diagnosis

### Types of Supervised Learning

### Regression

Predicts continuous numerical values.

Examples:

* House Price Prediction
* Temperature Prediction

### Classification

Predicts discrete categories or classes.

Examples:

* Spam / Not Spam
* Cancer Detection (Benign / Malignant)

---

## 2. Unsupervised Learning

Unsupervised learning discovers hidden patterns in unlabeled data.

Types:

### Clustering

Groups similar data points together.

Examples:

* Customer Segmentation
* News Grouping

### Anomaly Detection

Identifies unusual or abnormal examples.

Examples:

* Fraud Detection
* Manufacturing Defect Detection

### Dimensionality Reduction

Reduces the number of features while preserving important information.

Examples:

* Data Compression
* Data Visualization

---

# Linear Regression

Linear Regression is a supervised learning algorithm used to predict continuous numerical values.

The objective is to learn a function that maps inputs (**x**) to outputs (**y**).

Example:

| House Size | Price |
| ---------- | ----- |
| 1000       | 300   |
| 1500       | 450   |
| 2000       | 600   |

---

# Training Set Notation

* **x** : Input feature
* **y** : Output / Target variable
* **m** : Number of training examples
* **(x⁽ⁱ⁾, y⁽ⁱ⁾)** : i-th training example

Example:

```text
(x¹, y¹)
(x², y²)
...
(xᵐ, yᵐ)
```

---

# Model Representation

The hypothesis or model is represented as:

Where:

* **w** = Weight (slope)
* **b** = Bias (intercept)
* **f(x)** = Prediction

Goal:

Find values of **w** and **b** such that predictions closely match the actual values.

---

# Cost Function

The cost function measures how well the model fits the training data.

For Linear Regression:

Where:

* **J(w,b)** = Cost
* **m** = Number of training examples

Goal:

Choose **w** and **b** that minimize **J(w,b)**.

Prediction Error:

```text
Error = Predicted Value - Actual Value

Error = ŷ - y
```

---

# Gradient Descent

Gradient Descent is an optimization algorithm used to minimize the cost function.

It repeatedly updates the parameters **w** and **b** to reduce the cost.

Steps:

1. Initialize w and b.
2. Compute gradients.
3. Update parameters.
4. Repeat until convergence.

Parameter update rules:

Where:

* **α** = Learning Rate

---

# Gradient Computation

Derivative with respect to w:

Derivative with respect to b:

---

# Learning Rate (α)

The learning rate controls the step size during gradient descent.

* Too small → Learning becomes slow.
* Too large → Algorithm may diverge.
* Proper value → Faster convergence.

---

# Convergence

Gradient Descent converges when:

```text
Cost decreases and eventually stops changing significantly.
```

Typically, the Cost vs Iterations graph looks like:

```text
High Cost
    |
    |\
    | \
    |  \
    |   \____
    |
    +----------------> Iterations
```

---

# Key Takeaways

* Machine Learning learns patterns from data.
* Supervised Learning uses labeled data.
* Linear Regression predicts continuous values.
* Cost Function measures model performance.
* Gradient Descent minimizes the cost.
* The objective is to find optimal values of w and b.
