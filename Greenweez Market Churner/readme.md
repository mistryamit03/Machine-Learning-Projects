# 🧠 Predict Greenweez Churners – Logistic Regression Project

## 📌 Project Summary  
Developed a churn prediction model for **Greenweez**, aiming to identify customers unlikely to make a second purchase within 3 months. The solution classifies customers based on past purchasing behavior and enables targeted CRM actions to reduce churn.

---

## 🏢 Industry Domain  
**E-Commerce / Retail** (Organic & Eco Products)

---

## 🎯 Objective & Scope: Business Use Case

**Objective:**  
Predict whether a customer will **reconvert** (make a second purchase) within 3 months of their last order.

**Scope:**  
- Classification task using the `re_purchase` target (1 = repurchase, 0 = churn)  
- Help CRM teams identify high-risk customers  
- Recommend proactive retention strategies  
- Enable periodic scoring for CRM integration  

---

## 🛠 Project Implementation & Tech Stack  

**Environment & Tools:**  
- **Google Colab** (Python notebook environment)  
- **Google BigQuery** (Data source)  
- **Python Libraries:**  
  - `pandas`, `numpy` for data handling  
  - `scikit-learn` for modelling, scaling, and evaluation  
  - `matplotlib`, `seaborn` for EDA (optional extensions)

**Steps:**  
1. **Data Loading & Cleaning**  
   - Loaded 381,398 rows with 12 columns from BigQuery  
   - Verified no nulls  
   - Dropped `orders_id` and `date_date` (non-predictive)

2. **Preprocessing**  
   - Set `customers_id` as the index  
   - Features scaled using `StandardScaler`  
   - Train-test split (80-20)

3. **Modeling & Baseline**  
   - Baseline: Predict all as “re_purchase” → 48% accuracy  
   - Model: Logistic Regression → 73% accuracy  
   - Evaluation: Confusion matrix, precision, recall

4. **Probabilistic Output**  
   - Generated churn probabilities using `predict_proba()`  
   - Filtered customers with 20–50% re-purchase chance for CRM targeting

---

## 🔍 Key Findings  

- Logistic Regression achieved:  
  - **Accuracy**: 73.2%  
  - **Precision**: 75.9%  
  - **Recall**: 63.8%  
  - **Churner Recall (True Negatives)**: 81.8%

- Churn likelihood segments:  
  - `< 20%` → Very likely to churn  
  - `20–50%` → Opportunity for reactivation  
  - `> 50%` → Likely to repurchase

- 44K customers fall in the 20–50% range — ideal for focused retention efforts

---

## 🚀 Final Deliverables  

- ✅ Logistic Regression Churn Prediction Model  
- 📊 Probability Scores (Re-purchase vs Churn) per Customer  
- 🎯 List of at-risk customers for CRM team  
- 🔁 Recommendation to integrate with CRM using ELT pipelines for periodic scoring and re-engagement campaigns

---

## 💡 Business Recommendation

Set up a weekly or monthly scoring pipeline:
- Feed churn probabilities to CRM
- Target medium-risk customers (20–50%) with discounts, reminders, or offers
- Monitor uplift in conversion rates through A/B testing and feedback loops

---

_This project was completed as part of a Data Analytics Bootcamp to simulate real-world churn prediction in e-commerce._

