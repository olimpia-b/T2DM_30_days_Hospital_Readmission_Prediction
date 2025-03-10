# T2DM_30_days_Hospital_Readmission_Prediction

Team Members: Eric Bai, Min Xu, Olimpia Borgohain, Casey Chen

### Problem Statement
This study aims to build machine learning models that predicts 30 days hospital readmission likelihood of patients with diabetes.

### Project Proposal
Many predictive models for diabetic readmissions rely on outdated datasets, making them less relevant to today's healthcare. This study uses the MIMIC-IV database, a modern and comprehensive dataset with recent clinical and hospital data. By combining proven techniques with updated information, we aim to create a predictive model that is practical, reliable, and better suited to current diabetes care and hospital needs.

### Data Source
For this project, we used the MIMIC-IV (Medical Information Mart for Intensive Care IV) dataset, a publicly available database that contains de-identified health-related data from patients admitted to the intensive care units (ICUs) of the Beth Israel Deaconess Medical Center between 2008 and 2019. MIMIC-IV is widely used for healthcare research, offering rich data across demographics, admissions, laboratory results, diagnoses, prescriptions, and clinical notes, among others.<br>
In this study, we focus on hospital admission specifically. To make the dataset more relevant to our study on 30-day readmissions among type 2 diabetes patients, we applied the these transformations:<br>
We filtered the data and cleaned it based on the following criteria to focus on the relevant subset of admissions:
 **1. Length of Stay:** Only hospital admissions with a length of stay exceeding 24 hours were retained
 **2. Mortality Status:** Admissions where the patient died during their first hospitalization were excluded
 **3. Discharge Destination:** Admissions where the patient was discharged to hospice care were excluded
 **4. Primary Diagnoses:** We retained only admissions where at least one of the top five diagnoses was related to type 2 diabetes
 **5. Minimum Medical Activity:** To capture meaningful healthcare interactions, we included only admissions with at least one recorded lab test and one documented procedure.
 We engineered features by leveraging multiple tables in MIMIC-IV, mapping the m to the UCI Diabetes Dataset structure where possible. Despite limitations in MIMIC-IV data 
coverage, we successfully constructed 50 features (49 predictors and 1 target variable).

We also performed EDA on the data focusing on Demographic factors like Age, gender, race, and health insurance status, Clinical factors like Glucose levels, hemoglobin, heart rate, blood pressure, chronic conditions such as heart failure, depression, hypertension and Hospital-related factors: Length of hospital stay (LOS), type of admission, and source of hospitalization.

We also classifed the race groups, dealt with ICD codes in the preprocessing phase.
### Data Preprocessing Steps
11. Feature Creation
2. Feature Selection using Random Forest
3. Standardizing Categorical Variables
4. Handling Missing Data
5. Handling Outliers
6. Dealing with Class Imbalance
7. Data Type Conversion
     
### Methologies Used
 1. A neural network technique (MLP)
 2. Logistic Regression
 3. Random Forest
 4. K-Nearest Neighbors (KNN)
 5. CatBoost
 6. XGBoost
 7. LightGBM.

    We used  ROC-AUC as our primary metric for model evaluation because it can capture the model’s overall ability to discriminate between high-risk patients and low-risk patients across all thresholds. We also considered Recall as our second metric as it evaluates how well the model can identify high-risk patients
