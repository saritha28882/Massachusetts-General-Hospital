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
| 1 | DateTable (Date) | hospital_db_encounters (START) | One to Many | Inactive |
| 2 | DateTable (Date) | hospital_db_procedures (START) | One to Many | Active |
| 3 | hospital_db_procedures (PATIENT) | hospital_db_patients (Id) | One to Many | Inactive |
| 4 | AgeGroup (AGEGROUP) | Age (AGEGROUP) | One to Many | Active |
| 5 | Age (AGE) | hospital_db_patients (Age) | One to Many | Active |
| 6 | hospital_db_encounters (ID)    | hospital_db_procedures (ENCOUNTER) |  One to Many | Active |
| 7 | hospital_db_patients (Id) | hospital_db_ENCOUNTERS (PATIENT) | One to Many | Active |
| 8 | hospital_db_encounter class (Description) | hospital_db_ENCOUNTERS (Description) | One to Many | Active |
| 8 | hospital_db_encounter (Payer) | hospital_db_payers (ID) | One to Many | Active |
  
  <img width="1349" height="562" alt="Data Modeling" src="https://github.com/user-attachments/assets/6f0485a1-1fcc-4e36-80c9-002fb430f4dc" />


### **Features and Highlights**
##### Business Problem:
Analyze and build reports around patient, encounter, and procedure data to provide KPI and operational performance reports, and to uncover deeper insights from the dataset.

##### Key Questions:
1) How many patients have been admitted or readmitted over time?
2) How long are patients staying in the hospital, on average?
3) How much is the average cost per visit?
4) How many procedures are covered by insurance?

##### Visuals Used
1) Total Sales By Manager, Average Sales, Average Weeks to Close, New Opportunities, Engaged Opportunities - (Card Visuals)
2) Performance By Agent, Sales by Product, Open Opportunities (Table Visual)
3) Total Sales By Sector, Total Sales By Product, Performance comparison measures with other managers (Clustered Bar Chart)
4) Quarterly Opportunities for the manager (Stacked Column Chart)
5) Total sales of the manager over a year across querters (Line Chart)
6) Smart Narrative visual which analayses a number of visulas in the report page and derive insights from those


##### Screen shots
Selected Quarter Performance*(Maven-Sales-Analysis/Selected Quarter Performance by Manager.png)](https://github.com/saritha28882/Maven-Sales-Analysis/blob/main/Selected%20Quarter%20Performance%20by%20Manager.png)

Selected Quarter Sales[https://github.com/saritha28882/Maven-Sales-Analysis/blob/main/Selected%20Quarter%20Sales%20by%20Manager.png]

Performance By Team[[Maven-Sales-Analysis/Performance by Team.png at main · saritha28882/Maven-Sales-Analysis](https://github.com/saritha28882/Maven-Sales-Analysis/blob/main/Performance%20by%20Team.png)]

Open Opportunities of Manager[[Maven-Sales-Analysis/Open Opportunities of Manager.png at main · saritha28882/Maven-Sales-Analysis](https://github.com/saritha28882/Maven-Sales-Analysis/blob/main/Open%20Opportunities%20of%20Manager.png)]

Performance Over Time[[Maven-Sales-Analysis/Performance over time.png at main · saritha28882/Maven-Sales-Analysis](https://github.com/sarith
