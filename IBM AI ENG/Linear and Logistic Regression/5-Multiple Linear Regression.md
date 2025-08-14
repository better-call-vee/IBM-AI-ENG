> [!info] Simple vs. Multiple Linear Regression
> **Simple Linear Regression:** Uses **one** independent variable to predict a dependent variable.  
> Example: Engine size → CO₂ emissions (engine size = independent variable).  
> 
> **Multiple Linear Regression:** Uses **two or more** independent variables.  
> Formula:  
> ```
> ŷ = θ₀ + θ₁x₁ + θ₂x₂ + ...
> ```
> Example:  
> - `x₁` = engine size  
> - `x₂` = cylinder size  
> 
> **Interpreting Coefficients:** The coefficient for one variable (e.g., `θ₁`) tells you its **unique effect** while **holding all other variables constant**.  
> Analogy: If studying basketball scoring with `height` and `hours_of_practice_per_week`, to measure `height`'s effect, compare players with **same practice hours**.

---

> [!warning] Pitfall — Multicollinearity
> **Definition:** When independent variables are correlated with each other, making them not truly independent.  
> 
> Example: Predicting salary using both `years_of_experience` and `age`.  
> - Problem: Holding `age` constant while increasing `years_of_experience` often describes an unrealistic situation.  
> - Result: Model struggles to assign credit to each variable; coefficients become **unstable** and **hard to interpret**.  
> 
> **Solution:** Remove one of the correlated variables.  
> - If `age` and `years_of_experience` tell the same story, keep the better predictor and drop the other.

---

> [!summary] Key Takeaways
> - **Multiple vs. Simple:** Multiple regression uses two or more independent variables.  
> - **Interpreting θ:** Shows the unique effect of one variable while holding others constant.  
> - **Multicollinearity:** Highly correlated predictors cause unstable coefficients — remove redundancy.

## PRACTICE

> [!warning] Irrelevant Features and Overfitting
> **Scenario:**  
> Predicting a student's final exam score using:  
> - Useful features: `hours_studied`, `previous_test_scores`  
> - Proposed extra feature: `shoe_size` (*irrelevant*)  
> 
> **Why this is harmful:**  
> - In training data, the model might spot a **coincidental pattern** (e.g., students with larger feet happen to score higher).  
> - The model learns this **fluke** as if it were a real rule.  
> - On new students, this relationship won’t hold — predictions become **less accurate**.  
> - This is **overfitting**: the model has learned **noise**, not the true signal.

---

> [!tip] Feature Selection Principle
> - **More data** ≠ **better model** if the data is irrelevant.  
> - Only include **high-quality, relevant features** with a real, logical relationship to the target.  
> - Be **deliberate and thoughtful** — avoid dumping every possible variable into the model.  
> - Use domain knowledge and statistical checks to decide what to keep.





## 2)

> [!question] Can You Use Text Directly in a Regression Equation?
> **Equation:** ŷ = θ₀ + θ₁x₁ + θ₂x₂  
> **Problem:** You can’t plug words like `'Gasoline'` into this equation — regression models work only with **numbers**.  
> **Reason:** Text values have no inherent mathematical meaning for the model to process.

---

> [!tip] Encoding Categorical Variables 
> - **Idea:** Convert each category into its own **Boolean (0/1) column**.  
> - Example for `FUEL_TYPE`:
> ```
> | EngineSize | Fuel_Type | Is_Gasoline | Is_Diesel | Is_Electric |
> |------------|-----------|-------------|-----------|-------------|
> | 2.0        | Gasoline  | 1           | 0         | 0           |
> | 3.0        | Diesel    | 0           | 1         | 0           |
> | 0.0        | Electric  | 0           | 0         | 1           |
> ```
> - This avoids creating a **false order** between categories and keeps the data numeric for the model.
