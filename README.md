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

<img width="635" height="215" alt="Image" src="https://github.com/user-attachments/assets/293727b8-8056-4ada-be47-429ff228751c" />

<img width="708" height="470" alt="Image" src="https://github.com/user-attachments/assets/34bc60c2-3bbc-4be2-bb93-0ec64af84d94" />

<img width="704" height="466" alt="Image" src="https://github.com/user-attachments/assets/7e792304-8343-4935-8a9c-07a72e401b92" />
<img width="629" height="535" alt="Image" src="https://github.com/user-attachments/assets/38bd731c-9c50-4196-bbdb-afe45c574444" />

<img width="964" height="505" alt="Image" src="https://github.com/user-attachments/assets/46e00e5d-3d8c-47fd-b5f2-6d5591264ed7" />

<img width="958" height="451" alt="Image" src="https://github.com/user-attachments/assets/13370e92-b13d-479c-95e8-d77055e24db7" />

<img width="955" height="461" alt="Image" src="https://github.com/user-attachments/assets/0b357ff0-46bd-4e0b-bcd5-f1b31373cd2c" />

<img width="956" height="453" alt="Image" src="https://github.com/user-attachments/assets/bbbb27b2-13e4-49a6-a203-0c9f507f806f" />

<img width="951" height="454" alt="Image" src="https://github.com/user-attachments/assets/98ceff1e-c597-498c-8b45-8a8022bdd12b" />

<img width="954" height="436" alt="Image" src="https://github.com/user-attachments/assets/b0d794ce-624e-406b-9d8f-5fe1e1c373b1" />


6. Model Training and Evaluation
Three regression models were trained to predict the Recreation Visits:
Linear Regression: A baseline model for a linear relationship between features and the target.
Random Forest Regressor: An ensemble model that builds multiple decision trees to improve prediction accuracy.
Gradient Boosting Regressor: Another powerful ensemble model that builds trees sequentially, with each new tree correcting the errors of the previous ones.
<img width="825" height="504" alt="Image" src="https://github.com/user-attachments/assets/1c53f41f-b95c-4e06-8646-65711af119d3" />

The data was split into a training set (80%) and a testing set (20%) to evaluate the models on unseen data. The models were evaluated using the following metrics:
Mean Absolute Error (MAE): Measures the average magnitude of the errors in a set of predictions, without considering their direction.
Mean Squared Error (MSE): Measures the average of the squares of the errors. It penalizes larger errors more heavily.
R-squared (): Represents the proportion of the variance for a dependent variable that's explained by an independent variable or variables in a regression model. A score closer to 1.0 indicates a better fit.
Model Performance Summary:
The Python code creates a bar chart to visually compare the performance of the three trained models. It uses two separate y-axes to display both RMSE and scores on the same graph, which is an effective way to compare metrics with different scales.
Code Interpretation: The code sets up two y-axes (ax1 and ax2). The first axis, ax1, plots the RMSE scores (lower is better) using salmon-colored bars. The second axis, ax2, plots the R2 scores (higher is better) using skyblue-colored bars. The x-axis displays the names of the three models.
Graph Interpretation: Based on the provided data, the graph will show the following:
The Random Forest model has the shortest salmon bar, representing the lowest RMSE score (24882.04). This indicates its predictions have the smallest average error.
The Random Forest model also has the tallest skyblue bar, representing the highest R2 score (0.98). This means it explains 98% of the variance in the recreation visits, a very strong result.
In contrast, Linear Regression has the tallest salmon bar and the shortest skyblue bar, making it the worst-performing model.
Gradient Boosting performs well, but its RMSE is higher and its R2 is lower than that of the Random Forest model.
This visualization clearly and intuitively confirms that the Random Forest Regressor is the best-performing model for this forecasting task.

<img width="932" height="522" alt="Image" src="https://github.com/user-attachments/assets/4ed487d3-affc-4533-a6c5-31635760885c" />


7. Best Model Selection
Based on the evaluation metrics, the Random Forest Regressor was selected as the best-performing model. It achieved the highest R2 score of approximately 0.98, indicating it explained over 98% of the variance in recreation visits, and had the lowest MAE and MSE.

<img width="814" height="482" alt="Image" src="https://github.com/user-attachments/assets/e7cc942d-105e-4394-93b8-9d728476d7de" />

8. Testing the Model on New Subjects
To ensure the model is working correctly, the best-performing model (Random Forest Regressor) was then used to make a prediction for a new, hypothetical data point to simulate a real-world forecasting scenario. A hypothetical visit to Yellowstone National Park in July 2025 was put in place as the test subject in the prediction of the recreation visit count as shown below.

