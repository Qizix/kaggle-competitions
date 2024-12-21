# CIBMTR - Equity in Post-HCT Survival Predictions

## Overview
This competition aims to predict equitable survival outcomes for hematopoietic cell transplantation (HCT) across different race groups. The target metric is the **Stratified Concordance Index (C-index)**, which evaluates the model's ability to rank survival times correctly while ensuring fairness across race groups.

## Approach
The solution was developed using an ensemble of:
- **XGBoost**
- **CatBoost**
- **LightGBM**
- **Neural Networks**

### Key Steps:
1. **Data Preprocessing:**
   - Handled missing values and ensured consistency in features.
   - Encoded categorical variables using appropriate techniques.
   - Normalized numerical variables for better performance.

2. **Feature Engineering:**
   - Derived additional meaningful features.
   - Used domain knowledge and exploratory data analysis to identify important predictors.

3. **Model Training:**
   - Trained individual models (XGBoost, CatBoost, LightGBM, Neural Networks) with hyperparameter tuning using randomized search.
   - Used stratified k-fold cross-validation to validate model performance.

4. **Ensemble Learning:**
   - Combined predictions from all models using a weighted average strategy to improve robustness and accuracy.

5. **Evaluation:**
   - Assessed model performance using the Stratified Concordance Index (C-index) for fairness and reliability across race groups.

## Key Features
- **Targets:**
  - `efs`: Event-free survival (categorical: 'Event' or 'Censoring').
  - `efs_time`: Time to event-free survival in months (numerical).
- **Race Group:** An essential feature for ensuring fairness.

## Tools and Libraries
- **Python**
  - Libraries: `pandas`, `numpy`, `scikit-learn`, `xgboost`, `catboost`, `lightgbm`, `tensorflow/keras`
- **Lifelines**
  - Used for survival analysis and computation of the C-index.

## Challenges
- Balancing predictions across race groups to ensure fairness.
- Optimizing hyperparameters for multiple models while avoiding overfitting.
- Combining diverse models into an effective ensemble.

## Results
- **Leaderboard Score:** 

## Future Work
- Further improve fairness using advanced debiasing techniques.
- Explore alternative ensemble strategies, such as stacking or blending.
- Investigate other survival analysis methods for potential gains in performance.

## Acknowledgments
Thanks to the competition organizers and the community for providing the opportunity to work on this impactful problem.
