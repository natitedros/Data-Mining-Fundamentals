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
- [`K-Means`](unsupervised/K-Means.ipynb)
  - K-Means clustering implementation and evaluation 


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

## K-Means Clustering

This assignment implements **K-Means clustering** to segment and recolor an image based on RGB pixel similarity.

### Objectives
1. Load and preprocess the image by normalizing RGB values to \([0,1]\).
2. Implement K-Means with Euclidean distance.
3. Run the algorithm for `k = 2, 3, 6, 10` using the provided initial centroids.
4. Iterate until convergence or a maximum of 50 iterations.
5. Compute and report the final **Sum of Squared Errors (SSE)** for each k.
6. Recolor each cluster using the specified 10-color scheme.

### Method Overview
- Converted the image from shape `(244, 198, 3)` into a 2D array of pixels.
- Normalized all RGB channels by dividing by 255.
- Assigned pixels to the nearest centroid using Euclidean distance.
- Updated centroids as the mean RGB values of their assigned pixels.
- Stopped early when centroid movement was below a small threshold.
- Recolored each cluster using the assignment:  
  - Cluster 1 → SpringGreen  
  - Cluster 2 → DeepSkyBlue  
  - Cluster 3 → Yellow  
  - Cluster 4 → Red  
  - Cluster 5 → Black  
  - Cluster 6 → DarkGray  
  - Cluster 7 → DarkOrange  
  - Cluster 8 → Purple  
  - Cluster 9 → Pink  
  - Cluster 10 → White  

### Key Results
- Final SSE values were obtained for each k (`k = 2, 3, 6, 10`).
- Recolored output images were generated for each k using the provided palette.
- Larger k reduced SSE and produced finer segmentation of image regions.
- Most runs converged before reaching 50 iterations.

### Deliverables
- Program code implementing K-Means with the given initial centroids.
- Final SSE values for each k.
- Recolored images for `k = 2, 3, 6, 10`.

---
## Usage

Clone the repository and run the notebook files:

```bash
git clone <repository-url>
cd Data-Mining-Fundamentals
jupyter notebook

