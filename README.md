Google Advanced Data Analytics Capstone Project: Providing Data-Driven Suggestions for Salifort Motors HR
---
Daniel Poe, 2025-06-24

This is a capstone project that I have completed as part of the [Google Advanced Data Analytics Professional Certificate](https://www.coursera.org/professional-certificates/google-advanced-data-analytics). This certificate builds on data analytics skills and experience to take careers to the next level. It is designed for graduates of the [Google Data Analytics Certificate](https://www.coursera.org/professional-certificates/google-data-analytics) or people with equivalent data analytics experience. This course enables learners to expand their knowledge through practical, hands-on projects that feature Jupyter Notebook, Python, and Tableau. Course participants can learn the following:

- Explore the roles of data professionals within an organization 
- Create data visualizations and apply statistical methods to investigate data
- Build regression and machine learning models to analyze and interpret data
- Communicate insights from data analysis to stakeholders

This project is also available on [Kaggle](https://www.kaggle.com/code/phildanielpoe/google-advanced-data-analytics-capstone-project).

## Background

### About the Company
Salifort Motors is a fictional French-based alternative energy vehicle manufacturer. Its global workforce of over 100,000 employees research, design, construct, validate, and distribute electric, solar, algae, and hydrogen-based vehicles. Salifort’s end-to-end vertical integration model has made it a global leader at the intersection of alternative energy and automobiles.

### Business Case
As a data specialist working for Salifort Motors, I have received the results of a recent employee survey. The senior leadership team has tasked me with analysing the data to come up with ideas for how to increase employee retention. To help with this, they would like me to design a model that predicts whether an employee will leave the company based on their department, number of projects, average monthly hours, and any other data points you deem helpful. 

### Deliverable Value
For this deliverable, I am asked to choose a method to approach this data challenge based on my prior coursework. Select either a regression model or a tree-based machine learning model to predict whether an employee will leave the company.

## Dataset
The employee dataset provided by the HR department came from [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction). The dataset contains 14,999 rows and 10 columns, each row representing self-reported information from various employees.

## Modelling

Since the desired variable to predict (whether an employee leaves the company) is categorical, either a logistic regression model or a tree-based machine learning model could be built. For this project, I have decided to build a tree-based machine learning model.

We will build a random forest model and an XGBoost model for these reasons:

- This dataset contains outliers; a tree-based model is less sensitive to outliers.
- Tree-based models do not require feature scaling.
- This dataset is imbalanced. 83.4% of the dataset contains data of employees who stayed, while only 16.6% of it contains data of employees who left the company.

Since the dataset is imbalanced, F1 scores will be used as the metric instead of accuracy. The F1 score also combines information from precision and recall scores.

### Random Forest Model
![image](https://github.com/user-attachments/assets/ff4fc29b-ef11-446e-aad5-007ce02d25f4)
![image](https://github.com/user-attachments/assets/ea5fd4ae-d2ac-4798-9b78-a2f3a797fa77)

- F1 Score of RF Model: 0.958
- Recall Score of RF model: 0.928
- Precision Score of RF model: 0.989
- Accuracy Score of RF model: 0.986
- AUC Score of RF model: 0.963

### XGBoost Model
![image](https://github.com/user-attachments/assets/b8d9e88f-deeb-428a-87f0-da6c166fcefe)
![image](https://github.com/user-attachments/assets/0a8fb013-4e1d-48d9-8d93-e69749599892)

- F1 Score of XGBoost Model: 0.953
- Recall Score of XGBoost model: 0.928
- Precision Score of XGBoost model: 0.979
- Accuracy Score of XGBoost model: 0.985
- AUC Score of XGBoost Model: 0.962

### Results Summary
- `average_monthly_hours`, `satisfaction_level`, `last_evaluation`, `tenure`, and `number_project` are the most important features for predicting whether an employee will leave or not.
- The random forest model had a higher F1 score than the XGBoost model.

The random forest model was selected as the model to be used for predicting whether an employee will leave the company. Not only does it have a higher F1 score, it also took less time to run.

## Conclusion
The random forest and XGBoost models were built and compared, where the random forest model was selected as the model to be used. The EDA, machine learning models, and feature importances confirmed that employees were indeed overworked.

To retain employees, I would like to present the following recommendations to the stakeholders:

- Limit the number of projects that employees can work on.
- Consider promoting employees who have been with the company for at least four years, or conduct further investigation about why four-year tenured employees are so dissatisfied.
- Either reward employees for working longer hours, or do not require them to do so.
- If employees are not familiar with the company's overtime pay policies, inform them about this. If the expectations around workload and time off are not explicit, make them clear.
- Hold company-wide and team discussions to understand and address the company's work culture, across the board and in specific contexts.
- High evaluation scores should not be reserved for employees who work more than 200 hours/month. Consider a proportionate scale for rewarding employees who contribute more/put in more effort.

Through these recommendations, Salifort Motors can effectively counter employee turnover, enhance employee satisfaction, and cultivate a thriving workforce.
