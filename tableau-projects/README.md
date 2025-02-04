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
![Weekly Sales Analysis of Walmart (2010-2012)](images/Dashboard 1.png)](https://github.com/dmantica5/davide-mantica/blob/main/Dashboard%201.png)
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
