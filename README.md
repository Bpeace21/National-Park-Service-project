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

<img width="1007" height="348" alt="Image" src="https://github.com/user-attachments/assets/ee181090-6713-47f4-a8a7-3b437f35017e" />





5. Analysis
Exploratory Data Analysis
A more in-depth analysis of the data reveals was conducted to uncover relationships within the dataset, and from there several key insights emerged.
Jupyter Notebook Deductions
Data Structure: The info() output from the Jupyter Notebook confirms that all null values were successfully dropped and that the recreation_visits and recreation_hours columns were correctly converted to int64 data types, which is essential for model training.
Summary Statistics: The describe() output provides a statistical overview of the data. The mean, standard deviation, and quartiles of recreation_visits give a clear picture of the distribution of visitor numbers. The large standard deviation indicates a wide range of visitor numbers, likely influenced by the popularity of different parks.

Jupyter Notebook Visualizations
Distribution of Recreation Visits and Hours: The histograms for recreation_visits and recreation_hours show a highly right-skewed distribution. This means that a small number of parks receive an extremely high number of visits and recreation hours, while the vast majority of parks have relatively low visitation numbers. This indicates a few popular "outlier" parks.
Boxplots for Outliers: The boxplots for numeric variables highlight a significant number of outliers, particularly in the recreation_visits and recreation_hours columns. The extended whiskers and individual data points beyond the boxes confirm the presence of a few highly popular parks that skew the distribution.
Correlation Heatmap: The heatmap reveals a very strong positive correlation between recreation_visits and recreation_hours. The correlation coefficient is likely close to 1.0, which makes sense as more visitors will naturally lead to more recreation hours. This relationship can be leveraged by the model.
Recreation Visits by Categorical Variables: The boxplots for park, park_type, region, and state show a clear variation in visitation based on these categories.
By park: The boxplots show that some individual parks have significantly higher median and outlier visitation numbers than others.
By park_type: National Parks receive a higher number of visitors compared to other types like National Historical Parks or National Preserves.
By region and state: Certain regions and states (e.g., Intermountain region, Utah state) have much higher visitation numbers, indicating geographical popularity.
Recreation Visits Over Time: The line plot of recreation_visits over months reveals a strong and consistent seasonal trend. Visitation peaks dramatically in the summer months and drops in the winter. The hue='year' parameter allows us to see this trend across different years.

<img width="708" height="470" alt="Image" src="https://github.com/user-attachments/assets/34bc60c2-3bbc-4be2-bb93-0ec64af84d94" />

<img width="704" height="466" alt="Image" src="https://github.com/user-attachments/assets/7e792304-8343-4935-8a9c-07a72e401b92" />

<img width="964" height="505" alt="Image" src="https://github.com/user-attachments/assets/46e00e5d-3d8c-47fd-b5f2-6d5591264ed7" />

<img width="629" height="535" alt="Image" src="https://github.com/user-attachments/assets/38bd731c-9c50-4196-bbdb-afe45c574444" />

<img width="958" height="451" alt="Image" src="https://github.com/user-attachments/assets/13370e92-b13d-479c-95e8-d77055e24db7" />

<img width="955" height="461" alt="Image" src="https://github.com/user-attachments/assets/0b357ff0-46bd-4e0b-bcd5-f1b31373cd2c" />

<img width="956" height="453" alt="Image" src="https://github.com/user-attachments/assets/bbbb27b2-13e4-49a6-a203-0c9f507f806f" />

<img width="951" height="454" alt="Image" src="https://github.com/user-attachments/assets/98ceff1e-c597-498c-8b45-8a8022bdd12b" />

<img width="954" height="436" alt="Image" src="https://github.com/user-attachments/assets/b0d794ce-624e-406b-9d8f-5fe1e1c373b1" />






