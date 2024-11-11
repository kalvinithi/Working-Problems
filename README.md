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
