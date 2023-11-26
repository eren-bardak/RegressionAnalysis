# RegressionAnalysis

The source of the dataset is Kaggle: https://www.kaggle.com/datasets/mirichoi0218/insurance

The dataset contains a total of 1,338 rows and includes both numerical and categorical predictor variables. The columns present are: age, sex, bmi, children, smoker, region, and charges. Below is an initial overview of the data:

<img width="342" alt="Screenshot 2023-11-23 at 3 37 10 PM" src="https://github.com/eren-bardak/RegressionAnalysis/assets/131157575/3a6bbfba-ab02-41aa-b853-62f142f5e2e2">

# Summary of the Results

The primary objective was to identify the best fittinng model for predicting "charges". Initially, all potential predictors were considered, but after backward testing, "sex" was excluded for not being statistically significant. Despite the full model indicating a high adjusted R-square, considered the model complexity using AIC and BIC values, leaning more towards BIC due to its stricter penalization of model complexity. This approach led to the selection of the model 'charges ~ age + bmi + children + smoker’. However, further diagnostic tests highlighted issues like heteroscedasticity and violations of the normality assumption. Various attempts, including natural log transformations and outlier removals, were made to solve these problems, but they remained.

<img width="476" alt="Screenshot 2023-11-23 at 3 44 58 PM" src="https://github.com/eren-bardak/RegressionAnalysis/assets/138029233/71a25223-58bb-4e53-b2f1-05f8cc066b1c">

Considering the heteroscedasticity detected, the team pivoted to using robust standard errors. The HC0 model was selected given the large sample size, and though the full model's adjusted R-square was marginally higher, the decision was to conFnue with the simpler model, 'charges ~ age + bmi + children + smoker', due to its lower BIC. Notably, even aaer data transformations, the normality assumption remained a concern. Additionally, tests indicated potential non-linearity in the model, with attempts to log-transform predictors, like bmi, not delivering any substantial improvement. 

<img width="499" alt="Screenshot 2023-11-23 at 3 44 17 PM" src="https://github.com/eren-bardak/RegressionAnalysis/assets/138029233/c453ed17-9816-49ad-af11-1bb21a3465e2">

Ultimately, the chosen model was 'charges ~ age + bmi + children + smoker' with robust standard errors. Though this model still displayed potential violations of some linear regression assumptions, it was deemed the best fit given the large sample size and intent to retain all data points. Indicators like the Jarque-Bera test, lack of fit F test and QQ plots reiterated the concern about non-normality and non-linearity. However, with the VIF scores being acceptable, multicollinearity was not an issue. The presence of potential autocorrelation was acknowledged but deemed not definitive. In essence, while the model may not be perfect, it's one the best model to compromise given the available data and constraints.

<img width="464" alt="Screenshot 2023-11-23 at 3 43 46 PM" src="https://github.com/eren-bardak/RegressionAnalysis/assets/138029233/d2c70789-d7ad-4e7a-955e-1d5d8c350c3e">
