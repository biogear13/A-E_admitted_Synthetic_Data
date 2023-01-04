# Analysis of Accident and Emergency Department Admissions
## by Generoso Roberto

> This is an analysis of A&E admissions in a NHS provider from 2014-03-23 to 2018-03-22

## Dataset

> The dataset used in this exploratory analysis is the A&E Synthetic Data which created as a result of an NHS England pilot project to share more data without sacrifising the privacy of patients.

> The database could be accessed with this link: https://data.england.nhs.uk/dataset/a-e-synthetic-data

> The entire database is 4.2gb long and includes A&E consults that led to both admissions and non-admissions in 200+ providers.

> I decided to focus my analysis on just the admissions of the provider with the highest total number of admissions.

> The notebook get_AnE_Provider_Admission_Data.ipynb shows the code how I filter the original dataset to be used in this analysis. The resulting data can be found in the AnE_Synthetic_Data_Provider_Admission.csv

> The following are the descriptions of the columns used:
    * IMD_Decile_From_LSOA - measure of deprivation. A score of 1 indicates the entry comes from the 10% most deprived area in England
    * Age_Band - The interval of the age of the patient
    * Sex - Coded in 1 and 2 to represent the two sexes
    * AE_Arrive_Date - The date the patient arrived at the A&E provider
    * AE_Arrive_HourOfDay - The interval of what time the patient arrived at the A&E
    * AE_Time_Mins - Total number of minutes the patient stayed in the A&E
    * AE_HRG - Code for the health reference group
    * AE_Num_Diagnoses - Number of diagnoses the patient have in the A&E
    * AE_Num_Investigations - Number of investigations done to the patient
    * AE_Num_Treatments - Number of treatments done to the patient
    * AE_Arrival_Mode - Code for the mode by which  patient arrived
    * Provider_Patient_Distance_Miles - Distance from the patient place of origin to the provider in miles
    * Admission_Method - Code for the method how the patient was admitted
    * ICD10_Chapter_Code - International classification of disease chapter code
    * Treatment_Function_Code - The treatment function under which the patient is treated.
    * Length_Of_Stay_Days - The number of days the patient was admitted

Provide basic information about your dataset in this section. If you selected your own dataset, make sure you note the source of your data and summarize any data wrangling steps that you performed before you started your exploration.


## Summary of Findings

> Summarize all of your findings from your exploration here, whether you plan on bringing them into your explanatory presentation or not.


## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.