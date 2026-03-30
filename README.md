📊 Street Vendors Analysis – Mumbai
📌 Project Overview

This project presents a data-driven socio-economic analysis of street vendors in Mumbai, focusing on:

Income determinants
Migration patterns
Customer footfall dynamics

Unlike traditional qualitative studies, this project uses statistical modeling and machine learning to generate actionable insights.

🎯 Objectives
Analyze the impact of socio-economic factors on vendor income
Identify migration patterns using clustering techniques
Model daily customer count using count-based regression

🧾 Dataset
Primary survey data of 400 street vendors
Stratified sampling across:
Western Line
Central Line
Harbour Line
Trans Harbour Line
Features:
Demographics (Age, Gender, Education)
Business attributes (Product type, Working hours)
Migration details
Income & customer data

⚙️ Methodology
🔹 1. Exploratory Data Analysis (EDA)
Data cleaning & preprocessing
Distribution analysis
Visualization of trends
🔹 2. Multiple Linear Regression
Target: Monthly Income
Key finding:
Western region ↑ income
Non-food vendors ↓ income significantly
🔹 3. K-Modes Clustering

Identified 3 vendor segments:

Economic Migrants → Low income, high dependency
Stable Vendors → Non-migrants, steady income
Opportunity Seekers → Migrants seeking better markets
🔹 4. Poisson Regression
Target: Daily customer count
Key finding:
Full-day vendors attract more customers
Shorter working hours significantly reduce footfall

📈 Key Insights

✔ Region and product type are strongest predictors of income
✔ Non-food vendors earn significantly less
✔ Migration is structured, not random
✔ Working hours directly impact customer volume

🛠️ Tech Stack
R → Regression & statistical modeling
Python → Clustering & preprocessing
Excel → Data handling
Matplotlib & Seaborn → Visualization
📊 Model Performance
Adjusted R² ≈ 0.43 (Moderate fit)
Statistically significant model (p < 0.05)
Assumptions validated using:
Box-Cox Transformation
Normality tests
Homoscedasticity tests

💡 Business & Policy Recommendations
Support non-food vendors with marketing & training
Improve infrastructure in low-income regions
Promote full-day vending for higher customer engagement
Enable targeted schemes (e.g., urban livelihood programs)

📌 Author

Ekta Shirsulla
Aspiring Data Analyst / Data Scientist
     
