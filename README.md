
## 🌍 Global Weather & Air Quality Analysis (2024 - 2026) using Python
## 📌 Project Overview

- This project analyzes global weather conditions and air quality data across different countries. The analysis focuses on identifying weather patterns, air pollution levels, and the relationship between weather conditions and air quality.
## 💼Business Problem
- Air quality and weather conditions vary significantly across different countries and cities, making it difficult to identify pollution hotspots and understand the environmental factors associated with poor air quality.
- The business problem is to analyze global weather and air-quality data to identify high-pollution locations, understand patterns and relationships between weather conditions and air-quality indicators, and provide data-driven insights that can support effective environmental monitoring, pollution management, and decision-making.
## 🎯Objectives
- 1.	To analyze the distribution and variability of temperature across the dataset. 
- 2.	To identify and visualize the most frequently occurring weather conditions in the dataset. 
- 3.	To analyze global weather conditions across different countries. 
- 4.	To identify relationships between weather parameters and air quality indicators using correlation analysis. 
- 5.	To analyze the relationship between actual temperature and feels-like temperature. 
- 6.	To identify locations with higher pollution levels using air quality indicators and pollution categories. 
- 7.	To analyze the monthly distribution and variation of pollution categories. 
- 8.	To examine the relationship between temperature and PM2.5 levels across different pollution categories. 
- 9.	To identify hourly patterns in PM2.5 and PM10 pollution levels.
## 🛠️ Tools & Technologies
- •	Language   -   Python
- •	Environment  -  Google colab
- •	Data Manipulation -  pandas, Numpy
- •	Data Visualization – matplotlib, seaborn
## 📊 Dataset Description
   |Column Name | Data Type | Description|
   |------------|-----------|------------|
   |country|object|The name of the country where the weather and air-quality observation was recorded.|
   |location_name|Object|The name of the city or specific location where the observation was recorded.|
   |latitude|float64|The north–south geographic coordinate of the location, measured in degrees.|
   |longitude|float64|The east–west geographic coordinate of the location, measured in degrees.|
   |time/zone|object|The local time zone of the recorded location.|
   |last_updated|object|The date and time when the weather and air-quality data was last updated.|
   |temperature_celsius|float64|The actual air temperature at a specific location and time, measured in degrees Celsius (°C).|
   |Weather_condition|object|A text description of the observed weather condition, such as Sunny, Cloudy, or Rainy.|
   |wind_kph|float64|The wind speed recorded at the location, measured in kilometres per hour (km/h).|
   |wind_degree|int64|The direction from which the wind is blowing, measured in degrees.|
   |pressure_mb|int64|The atmospheric pressure at the location, measured in millibars (mb).|
   |Precip_mm|float64|The amount of precipitation recorded at a specific location and time, measured in millimetres (mm).|
   |Humidity|int64|The percentage of moisture present in the air at a specific location and time.|
   |cloud|int64|The percentage of the sky covered by clouds.
   |feels_like_celsius|float64|The perceived temperature experienced by people, measured in degrees Celsius (°C).|
   |visibility_km|float64|The distance at which objects can be clearly seen, measured in kilometres (km).|
   |uv_index|float64|A measure of the intensity of ultraviolet (UV) radiation from the sun.|
   |gust_kph|float64|The maximum or sudden increase in wind speed, measured in kilometres per hour (km/h).|
   |air_quality_Carbon_Monoxide|float64|The concentration of carbon monoxide (CO) in the air, indicating a level of air pollution.|
   |air_quality_Ozone|float64|The concentration of ozone (O₃) present in the air, used as an indicator of air quality.|
   |air_quality_Nitrogen_dioxide|float64|The concentration of nitrogen dioxide (NO₂) in the air, an important air-pollution indicator.|
   |air_quality_PM2.5|float64|The concentration of fine particulate matter with a diameter of 2.5 micrometres or less in the air.|
   |air_quality_PM10|float64|The concentration of particulate matter with a diameter of 10 micrometres or less in the air.|
   |air_quality_us-epa-index|int64|The US EPA Air Quality Index value used to indicate the overall level of air pollution and its potential            health impact.|
