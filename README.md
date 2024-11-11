# Working-Problems
Let's consider an insurance pricing problem where we estimate premiums based on a dataset of customer demographics and historical claim data. The goal is to determine an appropriate premium by analyzing risk factors like age, gender, vehicle type, and past claims.

**Problem Statement**
Imagine a car insurance company wants to set premiums based on the likelihood of a customer filing a claim. The dataset contains:

Age: Customer’s age in years

Gender: Male or Female

Vehicle_Type: Type of car (e.g., sedan, SUV, truck)

Claims: Number of claims filed by the customer in the past year

We will create a pricing model based on the customer's risk profile, using Poisson regression to predict the frequency of claims. The premium will be proportional to the predicted number of claims, with adjustments for specific factors (e.g., vehicle type, age).

To illustrate this, we’ll simulate a dataset and fit a Poisson regression model, a common approach for modeling count data, such as the number of claims.

**Explanation of the Code**
1. _Data Simulation:_ We create a synthetic dataset with customer demographics (age, gender, vehicle type) and simulate the number of claims using a Poisson distribution. Claims are influenced by age and vehicle type, making older customers or truck drivers slightly riskier.
2. _Poisson Regression Model:_ We fit a Poisson regression model to predict the claim frequency based on age, gender, and vehicle type.
3. _Premium Calculation:_ We calculate the premium as a function of the predicted claim frequency, scaled by a base rate (e.g., $100 per expected claim).
4. _Results:_ We summarize the average premium by vehicle type to see how pricing varies by risk factors.

**Interpretation**
Model Summary: The model uses a Poisson regression to predict the number of insurance claims based on Age, Gender, and Vehicle_Type.

Coefficients Interpretation
Each coefficient shows the effect of the predictor variable on the log of the expected number of claims.

Intercept (-1.270422, p < 2e-16)
  
   The intercept represents the log-expected claim frequency when all predictors (Age, Gender, and Vehicle_Type) are at their reference levels. Here, it represents the baseline log-claim frequency for female customers driving sedans (the reference categories for Gender and Vehicle_Type).Since it's highly significant (p < 0.001), this baseline is reliably different from zero.

Age (0.016278, p < 0.001)
    
     For each additional year in age, the log-expected number of claims increases by 0.0163.This is significant (p < 0.001), suggesting age has a positive and statistically significant effect on claim frequency, with older customers generally having a slightly higher claim frequency.

Gender   Male (0.053664, p = 0.4902)
    
     This coefficient represents the change in the log-claim frequency for male customers compared to female customers.
     The effect is positive (0.0537), but it's not statistically significant (p = 0.4902), indicating no meaningful difference in claim frequency between male and female customers.

Vehicle_Type   SUV (0.080727, p = 0.4161)
   
    This coefficient shows the log-claim frequency difference for SUV drivers compared to sedan drivers. 
    The positive coefficient (0.0807) indicates SUV drivers may have slightly higher claim frequencies than sedan drivers, but the effect is not statistically significant (p = 0.4161).

Vehicle_Type   Truck (0.184078, p = 0.0484)
    
     The coefficient for trucks indicates that truck drivers have a higher log-claim frequency than sedan drivers. 
     This is marginally significant (p = 0.0484), suggesting a small but meaningful increase in claim frequency for truck drivers compared to sedan drivers.

Model Fit Statistics
   
      Null deviance (1118.8) and Residual deviance (1074.6): The reduction in deviance indicates the model improves over the null model, though a more substantial decrease would indicate a stronger fit.
      AIC (2142.3): The Akaike Information Criterion measures the model's goodness-of-fit, with lower values generally indicating better models.

Summary
 
  Age and Vehicle_Type Truck significantly impact claim frequency, with age showing a positive relationship with claims and trucks associated with higher claim frequency.
Gender and Vehicle_Type SUV show no significant effects, indicating they do not strongly influence claim frequency in this dataset.
This model suggests that age and driving a truck are primary factors that could be used to adjust premiums, with older drivers and truck drivers potentially paying slightly higher premiums due to increased claim frequency.
