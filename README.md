# Donor Targeting - Optimising Fundraising Outreach with Machine Learning

Google Colab link - https://colab.research.google.com/drive/10b0ksOIpYzqG2gkbrtCwwm2F04BSW2-s?usp=sharing 

## Overview

This project aims to help a non-profit organisation **reduce outreach costs** by identifying which donors are most likely to contribute. Rather than sending donation requests to all previous donors — an expensive and inefficient approach — this project leverages **logistic regression** to prioritise a **subset of donors** with the highest probability of donating.  

The model's effectiveness is evaluated using performance metrics such as **Cumulative Gains Curve, Lift Curve, and AUC**, demonstrating significant improvements in targeting efficiency.

---

## Project Goal

The objective is to develop a predictive model that helps the non-profit organisation **identify high-potential donors**. Instead of sending outreach messages to everyone, the organisation can **focus resources on a smaller subset** of donors, thereby significantly reducing donor costs while retaining a majority of donations.  

The project follows a structured approach:
- **Data Analysis and Preprocessing**  
- **Feature Selection and Model Training**  
- **Model Evaluation using Performance Metrics**  
- **Business Impact Assessment**
- **Model Interpretation and Explaining Coefficients**

<img width="300" alt="Screenshot 2025-03-27 at 1 53 16 PM" src="https://github.com/user-attachments/assets/9c246654-df52-41e1-b9f3-24c9be5abf35" />


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
 
    <img width="355" alt="Screenshot 2025-03-27 at 1 53 44 PM" src="https://github.com/user-attachments/assets/2b93fdfb-a4a1-4e79-bc6d-3e972e681246" />  <img width="350" alt="Screenshot 2025-03-27 at 1 53 58 PM" src="https://github.com/user-attachments/assets/322eebfd-5fdb-44fa-9790-1414f7060f00" />



### 2. Exploratory Data Analysis (EDA)
- **Initial data inspection** to check for missing values and data consistency.
- **Visualisation of key features** to understand relationships with donation likelihood.

<img width="400" alt="Screenshot 2025-03-27 at 1 53 31 PM" src="https://github.com/user-attachments/assets/6e751e53-289a-4867-905b-dbff88c26c53" />


### 3. Train-Test Split and Feature Selection
- The dataset is split into **training and test sets** to assess model performance.
- **Forward Stepwise Variable Selection** is used to identify the most important features.
- **Overfitting Prevention**: Features are carefully chosen to balance predictive power and generalisability.

<img width="350" alt="Screenshot 2025-03-27 at 1 48 29 PM" src="https://github.com/user-attachments/assets/d6e78185-4c33-4db9-a58c-9a532ce6a722" />


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
  - The chart below indicates that when the donors are ranked in descending order of donation likelihood (as predicted by the logistic regression model), then:
    - the top 20% captures 60% of donors
    - the top 40% captures 80% of donors
    - and the top 50% captures ~90% of donors

<img width="400" alt="Screenshot 2025-03-27 at 1 48 46 PM" src="https://github.com/user-attachments/assets/b12dad3e-98d9-438e-b935-c9f878ffd5bb" />


- **Lift Curve**  
  - Measures how much better the model performs compared to random selection.
  - A **higher lift** at early percentages confirms the model successfully prioritises promising donors.

<img width="400" alt="Screenshot 2025-03-27 at 1 49 05 PM" src="https://github.com/user-attachments/assets/c25aa015-11c2-434b-837d-d2908735ec37" />


### 6. Business Impact - Cost Reduction Analysis
- The model enables the non-profit to **reduce outreach costs by 40-50%** while still reaching nearly **80% of potential donors**.
- These savings translate into **financial and resource efficiency gains**, allowing funds to be saved and allocated more effectively.

### 7. Model Interpretation and Explainability
- Model coefficients were interpreted and analysed to understand relative feature importance.
- Odds ratio was also calculated for different predictors to quantify impact on odds of donation.
- Predictor Insight Graphs were also looked at for income.

---

## Results and Key Insights

- The **logistic regression model** successfully **ranks donors by probability of donation**, significantly improving outreach efficiency.
- **At 20% of the test data**, approximately **60% of donors** have already been identified; **at 40% of the test data** approximately **80% of the donors** were identified; and **at 50% of test data**, close to **90% of donors** were captured.
- The **Cumulative Gains Curve and Lift Curve** confirm that the model is highly effective in prioritising donors.
- **Outreach cost savings of 40-50%** are achieved while maintaining high donor coverage - leading to a siginificant outreach cost reduction while still capturing a high percentage of donors.

<img width="400" alt="Screenshot 2025-03-27 at 1 49 19 PM" src="https://github.com/user-attachments/assets/187bf3b0-f3a1-4c64-83c8-3ee24872d640" />


---

## Real-World Applications

The approach used in this project can be applied to **various domains** beyond non-profits:
- **Nonprofits & NGOs**: Optimising donor outreach for fundraising campaigns.
- **Political Fundraising**: Identifying likely donors for election campaigns.
- **Marketing & Customer Retention**: Predicting high-value customers for targeted promotions.
- **Subscription-Based Businesses**: Identifying potential churners and engaging them with retention offers.

---

## Conclusion

This project demonstrates how **machine learning can help optimise donor targeting**, reducing costs while maintaining high donor engagement. The results showcase how data-driven decision-making can improve fundraising efficiency for non-profits, with potential applications across other industries.

---
## Logistic Regression as the Model of Choice

1. Problem-Specific Choice
   
The goal was to identify likely donors while keeping the model explainable for real-world decision-making. Interpreting the logistic regression coefficients provides clear insights into how donor characteristics influence donation likelihood, which can be crucial for informing a non-profit’s strategy.

2. Performance and Efficiency

Logistic regression performed well in ranking donors, achieving a 40-50% reduction in outreach costs. Given the structured nature of the dataset and the binary nature of the problem, more complex models may be unlikely to provide substantial gains while increasing complexity and computational cost.

3. Avoiding Overfitting

Tree-based models like Random Forest and XGBoost can overfit on smaller datasets, especially when features are limited. Logistic regression, combined with proper feature selection, generalises well without excessive tuning.

4. Business & Deployment Considerations

For practical applications, non-profits are likely to prefer simple, explainable models that can be deployed easily without requiring advanced infrastructure or extensive model monitoring. Additionally, the interpretability of logistic regression makes it a suitable choice to present to business stakeholders who may prefer explainable methods to black-box techniques.

Of course, more advanced models like decision trees or ensemble methods could be tested, but given the results, logistic regression provided a very good balance of performance, interpretability, and ease of implementation.
