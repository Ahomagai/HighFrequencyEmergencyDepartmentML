# HighFrequencyEmergencyDepartmentML
Predicting high frequency users of an emergency department using the MIMIC-III clinical dataset. 


## In construction 

## Project Description 
Noteworthy are the small subset of patients, commonly referred to as high-frequency users, who make up only 4.5-8% of all ED patients, yet account for a staggering 21-30% of visits (LaCalle & Rabin, 2010). High-frequency users are known to have higher rates of mortality, hospital admissions, and outpatient visits compared to their non-frequent counterparts (Moe et al., 2016). This population significantly contributes to ED overcrowding, disproportionate resource utilization, and are affected by adverse outcomes (Hunt et al., 2006; Moe et al., 2016). Therefore, interventions aimed at this group could potentially decrease ED visits and improve outcomes from an individual patient and health system perspective.


The ultimate aim was to leverage the predictive capability of machine learning models and explainability of these models to facilitate early decision-making and disposition planning for high-frequency ED users. By identifying these individuals early and implementing proactive interventions, we hope to reduce ED visits, improve care quality, and enhance ED metrics. Understanding the characteristics of frequent ED users is fundamental to decreasing ED overcrowding and assisting these patients.


## Lessons Learned 
As this was my first dive into ML and creating an end-to-end pipeline, a LOT was learned along the way. Especially as getting proper access to the entire MIMIC-III dataset required learning PostGreSQL and understanding how to do SQL queries to first select my dataset. 
The most important lession was that doing the front-end work even though it may take a while is entirely worth it. This means having a proper research question, feature selection/engineering, and understanding what it is you're really trying to do at the end of the project is essential to lay out at the start. As this was an evloving project, changes in research questions and more debate/discussion about specific features made the data extraction repetitive (which wasn't a bad thing, just time consuming), although I do recognize that it is the nature of solutions to evolve as you learn more about potential solutions. Sometimes solutions evolve and you have to pivot as you go.

Had I more time and space (in this case I'm referring to literal disk space) I would have loved to do this same analysis on a much (MUCH) bigger sample of data, this demo really is a short snippet of what really should be analyzed and althought I have a decent training set for the purposes to showcase a ML pipeline, for actual understanding and production, a bigger dataset should be used. 

### Data Pipeline, Cohort Selection & Feature Table 
The following figures show the data pipeline, cohort selection, and feature table with descriptions that were used in the project. 

#### Pipeline 
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/Pipeline.png)

#### Cohort Selection
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/Cohort_Selection_Schema.png)

#### Feature Table 
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/Feature%20Table.PNG)



## Highlights 
#### Initial XGBOOST Model Performance without hyperparameter optimization

With an mean ROC of 0.72, it's unsurprising that the model has relatively poor performance, especially for the main variables of precision, recall, and F1 Score. 
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/initial_ROC.png)

              precision    recall  f1-score   support

           0       0.90      0.95      0.92     10658
           1       0.32      0.19      0.24      1409

    accuracy                           0.86     12067
   macro avg       0.61      0.57      0.58     12067
weighted avg       0.83      0.86      0.84     12067




#### XGBOOST Model Performance with manual grid search 
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/ROC.png)

#### Feature Importance of Manual Grid Search XGBOOST model 
![Alt text](https://github.com/Ahomagai/HighFrequencyEmergencyDepartmentML/blob/main/img/Feature_importance.png)



#### More highlights to come as I finalize them 


### References 
Hunt, K. A., Weber, E. J., Showstack, J. A., Colby, D. C., & Callaham, M. L. (2006). Characteristics of frequent users of emergency departments. Annals of Emergency Medicine, 48(1), 1–8. https://doi.org/10.1016/j.annemergmed.2005.12.030
LaCalle, E., & Rabin, E. (2010). Frequent users of emergency departments: The myths, the data, and the policy implications. Annals of Emergency Medicine, 56(1), 42–48. https://doi.org/10.1016/j.annemergmed.2010.01.032
Moe, J., Kirkland, S., Ospina, M. B., Campbell, S., Long, R., Davidson, A., Duke, P., Tamura, T., Trahan, L., & Rowe, B. H. (2016). Mortality, admission rates and outpatient use among frequent users of emergency departments: A systematic review. Emergency Medicine Journal: EMJ, 33(3), 230–236. https://doi.org/10.1136/emermed-2014-204496


