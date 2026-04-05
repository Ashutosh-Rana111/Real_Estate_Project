🏠 Gurgaon Real Estate: Data Science Pipeline

This repository contains the complete end-to-end data science workflow for the Gurgaon Real Estate project. It covers everything from raw data scraping and cleaning to advanced feature engineering and model optimization.

Project Overview

The goal of this project was to transform raw, messy real estate listing data into a high-performance machine learning model capable of predicting property prices and recommending similar apartments in Gurgaon.

Data Science Lifecycle

1. Data Cleaning & Preprocessing

Handled missing values in critical columns like floorNum, facing, and agePossession.

Standardized area measurements (converting Square Yards and Acres to Square Feet).

Cleaned text data in the additionalRooms and features columns using string manipulation.

2. Exploratory Data Analysis (EDA)

Univariate Analysis: Analyzed the distribution of prices and areas.

Bivariate Analysis: Explored relationships between BHK, Sector, and Price.

Multivariate Analysis: Used heatmaps and pair plots to identify correlations.

3. Feature Engineering & Outlier Detection

Outlier Removal: Used the IQR (Interquartile Range) method and domain knowledge to remove unrealistic listings (e.g., 100 sq ft houses priced at 10 Cr).

Feature Creation: Developed a 'Luxury Score' based on the number of premium amenities provided.

Transformation: Applied Log Transformations to skewed numerical features to improve model convergence.

4. Model Building & Selection

Tested multiple algorithms: Linear Regression, Support Vector Regression (SVR), Random Forest, and XGBoost.

Used Target Encoding for the 'Sector' column to handle high-cardinality categorical data.

Hyperparameter Tuning: Optimized the XGBoost model using GridSearchCV to achieve the lowest MAE (Mean Absolute Error).

5. Recommendation Engine Logic

Created a hybrid similarity matrix using Cosine Similarity.

Balanced three distinct factors: Geographical Location, Price Point, and Facility list to power the "Similar Properties" feature.


⚙️ Tech Stack

Languages: Python

Libraries: Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn, Category Encoders

Tools: Jupyter Notebooks, Anaconda

🔗 Related Projects

This pipeline provides the backbone for the Gurgaon Real Estate Web App, which serves as the interactive frontend for these models.
Check it out here : https://gurgaonrealestateapp.streamlit.app/

👨‍💻 Author

Ashutosh Rana B.Tech Computer Science [www.linkedin.com/in/ashutosh-rana-7258432a7]
