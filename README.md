# Donor-Targeting

Google Colab link - https://colab.research.google.com/drive/10b0ksOIpYzqG2gkbrtCwwm2F04BSW2-s?usp=sharing 


# Donor Targeting - Optimising Fundraising Outreach with Machine Learning

## Overview

This project aims to help a non-profit organisation **reduce outreach costs** by identifying which donors are most likely to contribute. Rather than sending donation requests to all previous donors — an expensive and inefficient approach — this project leverages **logistic regression** to prioritize a **subset of donors** with the highest probability of donating.  

The model's effectiveness is evaluated using performance metrics such as **Cumulative Gains Curve, Lift Curve, and AUC**, demonstrating significant improvements in targeting efficiency.

---

## Project Goal

The objective is to develop a predictive model that helps the non-profit **identify high-potential donors**. Instead of sending outreach messages to everyone, the organization can **focus resources on a smaller subset** of donors, improving efficiency while maintaining donation levels.  

The project follows a structured approach:
1. **Data Analysis and Preprocessing**  
2. **Feature Selection and Model Training**  
3. **Model Evaluation using Performance Metrics**  
4. **Business Impact Assessment**

---

## Methodology

### 1. Data Collection and Preparation
- **Dataset**: Past donation records from a non-profit organisation (source: DataCamp).  
- **Target Variable**:  
  - `target = 1`: The individual donated.  
  - `target = 0`: No donation was made.  
- **Features Considered**:
  - `time_since_first_gift` – Number of months since the first donation.
  - `time_since_last_gift` – Number of months since the most recent donation.
  - `number_gift` – Total number of donations made.
  - `max_gift`, `mean_gift` – Highest and average donation amounts.
  - `age`, `income_high` – Donor demographic variables.
  - Others

### 2. Exploratory Data Analysis (EDA)
- **Initial data inspection** to check for missing values and data consistency.
- **Visualisation of key features** to understand relationships with donation likelihood.

### 3. Train-Test Split and Feature Selection
- The dataset is split into **training and test sets** to assess model performance.
- **Forward Stepwise Variable Selection** is used to identify the most important features.
- **Overfitting Prevention**: Features are carefully chosen to balance predictive power and generalisability.

### 4. Model Training
- **Logistic Regression** is used as the primary model for prediction.
- The model assigns a **probability score** to each donor, indicating their likelihood of making a donation.

### 5. Model Evaluation
- **AUC (Area Under the Curve)**  
  - Evaluates the model’s ability to distinguish between donors and non-donors.
  - Limitations of AUC are discussed, emphasising why additional evaluation metrics are necessary.

- **Cumulative Gains Curve**  
  - Illustrates how efficiently the model ranks high-probability donors.
  - A sharp rise at the start indicates that the model effectively captures donors early in the ranking.

- **Lift Curve**  
  - Measures how much better the model performs compared to random selection.
  - A **higher lift** at early percentages confirms the model successfully prioritises high-value donors.

### 6. Business Impact - Cost Reduction Analysis
- The model enables the non-profit to **reduce outreach costs by 40-50%** while still reaching nearly **80% of potential donors**.
- These savings translate into **financial and resource efficiency gains**, allowing funds to be allocated more effectively.

### 7. Model Interpretation and Explainability
- Model coefficients were interpreted and analysed to understand relative feature importance.
- Odds ratio was also calculated for different predictors to quantify impact on odds of donation.
- Predictor Insight Graphs were also looked at for income.

---

## Results and Key Insights

- The **logistic regression model** successfully **ranks donors by probability of donation**, significantly improving outreach efficiency.
- **At 20% of the test data**, approximately **60% of donors** have already been identified, while **at 40% of the test data** approximately **80% of the donors** were identified.
- The **Cumulative Gains Curve and Lift Curve** confirm that the model is highly effective in prioritising donors.
- **Outreach cost savings of 40-50%** are achieved while maintaining high donor coverage.

---

## Real-World Applications

The approach used in this project can be applied to **various domains** beyond non-profits:
- **Nonprofits & NGOs**: Optimising donor outreach for fundraising campaigns.
- **Political Fundraising**: Identifying likely donors for election campaigns.
- **Marketing & Customer Retention**: Predicting high-value customers for targeted promotions.
- **Subscription-Based Businesses**: Identifying potential churners and engaging them with retention offers.

---

## Conclusion

This project demonstrates how **machine learning can optimize donor targeting**, reducing costs while maintaining high donor engagement. The results showcase how data-driven decision-making can improve fundraising efficiency for non-profits, with potential applications across other industries.

---
## Logistic Regression as the Model-of-Choice

1. Problem-Specific Choice
The goal was to identify likely donors while keeping the model interpretable for real-world decision-making. Logistic regression provides clear insights into how donor characteristics influence donation likelihood, which is crucial for a non-profit’s strategy.

4. Performance and Efficiency
Logistic regression performed well in ranking donors, achieving a 40-50% reduction in outreach costs. Given the structured nature of the dataset and the binary nature of the problem, more complex models were unlikely to provide substantial gains while increasing complexity and computational cost.

5. Avoiding Overfitting
Tree-based models like Random Forest and XGBoost can overfit on smaller datasets, especially when features are limited. Logistic regression, combined with proper feature selection, generalises well without excessive tuning.

6. Business & Deployment Considerations
For practical applications, non-profits are likely to prefer simple, explainable models that can be deployed easily without requiring advanced infrastructure or extensive model monitoring.

Of course, more advanced models like decision trees or ensemble methods could be tested, but given the results, logistic regression provided an reaonsably good balance of performance, interpretability, and ease of implementation.
