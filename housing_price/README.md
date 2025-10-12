# Final Optimized Housing Price Predictor (Model 8)

## Project Summary

This repository contains the code for the **final, best-performing Linear Regression model** developed in an iterative research study on house price prediction. This model was optimized to balance variance explained ($\text{R}^2$) and real-world prediction error ($\text{MAE}$).

The model incorporates advanced feature engineering to handle location and non-linear data structures, resulting in the lowest average prediction error achieved.

## Core Techniques

The final model's superior performance is derived from two key techniques:

1.  **Target Encoding (Location Features):** Used to transform high-cardinality categorical variables (like `city` and `zip`) into a continuous numerical feature based on the mean price of that location, which proved to be the single greatest factor in improving model fit.
2.  **Polynomial Features (Degree 2):** Applied to the feature set to introduce non-linear terms and capture interaction effects between variables (e.g., `sqft_living` multiplied by `grade`), which reduced the final dollar-scale error.

## Final Performance Metrics

The model was evaluated using **5-Fold Cross-Validation** to ensure generalizability.

| Metric | Single Test Result | Mean Cross-Validation |
| :--- | :--- | :--- |
| **Mean Absolute Error (MAE)** | $\$70,844.44$ | $\mathbf{\$69,729.50}$ |
| **$\mathbf{R}^2$ Score** | $0.7100$ | $0.7435$ |

**Conclusion:** The model predicts house prices with an average error of less than **\$70,000**, representing a $\mathbf{58\%}$ reduction in $\text{MAE}$ compared to the initial unprocessed baseline.

## Repository Contents

* `polynomial_features_final_model.ipynb`: The Jupyter Notebook containing the full code for data preparation, Target Encoding, Polynomial Feature creation, training, and final evaluation of the best model.
* `housing.csv` (Note: Data file required to run the notebook, must be placed in the same directory).

## Setup and Requirements

To execute the notebook and reproduce the results, the following Python libraries are required:

```bash
pip install pandas numpy scikit-learn
