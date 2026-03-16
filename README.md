# Salary Dashboard  

  Excel-based data analytics and visualization project featuring an interactive Global Tech Salary Dashboard.

![Dashboard](https://github.com/user-attachments/assets/7379c7e4-0c6f-4ab4-b815-d8b8535f1e30)   

## Introduction
The dashboard enables tech job seekers to explore salary insights across different countries, job titles, and employment types, helping them better understand global compensation trends.  

The data is from [Kaggle](https://github.com/sSefin/Excel_Project-Salary_Dashboard/blob/main/Project_Dashboard.xlsx), you can find the link to the data [here](https://github.com/sSefin/Excel_Project-Salary_Dashboard/raw/main/salaries.csv). It includes key information from the past 5 years such as  

- 💼 Job Titles
- 💰 Salaries
- 🌍 Company Locations
- 🏢 Job Type
- 🏠 Job Mode

## Dashboard File
You can find the final dashboard [here](https://github.com/sSefin/Excel_Project-Salary_Dashboard/raw/main/Project_Dashboard.xlsx)

## Excel Skills Used
The following skills were used in preparation of this dashboard:  

- 🔄 Power Query ETL
- 🧮 Formulas & Functions
- 🔽 Data Validation
- 📊 Charts

## Dashboard Overview  

### 🔄 Power Query  
The following steps were performed in Power Query as part of the ETL process to prepare the data for the dashboard.  

![PowerQuery](https://github.com/user-attachments/assets/7f3fa459-2fbb-48b5-87e8-adb667a8a8aa)  

- 🧹 Data Cleaning – Removed unnecessary fields and filtered out incomplete or irrelevant records.
- 🔧 Data Transformation – Standardized formats, corrected data types, and structured the dataset for analysis.
- 🌍 Data Enrichment – Mapped country codes, job titles and transformed remote work data into readable categories.
- 📊 Data Structuring – Renamed and reorganized columns to optimize the dataset for dashboard calculations.

### 🧮 Backend Formula
The formula below is used to calculate the median salary dynamically based on the selected dashboard filters.  
```
=MEDIAN(
IF(
(salaries[job_title_short]=A2)*
(salaries[salary_in_usd]<>0)*
(salaries[job_country]=country)*
(salaries[job_type]=type)*
IF(mode="All", 1, (salaries[job_mode]=mode)),
salaries[salary_in_usd]))
```
Logic:  

- 🔎 Filters the dataset dynamically based on the selected job title, country, job type, and work mode.
- 🛠 Combines the `MEDIAN()` function with a nested `IF()` statement to calculate the median value from a filtered array of data
- ⚙️ Uses conditional logic to allow the “All” option for work mode, meaning the filter is ignored when "All" is selected in job mode.
- 🔄 Updates dynamically when dashboard filters are changed.

### 🔽 Data Validation  

![Data Validation](https://github.com/user-attachments/assets/b4af25c6-30d4-4278-a195-35c0c6317ae2)

This ensures:  

- ✅ Controlled Inputs – Users can only select from predefined and validated options.
- 🚫 Error Prevention – Prevents incorrect entries in the dashboard filters.
- ⚡ Improved Interactivity – Enables the dashboard to update dynamically based on user selections.
- 🎯 Better User Experience – Ensures a cleaner, more intuitive interaction with the dashboard.

### 📊 Charts  

Tech Jobs Salaries - Column Chart

![Column Chart](https://github.com/user-attachments/assets/6fef3de4-fedb-4ff9-8426-dc2e5354e0c6)

- 📊 Implemented column charts with custom salary formatting to improve clarity and visual interpretation.
- 🔼 Organized salary values in ascending order to make role comparisons easier.
- 💡 Highlights Senior Machine Learning Engineer as the highest-paid role in the dataset.

Job Country - Map Chart

![Map Chart](https://github.com/user-attachments/assets/e912fff0-bc0c-45be-b919-d211200e7e55)  

- 🗺️ Implemented a map chart to visualize median salaries across different countries.
- 🌍 Represents country-level median salary data where information is available.
- 📊 Provides an overview of global compensation trends and regional differences.

# Conclusion  

This project demonstrates how Excel can be used as a powerful tool for data analysis and interactive dashboard development. By combining Power Query, dynamic formulas, data validation, and visualizations, the dashboard transforms raw salary data into meaningful insights.

The goal of this project was to showcase my Excel data analytics skills while also providing a useful resource for tech professionals to explore global salary trends and better understand compensation across different roles and locations.
