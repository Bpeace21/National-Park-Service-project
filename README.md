National Park Service Analysis Report
Course: Introduction to Big Data Analytics
Instructor: Eric Maniraguha
Assignment Date: August 3, 2025
Name: BIZIMA PeaceID: 27778
1. Project Overview
This project aims to predict the number of recreation visits to U.S. National Parks using historical data provided by the National Park Service. The analysis involves data cleaning, exploratory data analysis, and training multiple machine learning models to identify the best predictor. The best-performing model is then used to make predictions on new, unseen data.
-The objectives of this analysis are to:
-Explore and clean the National Park Service dataset to ensure quality data for analysis.
-Examine how factors such as season trends,and site popularity impact the national park visitation .
-Develop an interactive Power BI dashboard that presents these insights clearly and professionally.
-Provide data-driven recommendations to enhance the National Park’s operations based on the obtained insights and deductions.
-Future work

The scope of this project is to predict the number of recreation visits to the U.S. National Parks using historical data provided by the National Park Service.Specifically, the data covers:
Timeframe: Monthly data for the year 2024.
Metrics: Recreation Visits and Recreation Hours.
Dimensions:
Individual parks (Park, Unit Code).
Park classifications (Park Type).
Geographic locations (Region, State).

2. Methodology
The project followed a structured, three-phase methodology to forecast national park visitation accurately.
 The National Park Service dataset was downloaded from https://www.nps.gov/subjects/socialscience/visitor-use-statistics-dashboard.
In Phase 1, raw data was cleaned and pre-processed in Python, converting messy text fields into usable numeric formats and standardizing columns.
Exploratory Data Analysis (EDA) was conducted in both Jupyter Notebook unveiling visualizations such as histograms, boxplots, and correlation heatmaps
 to understand the relationship between variables. In Phase 2, categorical data was encoded, and three regression models—Linear Regression, Random Forest,
 and Gradient Boosting—were trained and evaluated using RMSE and R². The Random Forest Regressor emerged as the most accurate model. In Phase 3, this model
was applied to forecast future visits, demonstrating practical forecasting capability. 
We also imported the cleaned enhanced version of the National Park service in Power BI and hereafter created interactive dashboards to reveal key patterns
such as seasonal visitation spikes and popular park types. A custom DAX formula was used to create a season-based grouping for deeper insights.

4. Tools and Techniques
Jupyter Notebook: For data cleaning, exploratory data analysis (EDA), and machine learning model training.
Python Libraries:
pandas and numpy: For data manipulation and numerical operations.
scikit-learn (implied): For building and evaluating the machine learning models, including LabelEncoder, LinearRegression, RandomForestRegressor,
 and GradientBoostingRegressor.
Power BI: For creating interactive data visualizations and performing data analysis using a DAX formula to categorize data by season.
Machine Learning Models: Specifically, Linear Regression, Random Forest Regressor, and Gradient Boosting Regressor were trained and evaluated.

4. Dataset and Data Cleaning
The dataset used is the "NPS Public Use Statistics Query Builder" which contains monthly recreation visit data for various National Parks. Before analysis, the data was cleaned to handle missing values and convert columns to the correct data types.
Data Cleaning Steps:
Handling Missing Values: Rows with any missing data were dropped.
Data Type Conversion: The Recreation Visits column, which was initially stored as an object with commas, was converted to a numeric type. Year and Month columns were converted to integers.











