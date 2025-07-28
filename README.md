Customer-Churn-Prediction-Through-App-Behavior-Analysis

Objective:

A FinTech company launched a mobile app and provided a 24-hour free trial. The goal of this project is to segment users based on their behavior during the trial using clustering techniques. This helps the company:

Understand user engagement patterns.
Identify low-engagement users.
Offer personalized deals to improve subscription conversion rates. This is an unsupervised machine learning problem.
Dataset Overview:

FineTech_appData.csv - Main dataset with user behavior.
top_screens.csv - List of top app screens used to generate binary screen features.
The dataset has 50,000 records and 12 features, including:

user: Unique ID
first_open, enrolled_date: Timestamps
screen_list: Comma-separated screens visited
numscreens: Number of screens visited
enrolled: Target flag (1 if enrolled)
Derived features: difference (time to enroll), flags for top screens, screen group countsop Screens Feature Engineering:
-top_screens.csv contains a list of the most important app screens (features).

These were used to generate binary variables: if a user visited a top screen, a 1 was assigned, else 0.



Created difference feature: time to enroll (in hours).
Grouped screens into features: Savings Count, Credit Count, Loan Count, etc.


Unsupervised Learning Methods:

1. K-Means Clustering:


2. DBSCAN:
Reduced feature dimensions for visualization.
Used 2D PCA plots to visualize clusters and identify behavior-based groupings.


Results & Behavioral Insights:

Clusters revealed meaningful patterns:
One group converted quickly (enrolled within hours).
One explored many screens but didn’t enroll (curious).
One group had very low engagement (few screens, no premium use).
Final PCA scatterplot clearly highlighted low-engagement cluster for targeting.
DBSCAN showed some noise users that didn’t belong to major patterns.

Files in This Project:
UML_Project.ipynb : Jupyter notebook with full analysis and clustering.
FineTech_appData.csv : Main dataset with user behavior data.
top_screens.csv : List of screens used for feature engineering.
UML_report.pdf : Final report document.
README.txt : Overview of the project.