## Data Analytics Life Cycle
 -  A Data Analytics Pipeline is a step-by-step process used to convert raw data into meaningful insights.
   <img width="777" height="324" alt="image" src="https://github.com/user-attachments/assets/70cb5f9f-0c2b-43d2-ba9f-0db583aa51c7" />
##🧹**Data Cleaning & Preprocessing**
 - During the data cleaning and preprocessing stage, the dataset was carefully reviewed to ensure data quality, consistency, and reliability        before proceeding with further analysis.
 - ## Removal of Unwanted Columns:
   - Unnecessary and redundant columns were removed based on the project objectives. Duplicate unit-based columns such as Fahrenheit, MPH, and         miles were eliminated, along with irrelevant timestamp, moon, and certain air-quality columns. This reduced dataset complexity and created a      focused dataset for weather and air-quality analysis.
 - ## Handling Missing Values:
   - The dataset was checked for missing values using the **isnull().sum()** method. The result showed that all selected columns contained zero            missing values.
   - Therefore, **no missing value imputation** or replacement techniques were required.
- ## Duplicate Check:
   -	Duplicate records were checked using the **duplicated().sum()** method after removing the unwanted and redundant columns. 
   - The result showed that the dataset contained **no duplicate records**, ensuring that each observation was unique and suitable for further analysis.
- ## Standardization of Country Names
   - The unique values in the **country column** were first examined to identify inconsistent country names. During this inspection, some country names were found to be represented in different languages, spellings, and naming formats.
	- To ensure consistency in country-wise grouping and analysis, a mapping dictionary was created to convert these inconsistent representations into standardized country names. The mapping was then applied to the country column.
	- For example, **Malásia** was converted to **Malaysia**, **كولومبيا** to **Colombia**, **Гватемала to Guatemala**, and **火鸡 to Turkey**.
- ## Removal of Invalid Location Entry
   - •	The **location_name** column was examined for invalid or inconsistent entries. An invalid location entry named **#NAME?** was identified, which does not represent an actual geographical location. Therefore, the corresponding record was removed from the dataset to maintain data accuracy.
- ## Outlier Detection and Data Validation
   - 	As part of the data validation process, potential outliers were identified using box plots for selected numerical variables. 
   - This analysis helped detect unusually high or low values that could indicate potential data errors or inconsistencies in the dataset.
   - The following variables were analyzed:
        **wind_kph, gust_kph, air_quality_Carbon_Monoxide,
        air_quality_PM10, pressure_mb**
    <img width="685" height="267" alt="Screenshot 2026-09-02 124306" src="https://github.com/user-attachments/assets/4469e86f-045e-4b4f-ad9a-7db5760a498c" />
  - **Wind Speed:** An unrealistic value of **2963.2 km/h** was identified in the wind_kph column.

  - **Gust Speed:** An unrealistic value of **2970.4 km/h** was identified in the gust_kph column.

  - **Carbon Monoxide:** The air_quality_Carbon_Monoxide column contained a negative value of **-9999**, which is physically invalid.

  - **PM10:** The air_quality_PM10 column contained a negative value of **-1848.15,** which is also physically invalid. A negative value of -1848.15 was identified... Therefore, all negative PM10 values were removed.

  - **Atmospheric Pressure**: Extreme values of **3000 mb and 3006** mb were identified in the pressure_mb column, which are unrealistic for normal atmospheric conditions.
- Therefore, only values that were clearly identified as physically invalid or data-entry errors were removed. The remaining statistically identified outliers were retained to preserve the natural variation and extreme conditions present in the dataset.
- ## 🔧Feature Engineering
  - **Pollution Category:**
    - 	A new column named **pollution_category** was created using the **air_quality_us-epa-index** column. The EPA air quality index values were mapped into meaningful categories such as **Good, Moderate, Unhealthy for Sensitive Groups,  Very Unhealthy, and Hazardous.**
    - This feature helps in analyzing and comparing air quality levels across different locations.
  - **Temperature Category:**
    - 	A new column named **temperature_category** was created based on the **temperature_celsius column**. Temperature values were grouped into meaningful temperature ranges or categories such as **Freezing, Cold, Moderate, Hot.** 
	 - This feature helps to understand the distribution of weather conditions and compare air quality across different temperature levels.
  - **Month Name Extraction:**
     - The **month_name** feature was extracted from the **last_updated** datetime column to analyze monthly variations and seasonal patterns in     temperature and air-quality levels.
  - **Hour Extraction:**
     - •	A new column named **update_hour** was created by extracting the hour component from the **last_updated** datetime column. 
      |New Feature|Derived from|Purpose|
      |-----------|------------|-------|
      |Pollution_category|air_quality_us-epa-index|To classify and compare pollution levels across locations.|
      |Temperature_category|temperature_celsius|To analyze and compare temperature conditions across locations.|
      |Month_name|last_updated|To analyze monthly and seasonal variations|
      |Update_hour|last_updated|To analyze hourly weather and pollution patterns|
