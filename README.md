# Individual-Self-Assessment

# Self-Assessment

The goal to take this bootcamps is develop my own IT skills in order to help me for my job seeking in financial analyst areas. Before I took this program, I was no idea about python, machine learning, SQL, etc. After taking the program, I am able to solve some basic issue at least. However, during the program, I always come across with some errors which I cannot understand why, even though I followed the instruction strickly. But the Ask BCS was helping me a lot while I came across with any issue. For each of the assignment, there always starter code provided, but I do not feel confident if there is no starter code for me for my future work. I believe  I still need some hard work on thoses technique I learned and improve my self problem solving skills.

# Team Assessment

In order to effectively complete our project, we have distributed the different part of our project to each teammates base on our skills. Our team has approach for help when we have any issues which been solved effectively. Work and leadership roles were well-defined, Rahul Lal did a great job as leader of out group. We have a clear direction of our project. Each individule team members were respect to each other's perspective. Members work collaboratively with each other. 


# Summary of the Project

# Project Goal

Diabetes is a very common disease with a wide range of ages. But the treatment varies from patient to patient. Medication regimens and efficiency cycles are also very different for each patient. We used patient information from 130 U.S. hospitals from 1999 to 2008. Through the data, we will analyze the response, cycle and drug resistance rate of different patients to treatment drugs. However, through a large amount of data analysis can provide limited information. Therefore, our project will use machine learning techniques to analyze patients' responses to drugs based on different attributes and determine what are the features that are affecting the readmittance rate.

# Dataset Description

Our dataset is “Diabetes 130-US hospitals for years 1999-2008”.

Source: https://www.kaggle.com/datasets/jimschacko/10-years-diabetes-dataset

This dataset is representative of 10 years (1999-2008) of treatment/clinical care at 130 US hospitals. The information has been extracted from the database of patient encounters based on the following criteria:

The patient has been admitted to the hospital.
Diabetes was entered to the system as a diagnosis during the encounter
The length of hospital stay was between 1 to 14 days
Lab tests were carried out during the encounter
Medication was administered during the encounter
The different attributes in the data are as follows:

Patient number
Encounter id
Patient demographics such as race, gender, age and weight
Pre-decided codes for the hospital industry
Admission type (basic types of admission for inpatient hospital stays and a code indication priority of admission)
Discharge disposition id (the final place or setting to which the patient was discharged)
Admission source id
Payer code
Diag Features (indicate the diagnoses of the cause of the patient’s health problem)
Diag_1 (first diagnose)
Diag_2 (second diagnose)
Diag_3 (third diagnose)
Time in hospital
Medical specialty
Number of
Lab procedures
Outpatients
Emergency
Inpatient
Diagnoses
Different drugs administered (a list of 22 drugs)
Change (if the drug dosage was changed)
Diabetes medication
Readmitted
<30 – indicates the patient was readmitted within 30 days of discharge
30- indicates the patient was readmitted after 30 days of discharge
No- indicates there was no readmission

# Data Cleaning

Remove duplicate data points There are 101,766 data points in the dataset, some of them are duplicates. We will use patient_nbr column as a reference, since it is a unique number given to each unique patient.This gave us 71518 data points.

<img width="657" alt="image" src="https://user-images.githubusercontent.com/6320035/184040497-232c81cf-2e29-42c1-826e-014cea6ddf91.png">

Remove Uninformative Features The uninformative features in the dataset (21 in total) were discarded due to either, a huge amount of missing sample values (>50%), or due to the fact that some features are not relevant to classify the data towards our target or if the feature is compeletly unbalanced (>95% of data points have the same value for the feature).

<img width="453" alt="image" src="https://user-images.githubusercontent.com/6320035/184040461-a18b0770-05c4-48de-abfc-522479630fd2.png">

Diag Feature Diag Features Fix Diag features indicate the diagnoses of the cause of the patien’s health problem.

diag_1: First diagnose
diag_2: Second diagnose
diag_3: Third diagnose
They are coded in ICD-9 code (https://en.wikipedia.org/wiki/List_of_ICD-9_codes), resulting in hundreds of distinct categories. One way to simplify this, is by grouping every ICD-9 code value into one of 18 generic health problems.

Race Feature For 'Race' we replaced the missing data points values with ‘Other’ category, as most likely people who skipped filling their race did that because they couldn’t find their race listed within the options.

Gender Feature For 'Gender' we replaced the invalid values with 'Female' as a larger sample size belongs to this gender category.

Age Feature For age, we have 10 categories, each represents 10 years range from [0-10] to [90-100]. We replaced those with the middle age for each age range: for example (0,10] will be replaced with 5; (60, 70] will be replaces by 65; and so on.

Drugs Feature Drugs Features Fix We still have 7 features, each one represents the change in the patient’s dosage of a specific drug, during hospital encounter. Those 7 drugs are the following:

metformin
glimepiride
glipizide
glyburide
pioglitazone
rosiglitaz

# Dashboard

The following visualisations were obtained using the top ranking features.

<img width="551" alt="image" src="https://user-images.githubusercontent.com/6320035/184040151-c24df0d8-57f2-4bf4-972f-3774aee6a597.png">

<img width="844" alt="image" src="https://user-images.githubusercontent.com/6320035/184040193-f8b1b803-219c-4483-a345-dc291d5c6ae9.png">
<img width="586" alt="image" src="https://user-images.githubusercontent.com/6320035/184040215-761185ae-3b13-4aa1-ae86-b1a9f13f8237.png">
<img width="606" alt="image" src="https://user-images.githubusercontent.com/6320035/184040253-80adbbc5-f75b-4ffc-b610-81e2f0939cdf.png">

# Machine Learning Models

Random Forest Classifier

<img width="426" alt="image" src="https://user-images.githubusercontent.com/6320035/184040322-579306f2-3957-4d0c-a7d2-6260d9b534fa.png">
<img width="561" alt="image" src="https://user-images.githubusercontent.com/6320035/184040340-cb56b633-c4b5-48da-97d8-da8d26983b43.png">
<img width="465" alt="image" src="https://user-images.githubusercontent.com/6320035/184040358-596962f9-8a03-43bf-9fae-565ff34a96eb.png">

<img width="443" alt="image" src="https://user-images.githubusercontent.com/6320035/184040372-b04fc438-deba-4f11-aad4-f3f834e891a8.png">

# Conclusion

After multiple attempts to improve the machine learning model results we reached the following conclusions:

Random Forest classifier is more successful in readmittance rate prediction compared to ANN and Logistic Regression.

Using more datapoints and converting the model from multi-class classification to binary classification improves the results.

The classification model can improve if we provide more data points. One way to achieve this is to use updated and live data.

Obesity is known to have a correlation with diabetes. One major shortcoming of this dataset was that majority of the weight data was missing.
