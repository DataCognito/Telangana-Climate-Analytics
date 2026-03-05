<img width="616" height="302" alt="image" src="https://github.com/user-attachments/assets/4ab2bd9e-64e3-4294-a8c1-943f60f00e13" /><img width="616" height="302" alt="image" src="https://github.com/user-attachments/assets/de3be4c9-6807-4300-912d-74e683772bd4" />Telangana Climate Zone Segmentation Analysis

**Project Overview**
I started this project to make sense of the erratic weather patterns that Telangana’s farmers deal with every single day. Instead of just looking at a spreadsheet of numbers, I used Python to dig deeper and understand the actual stress these conditions put on our crops. I spent time cleaning the data to make sure it was reliable, exploring how heat and rain interact, and creating visuals that tell a clear story of the land. My goal was to move past generic weather reports and create a zonal strategy identifying which areas are most at risk so we can give farmers the practical, data-backed insights they need to protect their harvests and make better decisions for the future.

**Data Source**
Dataset Name: Telangana State Open Weather Data
Source: Hugging Face
File Type: CSV
Number of Records: 242828 (Cleaned Data)
Number of Attributes: 12 (Cleaned Data)
The dataset contains information related to daily weather conditions across various districts to identify seasonal risks.

**Problem Statement**
Telangana is rich in climate data, but most of it stays locked in complex spreadsheets that offer no real help to a farmer standing in a field. Without a clear way to interpret these numbers, it’s nearly impossible to see the hidden patterns that determine whether a crop survives or fails.

This project aims to bridge the gap between complex climate data and actual farming by pinpointing areas most at risk for extreme heat or flooding that help farmers protect their livelihoods.

**Objectives**
•	Understand the dataset structure and relationships among the weather attributes to ensure a solid analytics baseline.
•	Clean and prepare the data by handling missing values and duplicates to maintain high data integrity.
•	Perform Exploratory Data Analysis (EDA) using univariate, bivariate and multivariate techniques to uncover hidden climate patterns and correlations.
•	Create clear, intuitive visualizations including histograms, scatterplots, boxplots, pairplot, to translate complex climate data into clear climate insights.
•	Generate actionable insights that help move agricultural planning from a reactive approach to proactive planning.

**Attribute (Column / Feature) Details**
Attribute Name	Description
District	          Geographic identifier for localized risk zones
Date	              Daily timestamp for seasonal trends
Rain(mm)	          Precipitation levels to monitor drought/flood risk
Min/Max Wind Speed	Intensity of air movement and storm potential
Min/Max Humidity	  Moisture levels affecting crop health
Min/Max Temperature	Daily thermal range and extreme heat markers
Heat_Index          Temperature measuring environmental stress
Month	              Time feature used for seasonal grouping
Temp_Category	      Qualitative classification of thermal intensity.

**Tools & Technologies**
Python
Pandas
NumPy
Matplotlib
Seaborn
Google Collab

**Data Pre-Processing and Feature Engineering**
The dataset was prepared for analysis using standardized data preprocessing techniques.

**Data Cleaning Steps**
•	Checked data types of all columns.
•	Verified that dataset has no missing or null values.
•	Removed the Mandal column to focus on a broader district level climate strategy.
•	Identified and removed duplicate records to ensure integrity for weather patterns.
•	Corrected inconsistent data by applying median imputation and preserving statistical trends.
•	Converted date attribute to a datetime format for time series analysis.

**Feature Engineering**
New features were created to improve analysis and visualization.
•	Month: Created from the Date column.
•	Temp_category: Created based on the Max Temperature column.
•	Heat_Index: A calculated field generated using temperature and humidity.
•	Climate_Zone (Rule-Based Partitioning): This classification was created using Z-Score Standardization to group data into three distinct zones based on temperature and rainfall.
        • Hot-Dry Zone: Defined by high temperature scores (> 0.5) and low rain scores (< -0.5).
        • Monsoon Zone: Defined by high rain scores (> 0.5).
        • Balanced Zone: Includes all records not meeting the extreme threshold criteria. 

**Analysis and Visualizations**
This dataset was analysed using Exploratory Data Analysis techniques to uncover seasonal trends and climate correlations.

**Exploratory Data Analysis**
Temporal trends: We tracked how temperature and rainfall shifted month-to-month to pinpoint exactly when seasonal spikes occur.
Severity levels: By using our custom Temp Category, we were able to see how often the area hit extreme heat levels.
Correlation checks: We investigated how different factors, like humidity and our calculated Heat Index, work together to drive environmental stress.
Regional patterns: By comparing weather data across districts, we identified specific "risk zones" that are more vulnerable than others.

**Outcome:** The analysis revealed that the Heat Index, the combined effect of temperature and humidity is more accurate driver of environmental stress than either factor alone. By mapping these patterns, we pinpointed high-risk zones where heat levels frequently cross safety thresholds for crop health and agricultural planning.

**Data Visualization**
Purpose: To turn complex climate data into clear, visual patterns that make high-risk factors easy to identify immediately.

**Techniques Used**
Histograms: Used to show the distribution and frequency of rainfall and temperature.
Boxplots: Essential for spotting weather outliers in wind speed and moisture.
Bar charts: Compared monthly averages to highlight the shift between dry and wet seasons.
Scatter plots: Examined how humidity levels directly drive the intensity of the Heat Index.
Heatmaps: Generated a correlation matrix to show how the weather attributes interact.

**Exploratory Data Analysis (EDA)**
Initial Inspection

Data frame structure: We verified that the dataset correctly includes all core climate attributes, such as rainfall and humidity, alongside our engineered Heat Index.
Statistical summary: By using the describe () function, we reviewed the central trends of our variables, noting that Max Temperature showed a wide seasonal spread across different districts.
Null values: 0% null values across 242,828 records verified via df.isnull().sum()
Duplicate records: Removed 136 duplicate records (0.06%) using df.drop_duplicates() 

**Statistical Analysis**
Statistical measures were used to summarize the dataset.

**Central Tendency:**
•	Mean, Median, Mode: Calculated for all numeric climate columns to establish a baseline for weather intensity.
•	The average Max Temp is 34.25°C, while the median is 33.7°C, showing a slight skewness due to extreme heat spikes.
•	Rainfall Disparity: The mean rainfall (2.78 mm) is significantly higher than the median (0.0 mm), confirming that rare, heavy storms pull the average upward.

**Dispersion**
•	Variance & Standard Deviation: Measured to quantify the high variability and uneven distribution of weather events.
•	Standard Deviation (Std Dev): We observed a high standard deviation in Min Humidity (18.32%), indicating inconsistent moisture levels across the dataset.
•	Volatility (CV%): The Coefficient of Variation confirms that Wind Speed (388.28%) and Rain (378.04%) are the most volatile and unpredictable factors.

**Shape of Distribution**
•	Skewness & Kurtosis: Our results show strong positive skew (9.30) and high kurtosis (169.62) in Rainfall, indicating a long-tailed distribution with many outliers.
•	Non-Normal Nature: Together, these metrics emphasize that the dataset is non-normal, requiring robust statistical methods rather than relying solely on simple means.

**Key Insights**
Trend Analysis: Climate values show clear seasonal fluctuations, with the Heat Index (38.81) remaining a persistent stressor.
Predictability: Low CV in Heat Index (9.66%) suggests thermal stress is consistent, while high CV in Rain makes it the primary risk driver.
Strategic Planning: Due to extreme outliers in wind and rain, agricultural planning must prioritize the Median and IQR for reliable estimates.

**Data Visualization**
1. Univariate Analysis














