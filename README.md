**<h1 align="left">Objective</h1>**

The goal is to design a loan decision engine that maximizes net profit while minimizing default losses. The system evaluates loan applications based on their likelihood of default and makes approval decisions accordingly.


**<h2 align="left">Approach</h2>**



<h3 align="left">1. Data Preprocessing</h3>

**Feature Engineering**: Encoded categorical variables into numeric form using LabelEncoder.

**Handling Class Imbalance**: Used class_weight="balanced" in the logistic regression model to address the imbalance between default (1) and non-default (0) classes.

**Train-Test Split**: Divided the dataset into training (80%) and testing (20%) sets to evaluate model performance on unseen data.

<h3 align="left">2. Machine Learning Model</h3>

**Logistic Regression**:
Chosen as the baseline model for its simplicity, interpretability, and ability to provide probabilistic predictions (default probabilities).
Regularization (max_iter=1000) ensured convergence.

<h3 align="left">3. Profit-Loss Calculation</h3>

**Income**: 30 OMR for each approved loan.


**Loss**: Random value between 50 and 1000 OMR for each defaulted loan.
Decisions:
Approve loans if the predicted probability of default is below the threshold.
Reject loans otherwise.

<h3 align="left">4. Net Profit Evaluation</h3>

Net profit was calculated as

**<h3 align="center">Net Profit =(Approvals×30)−Losses from Defaults</h3>**

Simulated random losses using a uniform distribution to reflect real-world variability.


<h3 align="left">5.Threshold Optimization</h3>

Evaluated net profit for thresholds between 0 and 1.
Selected the threshold with the highest net profit as the **optimal threshold.**

<h3 align="left">6. Model Evaluation</h3>

**Primary Metric**: Net profit.

**Secondary Metrics**:
**Default Rate:** Defaults among approved loans.
**Approval Rate:** Total loans approved relative to all applications.


<h3 align="left">Machine Learning Algorithm</h3>

**1.Logistic Regression:**

- Chosen for its ability to provide interpretable results and its effectiveness with class imbalance when paired with weighting.

- The model predicts the probability of default for each loan application, enabling decision-making based on thresholds.


**2.Threshold-Driven Decisions:**

- Loan approval decisions are made solely based on predicted default probabilities and a fixed threshold.

**3.Data Integrity:**

- Assumes that the dataset is representative of real-world scenarios and free of significant biases or inaccuracies.


**4.Random Loss Simulation:**

- Loss values for defaults are randomly simulated, representing variability in real-world default scenarios.


<h3 align="left">Future Enhancements</h3>

**Advanced Models:**

- Use tree-based algorithms (e.g., Random Forest, XGBoost) for improved prediction accuracy.


**Profit-Driven Learning:**

- Implement custom loss functions that directly optimize for net profit.


**Explainability:**

- Use SHAP or LIME to understand feature importance in decision-making.
