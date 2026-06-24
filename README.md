# Massachusetts-General-Hospital
### **Massachusetts General Hospital (Patient Analysis)** : 
Massachusetts General Hospitals Patient Analysis Dashboard : A dynamic interactive dashboard built to explore patient data and analyse patient admission records, procedures performed and the insurance coverage etc.

### **Project Description** : 
In Massachusetts General Hospitals Patient Analysis, I am playing the role of an Analytics Consultant for the Massachusetts General Hospitals. The Goal of the project is to build a high-level KPI report for the executive team, based on a subset of patient records.

### **Tech Stack**
The key technologies used to build the dashboard are
1) Power BI Desktop - Data Visualization platform for report creation
2) Power Query - Data Transformation and cleaning layer for reshaping and preparing tha data
3) DAX (Data Analysis Expression) - Used for calculated measures
4) Data Modeling - To establish relationships among tables

### **Data Source**
The data set used by the Massachusetts General Hospital includes details of the patient demographics, insurance coverage, and medical encounters & procedures.
The database has the following tables.
encounters: This table records the day-to-day patient encounters to the hospital which can be for different medical reasons.
patients: This table records the demographic data of the patients visiting the hospital.
Payers: This table records the insurance payer’s data.
Procedures: This table records the details of the procedures done by different patients in the hospital.

### **Data Set Analysis**
Identified the attributes and metrics for the chart preparation.
Patient’s admission is supposed to be identified by the value “inpatient” in the encounter class field of the encounter table. But there are records where the encounter class shows “Outpatient” and there is overnight stay for these employees.

### **Data Modeling**
1. The first step is to create a date dimension table DateTable in Power Query and then load the same to Power BI Desktop. 
2. Created AgeGroup table in Power Query. (AGEGROUP, DESCRIPTION)
3. Created Age table in Power Query(AGE, AGEGROUP)
4. Created EncounterClass table Power Query (CODE, ENCOUNTERCLASS, DESCRIPTION, BASE_ENCOUNTER_COST)
5. Calculated The Length of Stay (LOS) of each encounter by adding a custom column to the encounter table. If the LOS is >=1 then it is considered as an Admission. Else it is Non admission

##### **Relationships between Tables**
Once the data set loaded to Power BI Desktop, the following relationships are established between tables.

| SL No | Table1 | Table2 | Relationship | Relationship Status |
| --- | --- | --- | --- | --- |
| 1 | DateTable (Date) | hospital_db_encounters (STARTDATE) | One to Many | Inactive |
| 2 | DateTable (Date) | hospital_db_procedures (STARTDATE) | One to Many | Inactive |
| 3 | hospital_db_procedures (PATIENT) | hospital_db_patients (Id) | One to Many | Inactive |
| 4 | AgeGroup (AGEGROUP) | Age (AGEGROUP) | One to Many | Active |
| 5 | Age (AGE) | hospital_db_patients (Age) | One to Many | Active |
| 6 | hospital_db_encounters (ID)    | hospital_db_procedures (ENCOUNTER) |  One to Many | Active |
| 7 | hospital_db_patients (Id) | hospital_db_ENCOUNTERS (PATIENT) | One to Many | Active |
| 8 | hospital_db_encounter class (Description) | hospital_db_ENCOUNTERS (Description) | One to Many | Active |
| 8 | hospital_db_payers (ID) | hospital_db_encounter (Payer) | One to Many | Active |
  
<img width="1300" height="592" alt="Data Modeling" src="https://github.com/user-attachments/assets/8908d498-cf85-4c33-8116-f8ffc77d54ef" />



### **Features and Highlights**
##### Business Problem:
Analyze and build reports around patient, encounter, and procedure data to provide KPI and operational performance reports, and to uncover deeper insights from the dataset.

##### Key Questions:
1) How many patients have been admitted or readmitted over time?
2) How long are patients staying in the hospital, on average?
3) How much is the average cost per visit?
4) How many procedures are covered by insurance?

##### Visuals Used
1) Non-Admission - Total encounters, Procedure Count, Average Procedure Cost, Procedures covered by insurance - (Stacked Bar Chart)
2) Non-Admission - Total encounters by Gender and by Age Group - (100% Stacked Bar Chart)
3) Admission/Readmission - Count by Gender and Age Group (100% Stacked Bar Chart)
4) Admission/Readmission - Count over Month (Stacked Column Chart)
5) Admission/Readmission - Procedure Count Covered by Insurance, Average Procedure Cost, Total Procedure Count, Total Encounters (Stacked Bar Chart)
6) Procedure - Count Of Proceudres by Gender and Age Group (Donut Chart)
7) Procedure - Multi Row Card for KPI about Procedures
8) Procedures - Summary of Procedures according to Procedure Type (Table Visual)

##### Screen shots

