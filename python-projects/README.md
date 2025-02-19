# Employee Attrition Analysis – Salifort Motors

This repository contains the Capstone Project from the Google Data Analytics course, focused on analyzing employee satisfaction and predicting attrition for the fictional company Salifort Motors.

## Objective
The project aims to identify the key factors influencing employees' decisions to leave the company using data analysis and machine learning. A predictive model was developed in Jupyter Notebook to estimate with significant accuracy which employees are most likely to leave.

## Approach
- Data exploration and cleaning based on HR records
- Trend analysis to identify the main causes of attrition
- Development of a predictive model to estimate resignation risks
- Interpretation of results and recommendations to reduce turnover

## Impact
The insights from this analysis provide strategic value to Salifort Motors, enabling proactive interventions to retain key employees and optimize costs associated with turnover.

### Introduction
The project follows the PACE framework.

The PACE framework (Plan, Analyze, Construct, Execute) offers a structured yet flexible methodology for conducting data analysis projects. By breaking down the process into distinct stages, PACE ensures a clear workflow that supports efficiency, adaptability, and effective decision-making.



![](https://github.com/dmantica5/davide-mantica/blob/main/pace-stage.jpg?raw=true)



Plan: Establish the foundation by defining objectives, outlining project scope, and structuring workflows. This phase sets expectations and aligns goals with stakeholder needs.

Analyze: Prepare and refine data through cleaning, formatting, and transformation. This step ensures that data is structured and ready for in-depth exploration.

Construct: Develop models and analytical approaches to extract meaningful insights. Whether using statistical methods or machine learning, this phase focuses on uncovering patterns within the data.

Execute: Present findings, integrate feedback, and refine the analysis as necessary. Clear communication and iteration ensure that results are actionable and impactful.

PACE operates as an iterative cycle rather than a linear process, allowing movement between stages as needed. This adaptability makes it an effective framework for tackling complex data challenges while maintaining structure and clarity.

### PLAN
The planning phase is where the project's purpose is defined, and the steps required to complete it are developed.

The capstone project of the course involved a data analysis project for the fictional company Salifort Motors. The challenge focused on improving employee satisfaction within the company. The task was to better understand the reasons why employees were leaving and to propose data-driven solutions based on information collected by the HR department.

Through data analysis, I aimed to identify the key factors influencing employees' decisions to leave the company. Using data analysis and machine learning techniques, I was guided through the development of a predictive model in Jupyter Notebook, capable of accurately forecasting whether and when an employee is likely to leave.

This analysis and the predictive model I developed offer a strategic opportunity for Salifort Motors. The company can leverage these insights to take proactive measures, retain key employees, and reduce turnover-related costs such as recruitment and training.

STEP 1: Importing

First, I imported the necessary packages.

![](https://github.com/dmantica5/davide-mantica/blob/main/img.png?raw=true)

Then, I loaded the dataset

![](https://github.com/dmantica5/davide-mantica/blob/main/img2.png?raw=true)

STEP 2: EDA (Exploratory Data Analysis)
In the second step, during the EDA process, I analyzed the variables and cleaned the dataset.

![](https://github.com/dmantica5/davide-mantica/blob/main/img3.png?raw=true)
![](https://github.com/dmantica5/davide-mantica/blob/main/img4.png?raw=true)

I renamed the columns for standardization.

![](https://github.com/dmantica5/davide-mantica/blob/main/img5.png?raw=true)

I checked for missing values.

![](https://github.com/dmantica5/davide-mantica/blob/main/img6.png?raw=true)

The analysis did not reveal any missing values.

I checked for duplicates.

![](https://github.com/dmantica5/davide-mantica/blob/main/img7.png?raw=true)

The analysis revealed 3,008 duplicate rows, accounting for nearly 20% of the dataset.

I inspected some of the duplicate rows.

![Image](https://github.com/user-attachments/assets/32f39c16-5506-41b6-8043-2408f3dbfb58)

By examining the first five duplicate rows in the dataframe and considering the numerous numerical columns, it is highly unlikely that two employees provided exactly the same responses for every column. Since individuals have different experiences, it is improbable that they would have identical work histories. Therefore, it is reasonable to assume that these duplicate rows are errors or accidental duplications rather than distinct entries. For this reason, they should be removed.

![Image](https://github.com/user-attachments/assets/f36d69a1-fd42-4160-b214-ed8f0a7781aa)






