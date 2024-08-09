# CAR-PRICE-PREDICTION
This analysis involves a step-by-step process of building a multiple linear regression model by selecting features through Recursive Feature Elimination (RFE) and checking for multicollinearity using the Variance Inflation Factor (VIF). Here’s a summary of what was done:

<h3>Step 1: Data Normalization</h3>
The numerical variables in the dataset were scaled using MinMaxScaler, which normalizes the values between 0 and 1.
<h3>Step 2: Feature Selection Using RFE</h3>
RFE was used to select the top 10 features based on their contribution to predicting the target variable, price. The selected features were:
curbweight, boreratio, horsepower, carwidth, hatchback, sedan, wagon, dohcv, twelve, Highend
<h3>Step 3: Initial Model Building</h3>
An OLS regression model was built using the selected features.
The model showed high R-squared values (0.938 initially), indicating a good fit. However, one of the variables (twelve) had a high p-value and was removed to improve model significance.
<h3>Step 4: Checking and Reducing Multicollinearity</h3>
<ul>
  <li>VIF values were calculated to detect multicollinearity among the predictors. High VIF values indicate high multicollinearity.</li>
  <li>Variables with high VIF (curbweight, carwidth, boreratio) were considered for removal.</li>
  <li>The variable curbweight was removed first, reducing multicollinearity but slightly lowering the R-squared value to 0.928.</li></ul>
<h3>Step 5: Further Model Refinement</h3>
The model was further refined by removing sedan, another variable with a high VIF, leading to an R-squared value of 0.914.<br>
The final model included the following variables:<br>
<ul>
  <li>boreratio</li>
  <li>horsepower</li>
  <li>carwidth</li>
  <li>hatchback</li>
  <li>wagon</li>
  <li>dohcv</li>
  <li>Highend</li>
</ul>
  <h3>Key Observations:</h3>
<p>The variables horsepower, carwidth, and Highend had the most significant impact on predicting car prices, with low p-values and relatively low VIF values.
The overall model fits well with an R-squared value around 0.914 after refining, indicating that approximately 91.4% of the variance in car prices can be explained by these predictors.</p>
The model suggests that higher horsepower, car width, and the Highend variable (possibly indicating luxury status) are positively associated with car prices, while features like hatchback and dohcv had a negative association.
