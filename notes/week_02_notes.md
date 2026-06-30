# Machine Learning Specialization - Week 2 Notes

# Multiple Linear Regression

Multiple Linear Regression is an extension of Linear Regression that uses multiple input features to predict an output.

Instead of using a single feature, the model learns from multiple features simultaneously.

Example:

Predicting House Price using:

* Area
* Number of Bedrooms
* Number of Floors
* Age of House

Example Training Example:

```text
x = [2104, 5, 1, 45]

---

Multiple Feature Notation
n : Number of features
x : Feature vector
xⱼ : j-th feature
x⁽ⁱ⁾ : i-th training example
xⱼ⁽ⁱ⁾ : j-th feature of the i-th training example
w : Weight vector
b : Bias parameter

Example:

x⁽¹⁾ = [2104, 5, 1, 45]
Multiple Linear Regression Model

The hypothesis function for multiple variables is:

f(x) = w₁x₁ + w₂x₂ + w₃x₃ + ... + wₙxₙ + b

or in vectorized form:

f(x) = w · x + b

where:

w = Weight vector
x = Feature vector
b = Bias term

Goal:

Find values of w and b such that predictions closely match the actual values.

---

Vectorization

Vectorization allows us to perform operations on entire arrays without explicitly using loops.

Instead of:

prediction = 0

for i in range(n):
    prediction += w[i] * x[i]

prediction += b

We use:

prediction = np.dot(w, x) + b

Advantages:

Faster computation
Cleaner code
Efficient for large datasets
Cost Function for Multiple Variables

The cost function measures how well the model fits the training data.

For Multiple Linear Regression:

J(w,b) = (1 / 2m) Σ (f(x⁽ⁱ⁾) - y⁽ⁱ⁾)²

where:

J(w,b) = Cost Function
m = Number of training examples

Goal:

Choose values of w and b that minimize J(w,b).

---

Prediction Error:

Error = Predicted Value - Actual Value

Error = ŷ - y

---

Gradient Descent for Multiple Variables

Gradient Descent is an optimization algorithm used to minimize the cost function.

It repeatedly updates the parameters w and b to reduce the cost.

Steps:

Initialize w and b.
Compute gradients.
Update parameters.
Repeat until convergence.

Parameter Update Rules:

wⱼ = wⱼ - α (∂J / ∂wⱼ)

b = b - α (∂J / ∂b)

where:

α = Learning Rate
Gradient Computation

Derivative with respect to each weight:

∂J/∂wⱼ = (1/m) Σ (f(x⁽ⁱ⁾) - y⁽ⁱ⁾) xⱼ⁽ⁱ⁾

Derivative with respect to bias:

∂J/∂b = (1/m) Σ (f(x⁽ⁱ⁾) - y⁽ⁱ⁾)
Feature Scaling

Feature Scaling transforms features to a similar range.

Example:

Area	Bedrooms
2000	5
1000	2

The feature Area has much larger values than Bedrooms.

Without Feature Scaling, Gradient Descent may converge slowly.

Benefits:

Faster convergence
Improved optimization
Prevents oscillations during training
Mean Normalization

Mean Normalization scales features using:

x = (x - mean) / (max - min)

where:

mean = Average value of the feature
max = Maximum value
min = Minimum value
Z-Score Normalization

Z-Score Normalization transforms features such that:

Mean ≈ 0
Standard Deviation ≈ 1

Formula:

x = (x - μ) / σ

where:

μ = Mean
σ = Standard Deviation
Checking Gradient Descent Convergence

Gradient Descent converges when:

Cost decreases and eventually stops changing significantly.

Typically, the Cost vs Iterations graph looks like:

High Cost
    |
    |\
    | \
    |  \
    |   \____
    |
    +----------------> Iterations

If the cost consistently decreases, Gradient Descent is converging.

--- 

Learning Rate (α)

The learning rate controls the step size during Gradient Descent.

Too small → Learning becomes slow.
Too large → Algorithm may diverge.
Proper value → Faster convergence.

Common values:

alpha = 0.1
alpha = 0.01
alpha = 0.001
alpha = 0.0001
Feature Engineering

Feature Engineering involves creating new features from existing features to improve model performance.

Examples:

area = frontage * depth

age_per_room = age / rooms

Feature Engineering can significantly improve prediction accuracy.

--- 

Key Takeaways

Multiple Linear Regression uses multiple features for prediction.

Vectorization using np.dot() improves efficiency.

Gradient Descent minimizes the cost function.

Feature Scaling speeds up convergence.

Mean Normalization and Z-Score Normalization are commonly used scaling techniques.

Choosing an appropriate learning rate is essential.

Feature Engineering can improve model performance.