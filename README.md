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
>    * IMD_Decile_From_LSOA - measure of deprivation. A score of 1 indicates the entry comes from the 10% most deprived area in England
>    * Age_Band - The interval of the age of the patient
>    * Sex - Coded in 1 and 2 to represent the two sexes
>    * AE_Arrive_Date - The date the patient arrived at the A&E provider
>    * AE_Arrive_HourOfDay - The interval of what time the patient arrived at the A&E
>    * AE_Time_Mins - Total number of minutes the patient stayed in the A&E
>    * AE_HRG - Code for the health reference group
>    * AE_Num_Diagnoses - Number of diagnoses the patient have in the A&E
>    * AE_Num_Investigations - Number of investigations done to the patient
?    * AE_Num_Treatments - Number of treatments done to the patient
>    * AE_Arrival_Mode - Code for the mode by which  patient arrived
>    * Provider_Patient_Distance_Miles - Distance from the patient place of origin to the provider in miles
>    * Admission_Method - Code for the method how the patient was admitted
>    * ICD10_Chapter_Code - International classification of disease chapter code
>    * Treatment_Function_Code - The treatment function under which the patient is treated.
>    * Length_Of_Stay_Days - The number of days the patient was admitted

> The following were the data wrangling that was done
>    * Created a Year_Month column from AE_Arrive_Date
>    * Made the following columns into a categorical datatype
>        * `Sex`
>        * `AE_Arrival_Mode`
>        * `Admission_Method`
>        * `ICD10_Chapter_Code`
>        * `Treatment_Function_Code`
>    * The following columns are ordered categorical datatypes
>        * `IMD_Decile_From_LSOA`
>        * `Age_Band`
>        * `AE_Arrive_HourOfDay`
>        * `AE_HRG`
>    * Removed rows that have missing entries
# Summary of Findings
> * Univariate analysis
>       * The distribution of time spent in the emergency department (A&E) is positively skewed, with most patients staying for 240 minutes. The majority of patients have no diagnosis, there is a peak in the number of investigations at 10 and 1, and treatments follow a normal distribution with 1 being the highest. The majority of patients are from poorer areas, are aged 25-85, are female, and are located one mile from the provider. The median daily admission rate has increased from 2014 to 2018, with the lowest rate in August and the highest in March. Fridays have the lowest admission rate during the week, while Saturdays have the highest. The majority of patients come between 9:00 AM and 8:00 PM. There is a nearly equal split between patients arriving via ambulance and private transportation, and 96% are admitted to the provider's emergency department. Most patients need low healthcare resources, and over a quarter need high resources. The majority have diagnoses that cannot be categorized into an ICD10 chapter, are treated by the emergency medicine service, and spend less than a day admitted.
> * Bivariate analysis
>       * Time spent in the emergency department (A&E) is positively correlated with the number of investigations, older age group, night admissions, use of ambulances and low healthcare resource needs. It is negatively correlated with admissions arriving between 9:00 AM and 12:00 PM, admissions via GP, needing high healthcare resource or not needing healthcare resource, having a digestive system condition and being treated by general surgery and pediatric service. Additionally, it was found that the number of investigations is directly related to the number of treatments and healthcare resource needs. Using an ambulance is positively correlated with age and admissions during early morning hours.
> * Multivariate analysis
>       * The number of investigations a patient undergoes in the emergency department (A&E) directly impacts the amount of time they spend in A&E. Patients who require high healthcare resources spend the least amount of time in A&E, while those who require low resources spend the most. The median time spent in A&E exceeds 240 minutes for patients undergoing 8-9 investigations. Patients who arrive via ambulance have the lowest minimum A&E time, but also the highest upper limit. The hour of the day with the highest proportion of patients staying more than 240 minutes is 1:00-4:00 AM and 9:00-12:00 PM. Patients who arrive via ambulance have the shortest A&E time if they come in between 9:00 AM and 12:00 PM, and patients who use private transportation have the shortest A&E time if they come in between 5:00-4:00 PM. 75% of patients who do not require healthcare resources are admitted by 240 minutes. Patients who require high healthcare resources have the shortest median time in A&E, and those aged 65-84 have the longest time. The group of patients with low healthcare resource needs have the longest time in A&E, with the limit increasing as age increases.
## Key Insights for Presentation

> * Low healthcare resource group, higher number of investigations, older patients, using the ambulance and arriving at night is associated with longer time spent in the A&E
> For the presentation I changed the color of the different columns and line to emphasize my point also I remove other categories that are not significant for better clarity
