# Massachusetts-General-Hospital
### **Massachusetts General Hospital (Patient Analysis)** : 
Massachusetts General Hospitals Patient Analysis Dashboard : A dynamic interactive dashboard built to explore patient data and analyse patient admission records, procedures performed and the insurance coverage etc.

### **Project Description** : 
For the Maven Sales Challenge, I am playing the role of a BI Developer for MavenTech, a company that specializes in selling computer hardware to large businesses. They've been using a new CRM system to track their sales opportunities but have no visibility of the data outside of the platform.
In an effort to become a data-driven organization, you've been asked to create an interactive dashboard that enables sales managers to track their team's quarterly performance.

### **Tech Stack**
The key technologies used to build the dashboard are
1) Power BI Desktop - Data Visualization platform for report creation
2) Power Query - Data Transformation and cleaning layer for reshaping and preparing tha data
3) DAX (Data Analysis Expression) - Used for calculated measures
4) Data Modeling - To establish relationships among tables

### **Data Source**
The data contains B2B sales opportunities from a CRM database for a fictitious company that sells computer hardware, including information on accounts, products, sales teams, and sales opportunities. The data is stored in csv files.
   
### **Data Modeling**
The first step is to create a date dimension table db_Date_Table in Power Query and then load the same to Power BI Desktop. The db_Date_Table has Date column whose value starts from the earliest date available in close_date column or the engage_date column whichever is the earliest.

##### **Relationships between Tables**
Once the data set loaded to Power BI Desktop, the following relationships are established between tables.

| SL No | Table1 | Table2 | Relationship | Relationship Status |
| --- | --- | --- | --- | --- |
| 1 | Db_Date_Table (Date) | Db_sales_pipeline (Close_Date) | One to Many | Active |
| 2 | Db_Date_Table (Date) | Db_sales_pipeline (Engage_Date) | One to Many | Inactive |
| 3 | db_accounts (Account) | Db_sales_pipeline (Account) | One to Many | Active |
| 4 | db_products(Product) | Db_sales_pipeline (Product) | One to Many | Active |
| 5 | db_salesteams (sales_agent) | Db_sales_pipeline (sales_agent) | One to Many | Active |


   <img width="752" height="445" alt="Data Modeling" src="https://github.com/user-attachments/assets/b4f96f8a-ad50-497f-aa93-c6224ebbd74e" />


### **Features and Highlights**
##### Business Problem:
MavenTech company wants to get information about performance of the managers in different aspects. The company wants to assess the peformance of the managers every quarter and find who is lagging behind and take measures to improve their performance and hence improving the performance of the company.

##### Key Questions:
1) Analyse the overall performane of a sales manager and his team for a particulat quarter
2) Find the Total sales by sector, product and also the top organizations with highest sales executed.
3) Compare the Total and Number of sales Won, Average value of the sales, Average weeks taken to close a sale and the number of sales discounted by a manager with other managers in the company
4) Find the open opportunities of the manager and take steps to close them as soon as possible
5) Performance of the manager across different quarters of a particular year


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
