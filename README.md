# Parameter Optimization

This project applies a **Support Vector Machine (SVM)** classifier to a letter recognition dataset. The aim is to identify the best value of the regularization parameter **C** that gives the highest test accuracy across multiple train-test splits.

## Overview

- The dataset has a target variable `letter`, which is encoded numerically using `LabelEncoder`.
- The model used is `SVC` with an **RBF kernel**.
- The experiment is repeated across **10 different train-test splits**.
- For each split, **100 values of C (from 0.1 to 10)** are evaluated to find the optimal configuration.

## Methodology

### 🔹 Data Preprocessing

- Target label `letter` is converted to numeric using `LabelEncoder`.
- Features and labels are extracted from the DataFrame.
- The dataset is split into training and testing sets using `train_test_split` with `test_size=0.3`.

### 🔹 Hyperparameter Tuning

For each of 10 `random_state` values (0 to 9):
- Iterate through 100 values of **C** linearly spaced between 0.1 and 10.
- For each value:
  - Train an `SVC` model with RBF kernel.
  - Record test accuracy.
- Track the best-performing `C` and its corresponding accuracy for each split.

### 📈 Convergence Graph

- A plot is generated showing **accuracy vs. C** for the split that achieved the highest test accuracy.

## 📊 Results Snapshot

| Split | Best Accuracy | Best Parameters |
|-------|----------------|------------------|
| 0     | 0.9673         | C=10.0           |
| 1     | 0.9623         | C=9.9            |
| 2     | 0.9632         | C=10.0           |
| 3     | 0.9617         | C=10.0           |
| 4     | 0.9592         | C=10.0           |
| 5     | 0.9610         | C=9.7            |
| 6     | 0.9582         | C=10.0           |
| 7     | 0.9643         | C=8.5            |
| 8     | 0.9652         | C=9.7            |
| 9     | 0.9635         | C=9.9            |

## 🛠 Technologies Used

- Python
- `scikit-learn`
- `pandas`, `numpy`
- `matplotlib`, `seaborn`

## 🚀 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/Avishi2511/parameter-optimization.git
   cd parameter-optimization
