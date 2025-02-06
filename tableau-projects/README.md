# Tableau Projects - Introduction  
This section contains my Tableau projects, developed to gain hands-on experience with basic functionalities. Each project focuses on exploring and visualizing datasets to identify trends, patterns, and insights. Through these exercises, I have practiced key Tableau features such as data connections, calculated fields, filters, and interactive dashboards.  

These projects represent my initial approach to data analysis and visualization, and I'm working to further develop my skills over time. 

[Here](https://public.tableau.com/app/profile/davide.mantica/vizzes) you can find my Tableau page.


## Employee Retention Analysis


![Employee Retention Analysis](https://github.com/dmantica5/davide-mantica/blob/main/tableau-projects/Immagine.png?raw=true)


This project analyzes employee retention using various factors such as salary level, department, work accidents, promotions, satisfaction level, and performance evaluations.
The dataset contains information on employees who stayed with or left the company, allowing us to explore key patterns affecting retention.

Key Insights:
 - The majority of employees stayed with the company (83.04%), while 16.66% left.
 - Sales is the department with the highest number of employees.
 - Most employees have a medium salary level, while fewer have a high salary.
 - Promotions in the last 5 years were rare.
 - Employees with work accidents seem to be a smaller proportion of the workforce.
 - Employee satisfaction and evaluation scores vary significantly, impacting retention.

The visualizations were created to identify trends and potential factors contributing to employee turnover.


## Weekly Sales Analysis of Walmart (2010-2012)
![<img src="tableau-projects/Dashboard 1.png" width="500">](https://raw.githubusercontent.com/dmantica5/davide-mantica/refs/heads/main/Dashboard%201.png)
### Introduction 
This project started from a raw Excel dataset containing only numerical values with minimal context—no column names, no data types defined, and no clear indications of missing or anomalous data. To transform this into a structured and meaningful analysis, I conducted a sort of Exploratory Data Analysis (EDA), cleaned and preprocessed the dataset, and then created a dynamic Tableau dashboard to extract business insights.  

---

### 1. Data Cleaning

#### Date Handling  
The `Date` column was originally formatted as a string (`DD-MM-YYYY`). It was converted into a proper datetime format to enable accurate time-series analysis in Tableau.  

#### Missing Values and Duplicates  
A check was performed to detect missing values in all columns. No missing values were found, so no imputation techniques were needed.  
The dataset was also checked for duplicate rows, but no duplicates were present.  

---

### 2. Outlier Treatment
Several columns contained extreme values that could skew the analysis, including:  
- `Weekly_Sales`, with unusually high or low values  
- `Temperature`, with extreme fluctuations  
- `Unemployment`, with significant variations  

To detect and remove outliers, the **Interquartile Range (IQR)** method was applied. The first quartile (Q1) and third quartile (Q3) were calculated, and data points falling outside the range `[Q1 - 1.5*IQR, Q3 + 1.5*IQR]` were removed.  

---

### 3. Final Formatting
- Column names were standardized by removing spaces and special characters to ensure consistency in Tableau.  
- Measurement scales were reviewed to maintain accuracy in visualizations.  

---

### 4. Analysis in Tableau
After data cleaning, I built an interactive Tableau dashboard to make insights more accessible and visually engaging. The dashboard includes:
- Time-series analysis of weekly sales trends over three years.
- Correlation analysis between unemployment, temperature, and sales.
- Seasonality insights to detect high-revenue periods.
- Anomaly detection for unexpected dips or spikes in sales.

---

### 5. Next steps and potential improvements
- **Advanced Predictive Modeling**: Implementing a machine learning model (e.g., ARIMA, LSTM, or XGBoost) to forecast future sales trends.
- **Deeper Customer Insights**: Integrating demographic or customer segmentation data to analyze spending behaviors across different groups.
- **Geospatial Analysis**: Mapping sales performance across different store locations to optimize regional strategies.

This project highlights how raw, unstructured data can be transformed into actionable business intelligence through rigorous data preprocessing, statistical analysis, and data visualization.  


## Global CO2 Emissions

![globalco2emissions](https://github.com/dmantica5/davide-mantica/blob/main/Sheet%201.png?raw=true)

This project demonstrates a data visualization created in Tableau, using a dataset on CO2 emissions across various countries and regions. The goal of the visualization is to display the amount of CO2 emissions per country and region, as well as CO2 emissions per capita, using different chart types for enhanced insight.

### Dataset Overview:
The dataset includes information on CO2 emissions (measured in kilotons) and CO2 emissions per capita across multiple countries and regions. It covers various geographic dimensions such as countries and regions like East Asia & Pacific, Europe & Central Asia, and others.

### Key Features of the Visualization:
- CO2 Emissions per Country: A map that uses point sizes to represent the CO2 emissions by country, with larger dots indicating higher emissions.
- CO2 Emissions per Capita by Region: A breakdown of CO2 emissions per capita across different regions, displayed on a world map with multiple charts for each region.
- Customization Options: The chart allows further customization through the use of color, size, and label options to better represent the data. The color is based on the amount of CO2 (kt), with a color gradient to 
  highlight the scale of emissions.
- Interactive Features: Users can interact with the visualization by hovering over points for detailed information about each country or region’s CO2 emissions.

### Tableau Tools and Features Used:
- Data Connection: Connected the CO2 dataset to Tableau and imported it as the data source.
- Geographic Dimensions: Utilized the geographic dimension (Country Name) to generate a map visualization of CO2 emissions.
- Measure Aggregation: Used CO2 (kt) and CO2 per capita as the key measures to aggregate and visualize the data.
- Customization: Adjusted color, size, and labels to make the data more intuitive and visually appealing.

### Insights:
This chart provides a visual representation of the global distribution of CO2 emissions, highlighting the countries and regions that contribute most significantly to global emissions. It also helps identify regions with high CO2 emissions per capita, offering insights into the carbon intensity of different areas.

This visualization is an essential tool for understanding the global CO2 emission patterns and can be further refined to assess the impact of various countries' policies on emission reduction.


# World Happiness 

[worldhappiness](https://github.com/dmantica5/davide-mantica/blob/main/Foglio%202%20(1).png?raw=true)

## Data Collection and Preparation
- I downloaded a dataset from Kaggle containing the World Happiness Score for various countries.
- I examined and cleaned the data, checking for missing values and correcting any inconsistencies in country names to ensure proper geographical mapping.

## Importing into Tableau and Geographic Mapping
- I uploaded the dataset into Tableau and verified that the data was correctly recognized.
- I used the country field to create a geographic visualization.
- I assigned the Happiness Score to each country, using a color scale to highlight differences in happiness levels:
Blue for higher scores.
Green for lower scores.

## Customizing the Map
- I configured the geographic layer in Tableau using Mapbox and OSM for better visual rendering.
- I added labels displaying the Happiness Score directly on the map.
- I included a color bar legend to enhance readability.

## Interactivity and Optimization
- I made the map interactive, allowing users hover over countries to see detailed information, zoom and navigate across different regions.
- I tested the visualization to ensure that the data was accurate and easy to interpret.

## Although the visualization is functional, there are several ways to improve it:
Enhancing Data Accuracy:
- Incorporate additional metrics such as GDP per capita, life expectancy, and social support to provide more context.
- Cross-check the dataset with other sources to ensure the latest available data is used.

Incorporating Storytelling Elements:
- Add annotations to highlight key insights, such as the happiest and least happy regions.
- Create an accompanying dashboard with charts to analyze factors influencing happiness scores.

Adding Filtering Options:
- Implement filters to compare happiness scores by region, income level, or population size.
- Allow users to select specific years (if historical data is available).
