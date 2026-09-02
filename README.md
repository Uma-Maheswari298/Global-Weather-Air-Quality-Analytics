
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
Column Name	Data Type	Description
country	object	The name of the country where the weather and air-quality observation was recorded.
Location_name	object	
The name of the city or specific location where the observation was recorded.

latitude	float64	The north–south geographic coordinate of the location, measured in degrees.
longitude	float64	The east–west geographic coordinate of the location, measured in degrees.
time/zone	object	The local time zone of the recorded location.
last_updated	object	The date and time when the weather and air-quality data was last updated.
temperature_celsius	float64	The actual air temperature at a specific location and time, measured in degrees Celsius (°C).
Weather_condition	object	A text description of the observed weather condition, such as Sunny, Cloudy, or Rainy.
wind_kph	float64	The wind speed recorded at the location, measured in kilometres per hour (km/h).
wind_degree	int64	The direction from which the wind is blowing, measured in degrees.
pressure_mb	int64	The atmospheric pressure at the location, measured in millibars (mb).
Precip_mm	float64	The amount of precipitation recorded at a specific location and time, measured in millimetres (mm).
Humidity	int64	The percentage of moisture present in the air at a specific location and time.
cloud	int64	The percentage of the sky covered by clouds.
feels_like_celsius	float64	The perceived temperature experienced by people, measured in degrees Celsius (°C).
visibility_km	float64	The distance at which objects can be clearly seen, measured in kilometres (km).
uv_index	float64	A measure of the intensity of ultraviolet (UV) radiation from the sun.
gust_kph	float64	The maximum or sudden increase in wind speed, measured in kilometres per hour (km/h).
air_quality_Carbon_Monoxide	float64	The concentration of carbon monoxide (CO) in the air, indicating a level of air pollution.
air_quality_Ozone	float64	The concentration of ozone (O₃) present in the air, used as an indicator of air quality.
air_quality_Nitrogen_dioxide	float64	The concentration of nitrogen dioxide (NO₂) in the air, an important air-pollution indicator.
air_quality_PM2.5	float64	The concentration of fine particulate matter with a diameter of 2.5 micrometres or less in the air.
air_quality_PM10	float64	The concentration of particulate matter with a diameter of 10 micrometres or less in the air.
air_quality_us-epa-index	int64	The US EPA Air Quality Index value used to indicate the overall level of air pollution and its potential health impact.



