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

### Convergence Graph

- A plot is generated showing **accuracy vs. C** for the split that achieved the highest test accuracy.

## Results Table

![image](https://github.com/user-attachments/assets/39298e07-5b1b-48d4-b24c-66183a6a3f70)


## Result Graph

![image](https://github.com/user-attachments/assets/8df3c7e5-1a2b-460c-8654-d69928f9db0b)


## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/Avishi2511/parameter-optimization.git
   cd parameter-optimization
