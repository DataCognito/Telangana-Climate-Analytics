**Telangana Climate Zone Segmentation Analysis**

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
**Univariate Analysis**
<img width="616" height="302" alt="image" src="https://github.com/user-attachments/assets/d03f4115-0cad-40f8-8cac-7552f9cbf1f0" />

**Interpretation:** 
•	This distribution shows Telangana's hottest daily temperatures dominate between 30°C and 36°C, peaking around 33°C, showing consistent hot, daytime conditions. 
•	This pattern reflects a hot, sweaty summers, where high temperatures are common and cooler outliers are rare. 
•	The cooler days bring monsoon relief, helping them pinpoint hotter zones for smarter crop planning.

<img width="577" height="351" alt="image" src="https://github.com/user-attachments/assets/c651d5aa-0f9c-4307-acd5-447c0934ca11" />

**Interpretation:**
•	This histogram shows Telangana's rainfall peaking towards dry days at 0mm with light spread up to 50mm among dry seasons and occasional monsoon days extremes. 
•	The dry dominant patterns along with intense rain hotspots is crucial for water usage.

<img width="585" height="390" alt="image" src="https://github.com/user-attachments/assets/9b0c447b-cf20-48f3-8b09-670493894c4d" />

**Interpretation:**
•	This histogram shows heat index of Telangana, mostly hitting 30 - 40 with extra sweaty summer days that drain crops and light presence around 25 - 30. 
•	The rare peaks near 50 make the hottest danger zone for targeted climate planning.

<img width="693" height="352" alt="image" src="https://github.com/user-attachments/assets/c3de6e4e-00b6-4f9d-a694-e9b75de44845" />

**Interpretation:** 
•	This line chart shows Telangana's seasonal climate patterns. Maximum temperature peaks around 40°C in April-May marking the most stressful period for summer crops due to rapid moisture loss. 
•	As temperatures subside, rainfall increases from June-September indicating the monsoon season, peaking in September. 
•	For agriculture planning, this shows two distinct zones: high irrigation summer and high moisture monsoon where managing field drainage and water logging becomes the priority.

**Bivariate Analysis**
<img width="940" height="555" alt="image" src="https://github.com/user-attachments/assets/4c126232-b5ae-4ee4-8608-8b34604480aa" />

**Interpretation:** 
•	This correlation matrix shows that maximum temperature is the primary driver of the heat-index (0.99) making extreme heat the single biggest stressor for local crops.
•	The moderate negative correlation between heat and humidity reveals a double threat as hotter days are generally drier. 
•	This proves that for agricultural segmentation, the most critical factor is managing the temperature humidity balance to protect soil moisture and prevent crop wilting.

<img width="584" height="450" alt="image" src="https://github.com/user-attachments/assets/990f2507-6357-4251-af16-c0e9bf649a69" />

**Interpretation:**
•	This chart shows that as temperature rises, the heat index reaches dangerous peaks above 50 in May and June. 
•	Most months stay hot, with 34°C outliers showing those precious cooler days rather than measurement errors.
•	This late Q2 period (May-June) is high risk window for agriculture where actual heat stress is much harder on the body than the actual temperature shows.

<img width="588" height="444" alt="image" src="https://github.com/user-attachments/assets/9e4853f8-5e0f-4852-bd0c-edd7532e7306" />

**Interpretation:** 
•	This chart shows a wide range of conditions but with a clear pattern: as temperatures rise towards 45°C, humidity level tends to drop though they rarely fall below 20%. 
•	The heavy concentration of data at the top (80% - 100% humidity) across all temperatures show high moisture days are very common, regardless of how hot it becomes.
•	The empty space in bottom-left corner shows cool dry days are rare. 
•	If cooler day (around 20°C) we can always expect high humidity.

<img width="591" height="391" alt="image" src="https://github.com/user-attachments/assets/91cb22d8-9930-4442-8190-65db32586887" />

**Interpretation:**
•	The rainfall remains low early in the year but spikes in May reaching peak in September. 
•	July and August have more consistent moisture for crop growth, September is an unpredictable month seeing extreme downpours of nearly 500mm that far exceed the rest of the year. 
•	It makes September the critical window where rain transitions from a helpful resource to a high risk for crop damage, soil erosion, and harvest disruption.

<img width="881" height="673" alt="image" src="https://github.com/user-attachments/assets/a6fffc10-5e2f-421d-b437-c627641189d7" />

**District**	**Avg. Max Temperature**
Khammam	                35.37
Mulugu	                35.17
Mancherial	        35.07
Peddapalli	        35.04
Jayashankar	        35.00
Jagtial	                34.87
Nalgonda	        34.87
Suryapet	        34.84
Bhadradri Kothagudem	34.82
Mahabubabad	        34.72
Karimnagar	        34.53
Jogulamba Gadwal	34.42
Warangal	        34.40
Hyderabad	        34.40
Nirmal	                34.38
Wanaparthy	        34.34
Kumuram Bheem	        34.33
Nizamabad	        34.28
Yadadri Bhuvanagiri	34.14
Hanumakonda	        34.08
Medchal-Malkajgiri	34.08
Adilabad	        34.06
Rajanna Sircilla	34.06
Jangaon	                33.98
Mahabubnagar	        33.96
Kamareddy	        33.92
Rangareddy	        33.71
Narayanpet	        33.59
Nagarkurnool	        33.55
Siddipet	        33.49
Medak	                33.37
Vikarabad	        33.33
Sangareddy              33.29

