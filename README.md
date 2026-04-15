# Gurgaon Real Estate Price Prediction & Recommendation System

#### An end-to-end data science project that combines advanced feature engineering, machine learning, and recommender systems to solve real-world real estate problems — predicting property prices and recommending similar societies.
### 🔗 Related Projects

This pipeline provides the backbone for the Gurgaon Real Estate Web App, which serves as the interactive frontend for these models.
Check it out here : https://gurgaonrealestateapp.streamlit.app/

### 🚀 Project Overview

This project builds a complete pipeline starting from raw, unstructured real estate data to:

- Accurate price prediction model (R² ≈ 0.90)
- Intelligent society recommendation system
- Production-ready ML pipeline
---
### 📂 Dataset & Preprocessing
- Merged `flats + houses` datasets into a unified schema
- Cleaned highly unstructured columns using regex-based extraction
- Standardized price values → all converted to crore
- Engineered sector feature from society names (including manual enrichment)
  
### 🧱 Area Engineering
Split inconsistent area column into:
`built_up_area`, `super_builtup_area`, `carpet_area`
Converted all units → `sq.ft`
Imputed missing values using cross-feature relationships
Finalized `built_up_area` as primary feature
🧠 Advanced Feature Engineering
🪑 Furnishing Classification
Extracted 19 features from unstructured text
Applied StandardScaler + KMeans (k=3 via Elbow Method)
Reduced into:
Unfurnished / Semi-Furnished / Furnished
🏢 Luxury Score
Extracted ~130 facility features
Applied KMeans clustering (k=3)
Created luxury_score (low / mid / high)
📊 Exploratory Data Analysis (EDA)
Univariate Analysis: distribution, skewness, outliers
Applied log1p transformation on price (right-skew correction)
Multivariate Analysis:
Correlation heatmaps, scatter plots, boxplots
Identified key drivers: area, sector, BHK, luxury_score
Automated analysis using ydata-profiling
🧹 Outlier Detection & Cleaning
Used IQR, quantiles, and boxplots across all features
Removed data errors, retained genuine high-value properties
Validated using:
price per sq.ft consistency
area vs price relationships (lmplot)
Preserved real-world distribution integrity
🔧 Missing Value Imputation
Used domain-driven imputation logic for area features
Applied median/mode imputation for other columns
Ensured:
No logical inconsistencies
No distribution distortion
No data leakage
🎯 Feature Selection
Removed non-inferable features (e.g., society, price_per_sqft)
Applied multiple techniques:
Correlation, Random Forest, Gradient Boosting
Permutation Importance, RFE, Lasso
Aggregated & normalized importance scores

Top Features:

built_up_area, sector, bedroom

Performance Improvement:

Before selection → R²: 81.7%
After selection → R²: 82.5%
🤖 Model Building
🔄 Preprocessing Pipeline
Numerical → StandardScaler
Categorical → OneHotEncoder / OrdinalEncoder
Location → Target Encoding (sector)
📈 Models Trained
Linear Regression
Random Forest
Extra Trees
Gradient Boosting
XGBoost
🏆 Best Model (XGBoost)
R²: 0.9045
MAE: 0.4373 (after hyperparameter tuning)
Used RandomizedSearchCV for optimization
Saved complete pipeline (preprocessing + model) for deployment
🧠 Recommendation System

Built a hybrid content-based recommender using 3 independent similarity engines:

1️⃣ Facility-Based Similarity
TF-IDF on ~130 amenities
Cosine similarity → captures lifestyle similarity
2️⃣ Price & Configuration Similarity
Engineered BHK-wise:
Price range + area range features
Applied scaling + cosine similarity
Captures budget & size compatibility
3️⃣ Location-Based Similarity
Extracted nearby landmarks with distances
Standardized → meters
Missing values handled with large distance (~55km)
Captures connectivity & convenience
⚙️ Final Hybrid Score
Similarity = 0.5 × Facility + 0.8 × Price + 1.0 × Location
Returns Top-N similar societies
Ensures alignment across:
📍 Location
💰 Budget
🏡 Lifestyle
💡 Key Highlights
Real-world messy data → clean, structured dataset
Strong feature engineering + dimensionality reduction
Robust multi-method feature selection
High-performing model (R² ~0.90)
Hybrid recommender system (rare in student projects)
End-to-end pipeline → ready for deployment
🛠️ Tech Stack
Python (Pandas, NumPy, Scikit-learn)
XGBoost
Seaborn / Matplotlib
ydata-profiling
Category Encoders (Target Encoding)

👨‍💻 Author

Ashutosh Rana B.Tech Computer Science [www.linkedin.com/in/ashutosh-rana-7258432a7]
