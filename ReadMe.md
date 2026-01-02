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


Local Interpretation

We will discuss the following methods of local interpretation:

    LIME (Local Interpretable Model-agnostic Explanations)
    SHAP (SHapley Additive exPlanations)


LIME (Local Interpretable Model-Agnostic Explanations)

LIME provides a local interpretation by modifying feature values of a single data sample and observing its impact on the output. It builds a surrogate model from the input (sample generation) and model predictions. An interpretable model can be used as a surrogate model. Because LIME is a model agnostic technique, therefore it can be used on any model.

Steps involved in LIME:

    It creates a permutation (fake) of the given data.
    It calculates the distance between permutations and the original observations. Also, we can specify the distance measured.
    Then, it makes predictions on the new data using some black-box models.
    It picks “m” features that describe the complex model. It is an outcome from the permuted data in the best possible way through the maximum likelihood approach. Here, we can decide the number of features i.e. the value of “m” we want to use.
    It picks the “m” features and fits a simple model to the permuted data with the similarity score as weights.
    The weights from the simple model are used to provide explanations for the complex model’s local behavior.

SHAP (SHapley Additive exPlanations)

SHAP shows the impact of each feature by interpreting the impact of a certain value compared to a baseline value. The baseline used for prediction is the average of all the predictions. SHAP values allow us to determine any prediction as a sum of the effects of each feature value.

The only disadvantage with SHAP is that the computing time is high. The Shapley values can be combined together and used to perform global interpretations also.
Global Interpretation

following methods of global interpretation:

    PDP (Partial Dependency Plot)
    ICE(Individual Conditional Expectation)
