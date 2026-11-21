# Residential Construction Cost Prediction

A time-aware and explainable machine learning study for predicting residential construction costs using information available at the beginning of a project.

## Project Overview

This project investigates whether machine learning can be used to predict the final construction cost of residential projects using only information that could reasonably be available at the beginning of construction.

The analysis focuses not only on predictive performance, but also on realistic model evaluation, prevention of data leakage, categorical feature encoding, temporal validation, model interpretability, and robustness.

## Research Question

**Can information available at the beginning of a residential construction project be used to predict its future construction cost?**

A secondary objective is to identify which project characteristics contribute most strongly to cost prediction and to examine how model performance changes when predicting projects from later time periods.

## Dataset

The project uses the **Residential Building dataset from the UCI Machine Learning Repository**, containing 372 residential construction projects.

Dataset source: **UCI Machine Learning Repository – Residential Building Data Set**

The data includes:

- project locality
- total floor area
- lot area
- construction timing
- economic and market indicators
- preliminary cost information
- actual construction costs

The prediction target is **Actual Construction Cost**.

## Methodology

Three regression approaches were evaluated:

- Linear Regression
- Random Forest
- Gradient Boosting

A mean-based baseline model was also included for comparison.

The workflow included:

- data cleaning and restructuring
- prevention of data leakage
- categorical feature encoding using one-hot encoding
- feature scaling
- time-based train/test splitting
- five-fold cross-validation
- future-period holdout evaluation
- permutation feature importance
- robustness testing
- residual analysis

## Time-Aware Validation

To simulate a realistic forecasting scenario, the models were trained on earlier construction projects and evaluated on projects from later years.

This strict future holdout design helps measure how well the models generalize when market conditions change over time.

## Key Results

Random Forest showed the strongest overall performance.

### Historical Cross-Validation

Mean five-fold cross-validation performance:

**R² ≈ 0.75**

### Strict Future Holdout

Performance on projects from later time periods:

**R² ≈ 0.48**

The decline in performance demonstrates that forecasting construction costs across changing market conditions is substantially more difficult than predicting randomly selected historical projects.

## Model Explainability

Permutation importance showed that the most influential predictors were:

1. **Unit Price at Project Start**
2. **Project Locality**

Other project characteristics, including floor area and lot area, also contributed to prediction.

## Robustness Test

The most important predictor, Unit Price at Project Start, was removed and the Random Forest model was retrained.

Future-holdout performance decreased from approximately:

**R² = 0.479 → R² = 0.343**

This confirms that the variable contains substantial predictive information while also showing that the remaining project characteristics retain independent predictive value.

## Limitations

- The dataset contains only 372 projects.
- Construction costs vary substantially across time periods.
- Model performance decreases when predicting future projects under changing market conditions.
- Some high-cost projects are underestimated.
- The dataset represents a specific geographic and economic context.
- The model should be considered a decision-support tool rather than a replacement for professional cost estimation.
## How to Run

1. Download the Residential Building dataset from the UCI Machine Learning Repository.
2. Download the ZIP file containing the dataset.
3. Open the notebook in Google Colab.
4. Upload the dataset ZIP file to the Colab runtime.
5. Run all cells from top to bottom.

The notebook performs data preparation, feature selection, preprocessing, model training, cross-validation, future-holdout evaluation, feature-importance analysis, and robustness testing.

## Reproducibility

The analysis uses a fixed random seed where applicable to make model evaluation reproducible.

The strict future holdout is based on project start year, with earlier projects used for training and later projects reserved for final evaluation.
## Conclusion

The results suggest that machine learning can provide useful support for early-stage residential construction cost forecasting.

The project also demonstrates the importance of realistic temporal validation, data leakage prevention, model interpretability, and robustness testing when applying machine learning to real-world construction problems.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- Machine Learning
- Regression Analysis
- Model Explainability
- Time-Based Validation

## Author

**Yasaman Sharif**

Background in Mathematics with professional experience in architecture and interior design, exploring the application of data science and machine learning to real-world construction problems.