**Interpretation:**
•	This bar chart shows average maximum temperatures are consistent across the region, with all major districts between 33°C and 35.5°C.
•	Khammam and Mulugu are the warmest zones consistently staying above 35°C threshold. 
•	Temperature between hottest and coolest districts is about 2°C this slight variation can influence local energy demands. 
•	For crop planning, these temperatures suggest that while hottest district require more aggressive irrigation, even the cooler districts like Sangareddy remain high enough to impact soil health and water requirements.

**Multivariate Analysis**

<img width="575" height="433" alt="image" src="https://github.com/user-attachments/assets/ab33470e-69ad-48f6-8dd2-1c91eebe5ad2" />

**Interpretation:**
•	This pie chart shows two distinct agricultural profiles: the Balanced Zone (90.8%) and the Monsoon Zone (9.2%). 
•	For most of the region, the focus must remain on versatile irrigation to mitigate consistent heat stress. 
•	The smaller Monsoon zone marks high priority areas requiring drainage infrastructure and flood resistant crops to survive extreme in September. 
•	This approach ensures that water management and crop selection are precise to local climate's real-world risks.

<img width="580" height="557" alt="image" src="https://github.com/user-attachments/assets/1eb5a532-2acb-49a1-a1d6-070a552042e4" />

**Interpretation:**
•	This chart connects heat, rain, and humidity.
•	It clearly shows heat is the main driver for crop stress but the rainfall bars show occasional floods, dry days are the daily reality for most farmers. 
•	While the outliers at 34°C, rest of the data shows a clear transition. 
•	For a farmer, this critical shift from surviving summer heat to managing monsoon moisture.

<img width="578" height="468" alt="image" src="https://github.com/user-attachments/assets/2a154f06-9d21-47c8-80ca-0a1a5a01d2e1" />

**Interpretation:**
•	This boxplot shows the thermal stability of our two regions. 
•	The balanced zone is consistently warmer, while monsoon zone shows a lower, wider temperature range due to the cooling effect of rain. 
•	Although their averages differ, both zones share identical extreme peaks, proving that heat protection is a universal requirement across Telangana.

**Summary of Findings**
•	Climate Zones: Rule-based partitioning confirmed 90.81% of data in the Balanced Zone, with 9.19% in the Monsoon Zone.
•	Thermal Stress: A mean Heat Index of 38.81 shows that humidity significantly intensifies perceived heat over raw temperature.
•	Extreme Volatility: Rainfall is the most unpredictable variable, with a 378.04% Coefficient of Variation and frequent extreme outliers.
•	Data Nature: The non-normal distribution justifies our reliance on the Median and IQR for accurate seasonal planning.

**Types of Analysis**

**Descriptive Analysis**
We utilized central tendency and dispersion metrics to summarize the historical climate patterns.
Key Finding: Our analysis confirmed a mean Heat Index of 38.81 and identified that 90.81% of the data resides within the Balanced Zone.

**Diagnostic Analysis**
We examined the relationships between variables like Humidity and Max Temp to understand the drivers of thermal stress.
Key Finding: High Skewness (9.30) and Kurtosis (169.62) in rainfall data diagnosed the presence of extreme, non-normal weather events rather than a steady climatic trend.

**Predictive Analysis**
Using seasonal trends and the Month feature, we can forecast periods of high volatility.
Key Finding: The consistent Coefficient of Variation (378.04%) in rain suggests that while total volume is hard to pin down, the frequency of outliers remains a predictable seasonal risk.

**Prescriptive Analysis**
This stage uses our findings to recommend specific agricultural and safety actions.
Key Finding: Because the data is non-normal, we prescribe using the Median and IQR for resource allocation to ensure planning accounts for typical days while preparing for extreme outliers.

**Future Enhancements and Suggestions**
•	Advanced Modelling: Transition from rule-based partitioning to Machine Learning algorithms (e.g., Random Forest or K-Means) to automate and refine climate zone classification.
•	Feature Expansion: Integrate Soil Moisture and Evapotranspiration data to provide a holistic assessment of agricultural water stress beyond raw rainfall.
•	Real-time Deployment: Develop an Interactive Dashboard (Power BI) to provide stakeholders with live heat index alerts and seasonal trend visualizations.
•	Spatial Granularity: Incorporate GPS-tagged micro-climate data to enable hyper-local forecasting for precise resource allocation across specific farm blocks.

**Conclusion**
This analysis gives Telangana farmers a clear roadmap: 90.8% of areas need better irrigation while 9.2% monsoon zones require flood protection. Heat Index (38.81°C) shows humidity makes heat feel much worse than temperature alone.


