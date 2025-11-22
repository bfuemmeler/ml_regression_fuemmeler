# Project Summary: Regression Analysis 

This document summarizes the key decisions, assumptions, and findings for this regression analysis project. 
Complete each section clearly and professionally.
When you modify this document, rename the title to: PROJECT_SUMMARY.md. 

## Problem Definition (Front Matter)

- Project Title: Regression Analysis- Predicting Fuel Efficiency
- Author/Alias: Brenda Fuemmeler
  
- Brief description of the business or analytical problem:
  The goal of this project is to predict a vehicle’s fuel efficiency (miles per gallon) using key characteristics such as engine specifications and weight. Fuel efficiency is a critical metric in the automotive industry due to rising fuel costs, regulatory requirements, and consumer demand for economical vehicles. By understanding how engine size, horsepower, weight, and other attributes influence mpg, organizations can make more informed decisions about vehicle design, manufacturing, and environmental compliance.

- What decision or action the model is intended to support:
  The model is designed to support auto industry stakeholders in their evaluation of how design choices impact fuel consumption and identify the most influential factors to affect mgp.

- Who would use this model:
  Automotive Engineers, Production Managers, Environmental and Regulatory teams, Data Analysts, Consumers, Dealerships


## 1. Target Variable

- Target variable name: Fuel Efficiency (mpg)
- Two class values: Fuel Efficiency (mpg) is a numerical value, class value not used in this regression model
- Values are mutually exclusive and collectively exhaustive (yes/no): No
- Any unexpected or missing class values identified: No missing or invalid mpg values were found. All entries contained valid numerical values.


## 2. Feature Review

- List of available features:  Cylinders, displacement, horsepower, weight, acceleration, model year, origin
- Any restricted or disallowed features: None
- Possible sources of target leakage: None
- Example of potential leakage in this scenario: None
- How time-dependent features were handled: None
- Any features occurring after the true outcome and how they were treated:  None


## 3. Evaluation Metrics

- Primary metric chosen: R²
- Why this metric is appropriate: This metric is appropriate because it measures how much variance in mpg the model can explain.
- Secondary metrics reported: MAE and RMSE
- Brief discussion of these metrics: MAE shows average error in mpg, RMSE emphasizes larger errors and is widely used in regression performance evaluation
- Use of ROC-AUC, PR-AUC, F1, or other domain-specific metrics: N/A


## 4. Baseline Performance

- Simple mean baseline: Predicting the average mpg for all vehicles
- Rationale for this threshold: Any regression model must beat the mean predictor to be useful

## 5. Data Splitting and Validation

- Method used (train/test split or cross-validation): Train/test split (80/20 split)
- Rationale for chosen method:  Standard method for evaluating regression models and sufficient for non-temporal data.
- Is time order relevant (yes/no): No
- If yes, how time-based splitting was handled:
- Possible leakage risks across splits (duplicates, identifiers, out-of-order events): No duplicates, no future information used
- How these risks were mitigated:  Proper split was applied after cleaning and preprocessing

## 6. Real-World Impact

- Primary users or decision-makers for this model: Automotive engineers, design teams, regulatory analysts
- Action triggered by a positive prediction: Adjusting engine specifications, optimizing weight reduction, designing higher-efficiency models
- Consequences of prediction errors: 
  Poor design decisions
  Misleading estimates of regulatory compliance
  Incorrect consumer fuel-cost expectations
- Any ethical concerns or additional safeguards: Minimal, but transparency in modeling assumptions is important. No human-facing risk like in medical or credit models.

## 7. Final Notes

- Key limitations: 
  Strong multicollinearity among engine variables
  Linear regression cannot fully capture non-linear relationships
  Dataset lacks aerodynamic and drivetrain features that also affect mpg
- Future improvements:
  Use ridge/lasso for multicollinearity
  Add polynomial features or interaction terms
  Try tree-based models (Random Forest, Gradient Boosting)
- Any open questions or assumptions:
  How would additional features (e.g., transmission type, drag coefficient) improve predictions?
  Would a larger or more modern dataset change model performance?
