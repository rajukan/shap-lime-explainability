# Model Explainability

## What is Model Explainability?

Model explainability refers to the ability to **understand and interpret how a machine learning model makes decisions**.  
For example, if a healthcare model predicts whether a patient has a particular disease, medical practitioners must understand **which parameters influence the prediction** and whether the model contains **any bias**. Therefore, once a model is deployed in the real world, developers must be able to **explain its behavior and decisions**.

---

## Why is Model Explainability Required?

- **Trust and accountability**  
  Interpretable models increase trust, especially in high-stakes domains such as healthcare, law, and credit lending.  
  *Example:* If a model predicts cancer, healthcare providers should understand which variables influenced the prediction.

- **Bias detection**  
  Understanding a model helps identify potential biases.  
  *Example:* A healthcare model trained only on an American population may not generalize well to Asian populations.

- **Model debugging**  
  Explainability is essential during the development phase to debug errors and unexpected behavior.

- **Regulatory compliance**  
  Regulatory authorities such as the FDA and National Regulatory Authorities often require explainable models to verify safety, fairness, and real-world applicability.

---

## How to Develop Model Understanding?

There are two main approaches:

### Option 1: Glass Box Models (Inherently Interpretable)

These models are simple and transparent by design.

**Example:**  
### Linear Regression Example

**Model equation:**

    y = b₀ + b₁x

**Where:**
- **b₀** = Intercept (value of *y* when *x = 0*)
- **b₁** = Slope (change in *y* for a one-unit change in *x*)

**Interpretation:**
- If **x increases by 1 unit**, then **y increases by b₁ units**,  
  assuming all other factors remain constant.

---

### Option 2: Black Box Models (Post-hoc Explainability)

These models are complex and not directly interpretable, requiring explanation methods after training.

**Example:**  
In deep learning models, it is often unclear how input features combine to produce an output.

---

### Glass Box vs Black Box Models

| Glass Box Models | Black Box Models |
|------------------|------------------|
| Simple | Complex |
| Interpretable | Not easily interpretable |
| Lower accuracy | Higher accuracy |
| Examples: Linear Models, Decision Trees | Examples: Random Forests, Deep Learning |

---

## Ways to Interpret a Model

Model interpretation can be divided into **Global** and **Local** approaches.

### Global vs Local Interpretation

| Global Interpretation | Local Interpretation |
|----------------------|---------------------|
| Explains overall model behavior | Explains a single prediction |
| Describes how the model works in general | Describes why a specific instance got a prediction |
| Helps assess deployment suitability | Helps understand individual decisions |
| Example: Disease risk prediction across all patients | Example: W
