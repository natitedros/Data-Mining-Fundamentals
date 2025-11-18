# Data Mining Course Assignments

This repository contains my implementations and solutions for the Data Mining course assignments. The projects are organized by algorithm and technique, and each implementation includes code, results, and visualizations generated in Jupyter notebooks. The README is structured to allow easy extension for future assignments.

---

## Contents

- [`Linear Regression`](supervised/Linear-regression.ipynb)
  - L2 Regularized Linear Regression
  - Cross-Validation for λ selection
- [`Linear Regression with Cross Validation`](supervised/Linear-regression-with-cross-validation.ipynb)
  - Applying 10-fold cross-validation to select λ
- [`K-Nearest Neighbors (KNN)`](supervised/KNN.ipynb)
  - KNN classifier implementation and evaluation

---

## Linear Regression

This assignment focuses on **L2-regularized linear regression** (ridge regression) and explores the effect of the regularization parameter, λ, on model performance.

### Objectives
1. Implement L2-regularized linear regression for λ ranging from 0 to 150.
2. Plot **training** and **test** MSE as a function of λ for six datasets.
3. Identify the λ value giving the lowest test MSE for each dataset.
4. Analyze the effect of λ = 0 on datasets 100-100, 50(1000)-100, and 100(1000)-100.

### Key Results
- For each dataset, the λ value minimizing test MSE was identified.
- Visualizations include MSE vs. λ plots.
- Explanation of why no regularization (λ = 0) leads to abnormally large MSEs for certain datasets due to overfitting.

---

## Linear Regression with Cross Validation

In practice, the best λ cannot be determined directly from test data. This notebook implements **10-fold cross-validation (CV)** to select λ using only the training set.

### Objectives
1. Implement 10-fold CV for selecting λ.
2. Compare the best λ and corresponding test MSE obtained via CV with the results from the previous linear regression experiment.
3. Discuss potential drawbacks of CV.

### Key Results
- Optimal λ values selected using CV for each dataset.
- Comparison of CV-based λ values and test MSEs to direct evaluation results.
- Discussion of CV drawbacks, such as computational cost and variance in small datasets.

---

## K-Nearest Neighbors (KNN)

This assignment involves implementing a **KNN classifier** to classify emails as spam or not spam.

### Objectives
1. Implement KNN with Euclidean distance.
2. Evaluate classification accuracy for different values of `k` both **with** and **without** feature normalization.
3. Generate predicted labels for the first 50 test instances under different k values.
4. Compare KNN performance with and without normalization.
5. Describe a method for selecting the optimal k.

### Key Results
- Test accuracies were reported for `k = 1, 5, 11, 21, 41, 61, 81, 101, 201, 401`.
- Observed that **z-score normalization** improves KNN performance significantly.
- Generated predictions for the first 50 test instances.
- Analysis of performance differences with/without normalization.
- Suggested strategies for choosing the optimal k (e.g., cross-validation on training set).

---

## Usage

Clone the repository and run the notebook files:

```bash
git clone <repository-url>
cd Data-Mining-Fundamentals
jupyter notebook

