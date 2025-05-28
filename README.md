# Data-Scientist-Certification - DS601P
🍽️ Predicting High-Traffic Recipes for Homepage Optimization

📌 Project Overview

This project focuses on leveraging data science to help content teams make smarter, data-driven decisions about which recipes to feature on a website’s homepage. The key objectives are:
	•	🎯 Accurately predict which recipes will drive high user traffic.
	•	📈 Achieve a minimum precision rate of 80% in identifying high-traffic recipes.

⸻

📂 Dataset Summary

The original dataset contained 947 recipes across 8 columns:
	•	1 unique identifier: recipe_id
	•	4 numeric variables: calories, carbohydrates, sugar, protein
	•	2 categorical variables: category, servings
	•	1 target variable: high_traffic (binary classification)

After comprehensive preprocessing, the dataset was refined to 895 clean observations ready for modeling.

⸻

🧹 Data Cleaning & Preprocessing

We applied rigorous cleaning steps to ensure high data quality:
	•	✅ Removed duplicates
	•	✅ Filled or removed missing values
	•	✅ Standardized data types
	•	✅ Extracted numeric servings from mixed-format strings (e.g., “4 as a snack”)
	•	✅ Encoded categorical variables
	•	✅ Applied Yeo-Johnson transformation to correct skewed numeric distributions

📌 Why Yeo-Johnson?
It effectively normalized right-skewed features, improving model performance.

⸻

📊 Exploratory Data Analysis (EDA)

🔍 Key Insights:
	•	Minimal correlation among numeric features → less multicollinearity risk
	•	All numeric features were right-skewed → median used as the central tendency
	•	Outliers detected using boxplots
	•	Category medians for calories and nutrients varied widely

📈 Categorical Analysis:
	•	Recipes with serving size = 6 showed higher chances of being high traffic.
	•	Categories like Vegetable, Potato, and Pork consistently performed well.
	•	Beverages tended to attract the least traffic.

⸻

🤖 Modeling Approach

Model Candidates:
	•	Logistic Regression ✅ (Baseline - Best performing)
	•	Random Forest
	•	Support Vector Machine (SVM)

Preprocessing for Modeling:
	•	Yeo-Johnson transformation for numeric features
	•	One-hot encoding for the category column
	•	Train-test split for model evaluation

⸻

✅ Model Evaluation
	•	Logistic Regression achieved 80.35% precision, 82.56% recall, 81.44% f1-score, fulfilling the 80% objective.
	•	Other models (e.g., Random Forest) showed signs of overfitting or underfitting due to data size.
	•	Complex models like XGBoost and LGBM were intentionally excluded due to risk of overfitting on this dataset.

💡 From a business standpoint, false negatives (predicting low traffic for a high-traffic recipe) are costlier than false positives. Thus, model precision was prioritized over overall accuracy.

⸻

📊 Key Performance Indicator (KPI)

To align with business needs, we introduced a custom KPI:

High Traffic Conversion Rate

KPI = True Positives / False Positives

	•	A strong model should maintain a KPI > 4.0
	•	This metric was used to benchmark and compare model effectiveness

⸻

📌 Business Recommendations
	•	Consistently prioritize recipes in the “Vegetable,” “Potato,” and “Pork” categories on the homepage
	•	Avoid featuring recipes from the “Beverages” category based on historical low traffic
	•	Use the Logistic Regression model in production for daily content decisions
	•	Monitor the High Traffic Conversion Rate KPI as a proxy for ROI

⸻

🧠 Lessons Learned
	•	Simple models like Logistic Regression can outperform more complex ones when data is limited.
	•	Skewed features and data imbalance must be addressed during preprocessing.
	•	Business context should drive the choice of metrics—precision over accuracy in this case.

⸻

🚀 Next Steps
	•	Gather more labeled data, especially on low-traffic recipes
	•	Consider adding new features: prep time, number of ingredients, or user ratings
	•	Evaluate model stability over time and retrain periodically

⸻

