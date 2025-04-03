# 📊 Alphabet Soup Charity — Neural Network Model

## 🔍 Overview

This project was developed to support **Alphabet Soup**, a nonprofit foundation, in making data-driven decisions when selecting applicants for funding. Using a deep learning neural network, we aimed to build a binary classifier that predicts whether an applicant will be successful if funded.

By analyzing historical data from over **34,000 funded organizations**, the model seeks to identify patterns and features associated with successful funding outcomes.

---

## 🧠 Objective

Create a binary classification model using TensorFlow/Keras that can:

- Predict the success (`IS_SUCCESSFUL`) of an application
- Assist Alphabet Soup in evaluating future applicants based on historical success patterns

---

## 🗂 Dataset Details

The dataset includes categorical and numerical data describing organizations, their application types, funding requests, and success outcomes.

### 🎯 Target Variable: What variable(s) are the target(s) for your model?
- `IS_SUCCESSFUL`: Binary flag indicating if the funding resulted in a successful outcome (1 = Yes, 0 = No)

### 🔍 Features Used: What variable(s) are the features for your model?
- `APPLICATION_TYPE`
- `AFFILIATION`
- `CLASSIFICATION`
- `USE_CASE`
- `ORGANIZATION`
- `STATUS`
- `INCOME_AMT`
- `SPECIAL_CONSIDERATIONS`
- `ASK_AMT`

### 🧹 Features Removed: What variable(s) should be removed from the input data because they are neither targets nor features?
- `EIN`, `NAME`: These are unique identifiers and irrelevant for prediction, thus dropped early.

---

## 🧪 Data Preprocessing

- One-hot encoding was used for all categorical variables.
- Numerical features were normalized using `StandardScaler`.
- Dataset was split into training and test sets (approx. 75/25 split).

---

## 🏗 Model Architecture : How many neurons, layers, and activation functions did you select for your neural network model, and why?

The deep learning model was built using **Keras Sequential API**:

| Layer         | Neurons | Activation |
|---------------|---------|------------|
| Hidden Layer 1| 80      | ReLU       |
| Hidden Layer 2| 30      | ReLU       |
| Output Layer  | 1       | Sigmoid    |

### ⚙️ Compilation
- **Loss Function**: `binary_crossentropy`
- **Optimizer**: `adam`
- **Metrics**: `accuracy`

ReLU is a standard choice ... Sigmoid is ideal for binary outcomes.
---

## 📊 Model Performance : Were you able to achieve the target model performance?

- **Final Accuracy**: ~72.8%
- **Target Accuracy**: 75%

Although the model performed reasonably well, it fell slightly short of the performance goal.

---

## 🔧 Optimization Attempts : What steps did you take in your attempts to increase model performance?

Several experiments were conducted to enhance performance:

- Varying number of neurons and layers
- Adding dropout layers (to reduce overfitting)
- Reducing high-cardinality feature values (e.g., binning rare `APPLICATION_TYPE` and `CLASSIFICATION`)
- Feature normalization using `StandardScaler`
- Hyperparameter tuning (e.g., learning rate, batch size)

---
## 💡 Recommendations & Next Steps

While the current deep learning model provided promising results, alternative models could potentially outperform it:

### ✅ Try Other Algorithms:
- **XGBoost or Random Forests**: Better suited for categorical data and high-dimensional features.
- **Logistic Regression (as baseline)**: Simpler model to compare performance.
- **AutoML Tools**: Automate feature selection and model optimization.

### ✅ Enhanced Feature Engineering:
- Log-transform skewed features (e.g., `ASK_AMT`)
- Group rare categories
- Encode ordinal relationships where applicable

---
## 🚀 Conclusion
This project demonstrates how neural networks can be applied to nonprofit funding strategies. While the model was not perfect, it lays the groundwork for more advanced predictive tools that can support mission-driven decision-making.

## 📁 Project Files

```bash
.
├── AlphabetSoupCharity_Optimization.ipynb   # Main analysis notebook
├── README.md                                 # This project readme
└── charity_data.csv                          # Dataset (hosted externally if not included)