<img width="1011" height="561" alt="Image" src="https://github.com/user-attachments/assets/14a9997c-9737-4933-9eb9-50931e5b3ee0" />

9. Further Analysis with Power BI
Power BI was used to create interactive dashboards to visualize and analyze the data in a more dynamic way. This section includes key visualizations that highlight trends, comparisons, and other insights from the dataset, complementing the predictive model's results.
Seasonal Trends: The visualizations clearly show that visitation follows a strong seasonal pattern. Visitation consistently peaks during the summer months (June, July, August) and reaches its lowest points in the winter (December, January). This seasonality is a powerful predictor for the model.

<img width="865" height="540" alt="Image" src="https://github.com/user-attachments/assets/9a28234b-dc26-4dde-8c60-4647a5d9851c" />

Furthermore the 'Sum of recreation_visits by MonthName' visualisation with the National Historical Parks filter to only show National Historical Parks, further reinforces the importance of seasonality and specific holidays.The month of July has the largest percentage of visits, accounting for 4M (12.56%) of the total. This is a crucial insight that can be directly attributed to the 4th of July holiday. Many Americans visit historical sites during this period to celebrate national history, making it the peak month for this specific park type.

<img width="868" height="487" alt="Image" src="https://github.com/user-attachments/assets/3bde45b6-b03c-4e3c-9032-a86c61542b4e" />

Geographical Popularity: By analyzing visits by State, it is evident that states with multiple iconic parks, such as Utah (Zion NP), California, and North Carolina, receive a disproportionately high number of visitors. This highlights the importance of location as a predictor.

<img width="752" height="482" alt="Image" src="https://github.com/user-attachments/assets/a11526b6-66ae-48f1-a96c-48d94350b564" />


Site Popularity (Park Type): The visualizations reveal a significant difference in visitor numbers across different park types. National Parks are by far the most popular. This indicates that the type of park is a critical factor in forecasting visitation.

<img width="835" height="467" alt="Image" src="https://github.com/user-attachments/assets/3b3b8782-17e3-4ab6-9196-d815d7b1ca82" />


Correlation between Visits and Hours: There is a strong positive correlation between recreation_visits and recreation_hours. This indicates that when more people visit a park, they also tend to stay for longer periods.Shows if a park is visited frequently, and whether people stay longer or shorter.

<img width="815" height="415" alt="Image" src="https://github.com/user-attachments/assets/e97285c1-00b2-4f09-af78-7f81253130a7" />

Dax Formulas
The dax formula was put in place to add a month name column for enhanced simplicity in data analysis.Then it was applied to add a season column for the analysis of season trends.

<img width="493" height="306" alt="Image" src="https://github.com/user-attachments/assets/a0011f85-bccb-4284-b6fa-9eb2dc548615" />

<img width="600" height="146" alt="Image" src="https://github.com/user-attachments/assets/3b074797-5335-498d-8e10-f2f161d08175" />


10. Conclusion
The analysis successfully demonstrates that a machine learning model, specifically a Random Forest Regressor, can accurately predict recreation visits to U.S. National Parks based on the provided dataset. The model's high performance metrics and successful prediction on a new test subject confirm its reliability. This model can be a valuable tool for forecasting park attendance, which can assist in resource management and planning.

11. Recommendations : Data-Driven Business Suggestions

a.Dynamic Staffing: Use the predictive model's forecasts to adjust staffing levels in real-time. During peak summer months (June, July, August), schedule additional staff for visitor centers, maintenance, and ranger patrols. Conversely, reduce staffing in off-peak months to optimize labor costs.

b.Inventory Management: Anticipate the demand for park passes, maps, and gift shop items by using historical data and forecasts. Ensure inventories are fully stocked before the summer surge and adjusted appropriately for the low-demand seasons.

c.Promote Off-Season Travel: Launch targeted marketing campaigns highlighting the unique benefits of visiting in the spring or fall. Emphasize activities like fall foliage hikes, winter wildlife viewing, or springtime wildflowers to attract visitors during traditionally slower months.

12. Future work
a.Integrate External Data Sources
-Add weather, event, and holiday data to capture real-time factors influencing visitation.
Example: Rainfall might reduce visits; public holidays may cause spikes.
b.Park-Specific Predictive Models
-Build individualized models for high-traffic parks like Yellowstone or Zion.
-These models could account for park-specific trends and features (e.g., accessibility, capacity).
c.Real-Time Forecasting System
-Automate the data pipeline to update predictions regularly (weekly/monthly).
-Use APIs to fetch live data (e.g., Google Trends, traffic data).











