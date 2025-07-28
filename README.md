# Customer-Churn-Prediction-through-App-Behaviour-Analysis



## 🎯 Objective

This project focuses on **user segmentation** using **unsupervised machine learning** techniques based on user behavior during a **24-hour free trial** of a FinTech mobile application. The goal is to:

* Understand diverse **user engagement patterns**
* Identify **low-engagement users**
* Provide **personalized offers** to improve **subscription conversion rates**

---

+-------------------------+------------------------------------------------------------------------+
| File Name              | Description                                                            |
+-------------------------+------------------------------------------------------------------------+
| UML_Project.ipynb      | Jupyter notebook with full analysis, preprocessing, and clustering     |
| FineTech_appData.csv   | Main dataset with behavioral data of 50,000 app users                  |
| top_screens.csv        | List of most frequently visited app screens for feature engineering    |
| UML_report.pdf         | Final report with methodology, visualizations, and behavioral insights |
| README.txt             | Text-based summary and project overview                                |
+-------------------------+------------------------------------------------------------------------+


---

## 🧾 Dataset Overview

### Main Features (`FineTech_appData.csv`):

+------------------+------------------------------------------------------------+
| Feature          | Description                                                |
+------------------+------------------------------------------------------------+
| user             | Unique user ID                                             |
| first_open       | Timestamp when user first opened the app                   |
| enrolled_date    | Timestamp when user enrolled (if at all)                   |
| screen_list      | Comma-separated list of visited app screens                |
| numscreens       | Total number of screens visited                            |
| enrolled         | Binary flag: 1 if enrolled, 0 otherwise                    |
+------------------+------------------------------------------------------------+


### Top Screens (`top_screens.csv`):

Contains the most important screens for feature engineering (e.g., Loan2, Saving4, Credit3).

---

## 🛠️ Preprocessing & Feature Engineering

* **Datetime Conversion**: `first_open` and `enrolled_date` converted to datetime format.
* **Time Difference Feature**: Created `difference` = time to enroll (in hours).

  * Users with `difference > 48` hours marked as not enrolled.
* **Top Screens Mapping**:

  * Parsed `screen_list` and created binary flags for each screen in `top_screens.csv`.
* **Grouped Features**:

  * Grouped related screens into categories like:

    * **Loan Screens**: Loan2, Loan3, Loan4, Loan5
    * **Saving Screens**: Saving1, Saving2Amount, Saving4, Saving5
    * **Credit Screens**: Credit1, Credit2, Credit3Container, etc.
    * **Credit Card Screens**: CC1, CC1Category, CC3
* **Feature Reduction**:

  * Removed original `screen_list` and other redundant columns.
* **Standardization**:

  * Applied `StandardScaler` to normalize numerical features.

---

## 🤖 Unsupervised Learning Methods

1. K-Means Clustering
2. DBSCAN (Density-Based Spatial Clustering)
3. PCA (Principal Component Analysis)


---

+----------------------+--------------------------------------------------------------------------------+
| Cluster Type         | Description                                                                    |
+----------------------+--------------------------------------------------------------------------------+
| 🟢 Quick Converters  | Enrolled within a few hours, indicating strong interest                        |
| 🟡 Curious Users     | Explored many features but did not enroll — opportunity for onboarding tweaks  |
| 🔴 Low Engagement    | Visited few screens, didn’t enroll — target for special offers                 |
| 🔵 High Engagement   | Deep feature exploration — ideal users to retain and study further             |
+----------------------+--------------------------------------------------------------------------------+




---

##  Summary

By leveraging **unsupervised learning**, this project successfully segmented 50,000 users into actionable groups. Through clustering, PCA visualization, and behavioral insights, we created a data-driven foundation for **improving user engagement and conversion rates**.

---

## 📚 Requirements

* Python 3.x
* Pandas, NumPy
* Scikit-learn
* Seaborn, Matplotlib
* Jupyter Notebook

---