- ## Data Transformation
As part of the data transformation process, the dataset was modified to improve data consistency, readability, and usability for further analysis.
 - **Date-Time Conversion:**
  - The last_updated column was initially stored as an object (string) data type. It was converted into the datetime data type to enable proper date- and time-based analysis, sorting, filtering, and visualization.
 - **Column Name Standardization:**
  - The column name condition_text was renamed to weather_condition to make the column name more meaningful, descriptive, and easier to understand during analysis.
- ## Final EDA Validation
  - Verified the final number of **rows(125691) and columns(29)** in the dataset.
  - Reviewed the **remaining column names and their data types.**
  - Rechecked for **missing values** to ensure that no unexpected null values were introduced during the transformation process.
  - Rechecked for **duplicate records** to confirm data uniqueness.
  - Validated the newly created pollution category, temperature category, and hour columns.
  - Reviewed the numerical variables to ensure that previously identified invalid and unrealistic values had been properly handled.
  - Checked the overall data structure and value distributions to identify any remaining inconsistencies.
- ## Statistical Analysis
   |Columns Name|Mean|Median|Mode|Variance|Standard Deviation|
   |temperature_celsius|21.566100|24.100|26.30|92.458965|9.615559|
   |wind_kph|12.959654|11.200|3.60|70.863770|8.418062|
   |pressure_mb|1014.024425|1014.000|1013.00|49.211322|7.015078|
   |precip_mm|0.136675|	0.000|0.00|0.325355|0.570399|
   |humidity|66.179440|71.000|94.00|577.142071|24.023781|
   |cloud|40.036884|31.000|0.00|1161.979927|34.087827|
   |feels_like_celsius|22.455924|25.300|24.60|132.158749|11.496032|
   |visibility_km|9.516108|10.000|10.00|7.150968|2.674129|
   |uv_index|3.430491|2.100|0.00|12.703395|3.564182|
   |gust_kph|18.289470|15.500|10.80|126.467673|11.245785|
   |air_quality_Carbon_Monoxide|475.327953|302.850|217.00|608187.423778|779.863721|
   |air_quality_Ozone|58.849419|56.000|51.00|966.932293|31.095535|
   |air_quality_Nitrogen_dioxide|15.234244|5.500|0.00|587.048315|24.229080|
   |air_quality_PM2.5|24.558451|14.245|0.50|1421.511537|37.702938|
   |air_quality_PM10|49.175345|20.250|12.95|22925.464586|151.411573|
- ## Data Visulization
- **Univariate Analysis**
- **Objective:** To analyze the distribution and variability of temperature across the dataset.
- **Plot Summary:** Analyzes the frequency and density spread of ambient temperatures across dataset.
 <img width="922" height="494" alt="image" src="https://github.com/user-attachments/assets/240c773d-e790-4a92-9b94-83a25892fb44" />
 - **Key Insights**
 - The histogram shows a roughly bell-shaped distribution, indicating that most temperature readings are concentrated around a central range.
 - The highest frequency of observations is between approximately 25°C and 30°C, suggesting that moderate-to-warm temperatures are more common in the dataset.
 - The temperature values range from approximately -30°C to 50°C, reflecting the dataset's coverage of diverse climatic conditions across different countries and locations.
 - Overall, the distribution suggests that typical global temperature observations are concentrated around moderate-to-warm conditions, while extreme temperatures are relatively uncommon.	
 






