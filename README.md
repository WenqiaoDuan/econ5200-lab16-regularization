# econ5200-lab16-regularization
# Regularization: Selection, Shrinkage and Valid Intervals

## Objective

I explored how LASSO variable selection and coefficient shrinkage affect treatment effect estimates and confidence interval coverage.

## Methodology

- I simulated a treatment effect of 1.0 with 100 candidate control variables.
- I used LASSO to select controls and then applied OLS to estimate the treatment effect and confidence interval across 200 samples.
- I implemented double selection by selecting controls that predict either the outcome or the treatment.
- I compared LASSO coefficients with their true values and used post-LASSO OLS to reduce shrinkage.
- I implemented cross-validation to select the penalty parameter, fitted the scaler inside each fold, and compared my results with GridSearchCV.

## Key Findings

- The naive post-selection method achieved only 82.5% coverage, below the nominal 95%.
- Double selection improved coverage to 88.5%, keeping an average of 26.5 controls, but still fell short of the nominal coverage.
- LASSO shrank the true coefficients by an average of 4.6%. Post-LASSO OLS reduced this shrinkage.
- My cross-validation procedure matched GridSearchCV, selecting a lambda of 0.0501 with a CV MSE of 1.0173.

I learned that variable selection can affect both coefficient estimates and confidence intervals. Double selection improves coverage, but it does not completely solve the problem in this simulation.
