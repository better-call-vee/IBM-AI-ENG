
**Ordinary Least Squares (OLS)**
**Mean Squared Errors (MSE)**

- We use scatter plots in Regression Model.
- We get lines by adding those. We have to find the line with the least error.
- We get errors due to outliers.
- Suppose a data from +10 to -10, we get huge outliers. We do is 10x10 , -10x-10. That's OLS
- Our goal is to find that one line with the least MSE
- The "best-fit line" is the one that is closest to all the data points.


> [!info] Simple Linear Regression Example
> You've built a **simple linear regression** model to predict an employee's **monthly sales** (`y`) based on the **number of training hours** they received (`x`).  
> 
> **Model coefficients:**  
> - **Intercept** (*θ₀*) = **5,000**  
> - **Slope** (*θ₁*) = **250**  
> 
> **Formula:**  
> ```
> Predicted Sales (ŷ) = Intercept (θ₀) + Slope / Coefficient (θ₁) × Training Hours (x₁)
> ```


> [!info] Understanding Slope, Intercept, and Extrapolation
> - A **_slope_** tells us how much `y` changes for every **one-unit increase** in `x`.  
> - The **intercept** is the predicted value of `y` when `x` is zero.  
>     - Example: **5,000** sales when training hours = `0` — which sounds a bit like *clownery*. 🤡  
> - When a model is asked to predict for a range it **has not been trained on** (e.g., 0–4 hours), it extends its trend line into unknown territory.  
>     - This dangerous guess is called **extrapolation**.  
>     - Example: training hours = `0` → predicted sales = **5,000** — clearly unrealistic.


> [!example] Outliers and the Seesaw Effect
> **Dataset:**  
> - *Original Data:* `(Size, Price)` → (1000, 200k), (1200, 250k), (1500, 300k), (1800, 350k), (2000, 400k)  
> - *New Outlier:* `(800, 1.5M)` — a tiny but incredibly expensive historical landmark mansion.  
> 
> **Effect on Best-Fit Line (no math needed):**  
> - This high-priced, small-sized house acts like a **helium balloon** tied to the **left side** of the graph.  
> - The regression line will **tilt upward on the left** (smaller sizes) and **downward on the right** (larger sizes).  
> - In other words — slope **decreases** because the extreme left is being pulled up.  
> 
> **Analogy:** It's like a seesaw where the left end suddenly floats up in the air while the right side sinks down.
![[Effect of an outlier on LR.png]]



> [!info] Residuals in Regression
> **Definition:** A residual is the prediction error for a single data point — the difference between the **actual value** (`y`) and the **predicted value** (`ŷ`). It’s what’s *left over* after making a prediction.  
> 
> **Formula:**  
> ```
> Residual (e) = Actual (y) − Predicted (ŷ)
> ```
> 
> **Examples:**  
> - **Positive Residual (Underestimate):**  
>   - 10 hrs → Actual: $8,000, Predicted: $7,500 → **+500** → Point above the line.  
> - **Negative Residual (Overestimate):**  
>   - 20 hrs → Actual: $9,000, Predicted: $10,000 → **−1,000** → Point below the line.  
> - **Zero Residual (Perfect):**  
>   - 8 hrs → Actual = Predicted = $7,000 → On the line.

That's why it's Residual. We get the Part after subtracting the main part (predicted calculated number)




