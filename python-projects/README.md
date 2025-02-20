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

![image](https://github.com/user-attachments/assets/2129aacc-8e6c-4a9c-bf6b-2a2e4140128b)


Then, I loaded the dataset

![image](https://github.com/user-attachments/assets/be6df291-dbbe-47a6-b883-4413cfa87dd7)


STEP 2: EDA (Exploratory Data Analysis)

In the second step, during the EDA process, I analyzed the variables and cleaned the dataset.

![image](https://github.com/user-attachments/assets/1c4c7ca8-7e75-487e-83ba-b3961115cfda)
![image](https://github.com/user-attachments/assets/59978438-f3b9-4bd2-a9c7-7774a068db1b)

I renamed the columns for standardization.

![image](https://github.com/user-attachments/assets/6cb9c5fb-8edc-4733-8bc7-cc327a5c53be)
![image](https://github.com/user-attachments/assets/6b4900ee-f23e-4e79-b0ed-fee22a406f6b)

I checked for missing values.

![image](https://github.com/user-attachments/assets/b9fbc55a-9170-4215-8d30-05459ba2c6a2)

The analysis did not reveal any missing values.

I checked for duplicates.

![image](https://github.com/user-attachments/assets/70f6aee1-245c-430a-aa99-f7d8d1669a53)

The analysis revealed 3,008 duplicate rows, accounting for nearly 20% of the dataset.

I inspected some of the duplicate rows.

![Image](https://github.com/user-attachments/assets/32f39c16-5506-41b6-8043-2408f3dbfb58)

By examining the first five duplicate rows in the dataframe and considering the numerous numerical columns, it is highly unlikely that two employees provided exactly the same responses for every column. Since individuals have different experiences, it is improbable that they would have identical work histories. Therefore, it is reasonable to assume that these duplicate rows are errors or accidental duplications rather than distinct entries. For this reason, they should be removed.

![Image](https://github.com/user-attachments/assets/f36d69a1-fd42-4160-b214-ed8f0a7781aa)

I check for outliers. Understanding if there are outliers in the company tenure could provide crucial information about employee stability within the organization and the likelihood of attrition.

![Image](https://github.com/user-attachments/assets/9888d073-2a04-43b2-b07e-a5fecf473421)

The boxplot above indicates the presence of outliers in the tenure variable. It would be useful to check how many rows in the dataset contain anomalous values in the tenure column.

![Image](https://github.com/user-attachments/assets/af04580e-179e-40e0-a430-625521d222ec)

Based on the calculation, values outside the range of 1.5 to 5.5 are considered outliers, totaling 824 rows.

### ANALYZE

The analysis phase involves collecting, preparing, and examining all the data for the project.

STEP 1: Continuing the EDA

I begin the analysis phase by trying to understand how many employees have left and what percentage they represent.

![Image](https://github.com/user-attachments/assets/7334dd3e-b30d-47e9-8048-2f8886d74228)

From the analysis, employees who left represent approximately 16% of the total.

STEP 2: Data Visualization
In this phase, I create histograms based on the variables that might impact the analysis. I build a histogram to show the distributions of average monthly hours for the number of projects, comparing the distributions of employees who stayed with those who left. This can help understand if there is a correlation between dissatisfaction and working hours.

![image](https://github.com/user-attachments/assets/389f6562-6028-4acf-8c1f-3613dfd67ba7)

It may be natural for people working on more projects to also work more hours. This appears to be the case here, with the average hours for each group (those who stayed and those who left) increasing with the number of projects worked on. However, a few things stand out in this graph. There are two groups of employees who left the company:

•	(A) Those who worked significantly fewer hours than their colleagues with the same number of projects.

•	(B) Those who worked much more.

For those in group A, it's possible that they were laid off. It's also possible that this group includes employees who had already given their notice and were assigned fewer hours as they were about to leave the company.
For those in group B, it is reasonable to deduce that they likely resigned. These individuals probably contributed a lot to the projects they worked on; they may have been the top contributors.
Everyone who worked on seven projects left the company. The optimal number of projects for employees to work on seems to be 3–4, as the ratio of leavers to stayers is very low for these cohorts.
Assuming a 40-hour workweek and two weeks of vacation per year, the average number of working hours per month for employees working Monday to Friday is= 50 weeks * 40 hours per week / 12 months = 166,67 hours/month. This means that, aside from employees working on two projects, every group—even those who stayed—worked significantly more hours than this. It can also be confirmed that all employees with seven projects left, as shown in the analysis.

![image](https://github.com/user-attachments/assets/7be55807-787d-4597-bb68-ded71ca85edf)

Then, I examine the relationship between working hours and employee satisfaction to see if any significant patterns emerge.

![image](https://github.com/user-attachments/assets/2594137c-e8e8-416e-ab50-350de880b5fd)

The scatterplot above shows that there was a consistent group of employees who worked around 240-315 hours per month. 315 hours per month equals over 75 hours a week for an entire year. This is likely related to the fact that their satisfaction levels were close to zero. The graph also shows another group of people who left the company, those with more normal working hours. However, their satisfaction was only about 0.4. It is difficult to speculate on why they might have left. It's possible that they felt pressured to work more, considering many of their colleagues worked longer hours. That pressure might have lowered their satisfaction levels. Finally, there is a group that worked about 210-280 hours per month, and their satisfaction levels ranged from 0.7 to 0.9. The unusual shape of the distributions is indicative of data manipulation or synthetic data.

Another interesting representation can be depicted by the relationship between tenure at the company and satisfaction.

![image](https://github.com/user-attachments/assets/4709c8c6-85c8-4b26-89ae-a020e81e248b)

Employees who left the company fall into two general categories: dissatisfied employees with shorter tenure and very satisfied employees with average tenure. Employees with four years of tenure who left seem to have unusually low satisfaction levels. It is worth investigating any changes in company policy that may have specifically affected people after four years, if possible. Employees with longer tenure did not leave the company. Their satisfaction levels aligned with those of newer employees who stayed. The histogram shows that there are relatively few employees with longer tenure. It is possible that they are higher-ranked, better-paid employees.
For a more complete view, I calculate the mean and median for employees who left and those who stayed.

![image](https://github.com/user-attachments/assets/8b144909-7154-418c-8e1d-0afc1d5bc781)

As expected, the average and median satisfaction scores of employees who left are lower than those of employees who stayed. However, what is interesting to note is that among the employees who stayed, the average satisfaction score appears to be slightly below the median score. This suggests that even though most of the remaining employees are satisfied, there is still a significant proportion of employees with lower satisfaction levels.

I try to verify if the main cause lies in salary by correlating it with different levels of company tenure.

![image](https://github.com/user-attachments/assets/4ea89e04-137c-4427-9a42-99cc79ae6f6e)

According to the analyzed graphs, it doesn't appear that employees with longer tenure receive higher salaries more frequently than other employees. In other words, there is no clear relationship between the time spent in the company and the employees' compensation level.

For the next analysis, I check the correlation between working hours and employee ratings.

![image](https://github.com/user-attachments/assets/f28df0e6-5df7-483a-8d8f-05143cb29a96)

From the graph, it can be observed that high ratings can be achieved by working fewer than 140 hours, but most employees earn them by working between 150 and 280 hours. Therefore, there is a correlation between working hours and ratings. Nonetheless, most employees work well beyond 167 hours per month.

At this point, I examine employee promotions to confirm the hypothesis.

![image](https://github.com/user-attachments/assets/9cd6d9d7-8648-4258-b882-f47e93a40787)

The graph above shows the following:

• Since there is a very limited number of employees who have been promoted in the last five years and then left the company, it seems that promotion has been an effective retention factor.

• There are very few employees who worked the highest number of hours and were also promoted, suggesting that overtime work may not have been recognized or rewarded with a promotion.

• All employees who left the company without a promotion worked the highest number of hours, indicating that workload may have been a significant factor in their decision to leave.

At this point, I will check the distribution of employees across the various departments.

![image](https://github.com/user-attachments/assets/25094598-7cfe-46f6-aa6c-adfc5445cd2d)
![image](https://github.com/user-attachments/assets/ef3e74e8-d277-400f-a996-67372eef5cdc)

There do not appear to be any proportional differences between employees who stayed and those who left the company.

Finally, I will check for strong correlations between the variables to identify any significant relationships or patterns that could help better understand the data and guide future decisions or actions.

![image](https://github.com/user-attachments/assets/cb03d67c-6c1b-42e4-ba8c-b3df6d59e488)

The correlation map confirms that the number of projects, monthly hours, and evaluation scores all have a certain positive correlation with each other, while an employee leaving the company is negatively correlated with their satisfaction level.


INSIGHT: It appears that employees are leaving the company due to poor management. Attrition is linked to longer working hours, a high number of projects, and generally lower satisfaction levels. It can be frustrating to work long hours without receiving promotions or good evaluation scores. There is a considerable group of employees in this company who are likely exhausted. Additionally, it seems that if an employee has spent more than six years in the company, they tend to stay.

### CONSTRUCT

In the Construct Stage of the PACE process, the most appropriate models for data analysis are determined, and their actual construction takes place. Subsequently, the model assumptions are checked, and the results are evaluated to determine how well the model fits the data.

1.	IDENTIFYING THE TYPE OF PREDICTION:
The objective is to predict whether an employee leaves the company, which is a categorical output variable. Therefore, this task involves classification. More specifically, it is a binary classification since the output variable "left" can be either 1 (indicating the employee has left) or 0 (indicating the employee has not left).

2.	IDENTIFYING THE MODEL:
Since the variable to be predicted (whether an employee leaves the company) is categorical, a logistic regression model or a machine learning model based on decision trees can be built.

APPROACH A: LOGISTIC REGRESSION MODEL
Before splitting the data, non-numeric variables need to be encoded. There are two: department and salary.

•	Department is a categorical variable, meaning it can be represented using dummy encoding for the model.

•	Salary is also categorical, but it is ordinal. Since there is a hierarchy between categories, it is preferable not to create dummy variables for this column. Instead, the levels should be converted into numerical values, ranging from 0 to 2.

![image](https://github.com/user-attachments/assets/2be31346-ef95-4389-a721-f9d047e97288)

I create a heatmap to visualize how the variables are correlated, focusing on the most relevant ones for analysis.

![image](https://github.com/user-attachments/assets/81b0036e-6e36-4455-877c-b549a3e3a9f7)

I create a bar chart to visualize the number of employees per department, comparing those who left the company with those who stayed.

![image](https://github.com/user-attachments/assets/dbfa0659-fabc-4dc7-befb-ada3068f6413)

Since logistic regression is quite sensitive to outliers, it is a good idea at this stage to remove the outliers in the "tenure" column that were previously identified.

![image](https://github.com/user-attachments/assets/d49f0f6a-872d-4d63-86ce-acbd39cb561b)

I isolate the output variable, which is the variable we want the model to predict.

![image](https://github.com/user-attachments/assets/88c299f6-89d7-4072-ab61-68a18780aff3)

I select the features I want to use in my model, considering the variables that will help predict the output variable, "left.".

![image](https://github.com/user-attachments/assets/ead080ac-fa2d-44b0-9c1b-754724c019f4)

I split the data into a training set and a test set. I also stratify based on the values in y, as the classes are imbalanced.

![image](https://github.com/user-attachments/assets/7a95d5be-abd4-4e11-8239-5d5ec762d3d3)

I build a logistic regression model by fitting it to the training dataset.

![image](https://github.com/user-attachments/assets/35f0ef82-cf9c-4e7e-a25a-46c7762503fb)

I test the logistic regression model by using it to make predictions on the test set.

![image](https://github.com/user-attachments/assets/c2f5a07d-1cab-48c9-bc2c-c5fb9e831b8c)

I create a confusion matrix to visualize the results of the logistic regression model.

![image](https://github.com/user-attachments/assets/8afae5c5-2ccd-48ed-951d-d08b75683c10)

The top-left quadrant shows the number of true negatives. The top-right quadrant shows the number of false positives. The bottom-left quadrant shows the number of false negatives. The bottom-right quadrant shows the number of true positives.

•	True negatives: The number of people who did not leave and whom the model correctly predicted would not leave.

•	False positives: The number of people who did not leave and whom the model incorrectly predicted would leave.

•	False negatives: The number of people who left and whom the model incorrectly predicted would not leave.

•	True positives: The number of people who left and whom the model correctly predicted would leave.

A perfect model would produce all true negatives and true positives, with no false negatives or false positives.

I also check the class balance in the data.

![image](https://github.com/user-attachments/assets/bc8d5063-642e-4d02-b642-8eb8e425b055)

The data is realistic enough, so we can proceed with the evaluation. I create a classification report that includes precision, recall, F1 score, and accuracy to assess the performance of the logistic regression model.

![image](https://github.com/user-attachments/assets/57b8ccb6-f660-45cb-b98d-28223551bfcc)

The classification report above shows that the logistic regression model achieved a precision of 79%, a recall of 82%, an F1 score of 80% (all weighted averages), and an accuracy of 82%. However, when it comes to predicting employees who leave, the scores are significantly lower.

APPROACH B: DECISION TREES

Let's try the implementation of the decision tree and random forest to check if they are better suited for our classification problem.
First, I isolate the output variable.

![image](https://github.com/user-attachments/assets/c3e2947e-ebec-48f1-9c14-d02d0e8b01ef)

Then, I select the features.

![image](https://github.com/user-attachments/assets/e5bfdbca-44e6-472f-9e8b-2e358ecbfbef)

I split the data into training, validation, and test sets.

![image](https://github.com/user-attachments/assets/09e4c2ab-d447-451e-8e54-0804d6ce47c8)

Decision Tree – Round 1: I build a model based on decision trees as the first attempt for hyperparameter tuning. I use a technique called grid search with cross-validation. In short, I explore different configurations for the decision tree to find the one that works best for the data.

![image](https://github.com/user-attachments/assets/ad7604ed-f86f-4189-9e5a-06a39a122a35)

I fit the decision tree model to the training data.

 ![image](https://github.com/user-attachments/assets/82ba56ad-5f00-4f9e-a7a5-7a79f56a783b)

I identify the optimal values for the decision tree's parameters.

![image](https://github.com/user-attachments/assets/bc36bb82-10d9-41e2-95ad-aadca27c05d9)

I identify the best AUC score achieved by the decision tree model on the training set. The AUC score measures how well a model distinguishes between two different categories, such as "left" and "did not leave" in our case. The higher the AUC score, the better the model is at making this distinction.

![image](https://github.com/user-attachments/assets/c852bca3-6125-4869-bfd4-23383173ab04)

This is a high AUC score, which demonstrates that this model is very good at predicting which employees will leave the company.

Next, I can write a function that will help me extract all the scores from the grid search.

![image](https://github.com/user-attachments/assets/de244d2f-f4dc-47d4-b3c3-ac1d3166f698)

I use the function I just defined to obtain all the scores from the grid search.

![image](https://github.com/user-attachments/assets/bd3c2450-f2c4-4149-b2c8-f2fa36c42904)
 
All these scores obtained from the decision tree model are strong indicators of good model performance. Since decision trees can be vulnerable to overfitting, while random forests avoid overfitting by incorporating multiple trees for predictions, I could now build a random forest model.

Random Forest – Round 1: I build a random forest model and set up a grid search with cross-validation to thoroughly search for the best model parameters.

![image](https://github.com/user-attachments/assets/4e912157-5768-40b2-9f75-a70f95366de4)

Fitto il modello di random forest sui dati di addestramento.

![image](https://github.com/user-attachments/assets/d5fdb173-c020-46f9-a66d-227b203beba1)

I specify the path where to save the training data.

![image](https://github.com/user-attachments/assets/75108e52-f40a-46f0-82db-a9ccec6d5f88)

I define functions to perform model saving (pickling) and to read the model.

![image](https://github.com/user-attachments/assets/4944540f-42b7-4172-85eb-dcfa7fba1da4)

I use these functions to save the model in a pickle file and then read it back.

![image](https://github.com/user-attachments/assets/8e3493a5-9440-4a78-adc8-332fcdde5600)

I identify the best AUC score achieved by the random forest model on the training set.

![image](https://github.com/user-attachments/assets/7b6895f3-78a3-4a90-a5b7-1057e17d759c)

I identify the optimal values for the parameters of the random forest model.

![image](https://github.com/user-attachments/assets/964f9fd2-50d8-4cfc-891d-cae33bdaaf0c)

I gather the evaluation scores on the training set for both the decision tree and random forest models.

![image](https://github.com/user-attachments/assets/1e9fc960-2d8e-4f34-b34c-13ed12ce06c3)

The evaluation scores of the random forest model are better than those of the decision tree model, except for recall (the random forest recall score is approximately 0.001 lower, a negligible amount). This indicates that the random forest model generally outperforms the decision tree model.

Next, I can evaluate the final model on the test set.

I define a function that retrieves all the scores from the model's predictions.

![image](https://github.com/user-attachments/assets/04f57769-742e-4114-bfdc-21270a85050f)

Now, I use the model with the best performance to make predictions on the test set.

![image](https://github.com/user-attachments/assets/7367295f-5cc1-4680-8af8-ba9b5cbefcb3)

The test scores are very similar to the validation scores, which is a positive sign. This indicates that the model is robust. Since this test set was used exclusively for this model, we can be more than confident that the model's performance on these data is representative of how it will perform on unseen new data.

A concern is that our current models may be overly optimistic in their evaluation scores. This could be due to a phenomenon called data leakage, where the model uses information that is detached from reality. For example, the 'satisfaction level' column might not be available for all employees, and the 'average monthly hours' could be influenced by the fact that employees have already decided to leave the company. To improve the models, we could eliminate 'satisfaction level' and create a new feature called 'overload,' which indicates if an employee is working excessive hours. This could help us better predict who will leave the company.

![image](https://github.com/user-attachments/assets/6a2d7fc2-9a23-4ad0-b461-0ed86dba1fc7)

166.67 is approximately the average number of monthly hours for someone working 50 weeks a year, 5 days a week, 8 hours a day. Excessive working could be defined as working more than 175 hours per month on average. To make the "overload" column binary, the column could be redefined using a boolean mask.

![image](https://github.com/user-attachments/assets/a9137d03-7959-4dab-81a2-ae76e3d1978b)

I remove the column 'average_monthly_hours'.

![image](https://github.com/user-attachments/assets/ef0f2172-659d-4efa-97d8-629780a147ca)

Once again, I isolate the input variables and the target variable.

![image](https://github.com/user-attachments/assets/1019f902-5675-4024-b428-c46dd72c1c4a)

I split the data into training and test sets.

![image](https://github.com/user-attachments/assets/07f2936d-cb69-441b-827d-ab09697062bf)

Decision trees – round 2:

![image](https://github.com/user-attachments/assets/fefc602c-22e1-491a-a7b9-8f3f892b399f)

![image](https://github.com/user-attachments/assets/8a648767-071d-49c6-8c2a-02b17d703861)

This model performs very well, even without the satisfaction levels and detailed working hours data.

Next, let's check the other scores.

![image](https://github.com/user-attachments/assets/62676661-3dc9-41df-8daa-2038ea2a4403)

Some of the other scores have decreased. This is normal since fewer features were considered at this stage of the model. However, the scores are still very good.
Random forest – round 2:

![image](https://github.com/user-attachments/assets/5f9b149f-45f4-4668-aa08-88ab26ea3c81)
![image](https://github.com/user-attachments/assets/9b3589c3-2b4f-4e73-b7a0-940b372a5146)
![image](https://github.com/user-attachments/assets/3532bc9a-dc7f-4b38-a098-9706d0a65591)

Once again, the scores have slightly decreased, but the random forest performs better than the decision tree when using AUC as the benchmark metric.
Now let's evaluate the sample model on the test set.

![image](https://github.com/user-attachments/assets/64d820c1-a401-42d9-9426-1d33b775dfc7)

seems to be a stable and performant final model.
Let's plot a confusion matrix to visualize how well it predicts on the test set.

![image](https://github.com/user-attachments/assets/4a67f27f-45cd-4315-a7b9-30a5d892847b)

The model predicts more false positives than false negatives, meaning that some employees may be identified as at risk of leaving when, in reality, they are not. However, it remains a solid model.

For exploratory purposes, let's inspect the splits of the decision tree model and the most important features of the random forest model. Examining the decision tree splits provides a more detailed understanding of how the model makes its decisions, while identifying the most important features in the random forest offers insights into which variables most influence the model's predictions.

![image](https://github.com/user-attachments/assets/a09698a3-4fc6-4761-bc67-bd5d3e8eb6fe)

It is also possible to visualize the feature importance from decision trees.

![image](https://github.com/user-attachments/assets/947732b2-54f7-4d7e-8fa7-aaea87cbee34)

After obtaining the feature importance from the decision tree, you can create a bar chart to visualize them.

![image](https://github.com/user-attachments/assets/3cb9c46e-163e-403b-88bd-fc3551bd69f1)

The bar chart above shows that in this decision tree model, "last_evaluation", "number_project", tenure, and "overworked" have the highest importance, in that order. These variables are the most used in predicting the output variable, left.

Now, let's plot the feature importance for the random forest model.
  
![image](https://github.com/user-attachments/assets/36d4bdd2-20b5-4462-84e8-d4f8f0c31a9d)

The chart above shows that in this random forest model, "last_evaluation," "number_project," "tenure," and "overworked" have the highest importance, in this order. These variables are the most useful in predicting the output variable, "left," and they are the same ones used by the decision tree model.

### EXECUTE

The execution phase serves to put into practice the results obtained during the previous stages of the process. In this phase, the model's performance is interpreted, and the results are analyzed to extract useful insights. Then, steps and actions are shared with stakeholders to implement the recommendations derived from the analysis of data and models. Essentially, this phase aims to translate the model's results into concrete actions that can lead to improvements or informed decisions within the specific field where the study was conducted.

MODEL RESULTS 

Logistic Regression: The logistic regression model achieved an accuracy of 80%, recall of 83%, an F1 score of 80% (all weighted averages), and an accuracy of 83% on the test set.

Tree-based Models: After performing feature engineering, the decision tree model achieved an AUC of 93.8%, precision of 87.0%, recall of 90.4%, F1 score of 88.7%, and accuracy of 96.2% on the test set. The random forest model slightly outperformed the decision tree model.

Conclusions, Recommendations, Next Steps: The models and the feature importance extracted from the models confirm that the company’s employees are overloaded with work. To retain employees, the following recommendations could be presented to the stakeholders:

•	Limit the number of projects employees can work on.

•	Consider promoting employees who have been with the company for at least four years, or conduct further investigations into why employees with four years of tenure are so dissatisfied.

•	Reward employees for working extra hours, or do not require them to do so.

•	If employees are unaware of company policies regarding overtime, inform them. If expectations regarding workload and time off are not explicit, make them clear.

•	Hold discussions at the company level and within teams to understand and address the company’s work culture across all sectors and specific contexts.

•	High performance ratings should not be reserved for employees working more than 200 hours per month. Consider implementing a proportional scale to reward employees who contribute more/put in more effort.



























  
