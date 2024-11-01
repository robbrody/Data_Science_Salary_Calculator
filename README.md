# Data_Science_Salary_Calculator

![Data Science Salary Calculator](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/DS_Salary_Calculator.gif)*Dashboard in Excel showing Data Science Job Salary Calculator*

## Introduction
I developed an interactive Excel dashboard using Luke Barousse's Job Salary dataset, which includes over 32,000 job postings for Data Science roles worldwide, with a primary emphasis on the United States in 2023. This dashboard presents a comprehensive analysis by calculating the median salary for positions categorized by job title, country, and job schedule type. Users can interact with dropdown filters to customize the data view by job title, country, and schedule. The dashboard features three main visualizations: median salary by job title, median salary by country, and median salary by job schedule type. Additionally, KPI cards display key metrics, including the median salary, top job listing platform, and job count based on selected filters. This tool offers an efficient, user-friendly way to explore and analyze job posting data effectively

### Dashboard File

The final dashboard file is in (https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/Data%20Jobs%20Dashboard%20Project.xlsx).

### Excel Skills Used in Project

The following Excel skills were utilized for analysis:
* Charts: For visualizing the data.
* Formulas and Functions: For Sorting, ANalyzing, Filtering the Data.
* Data Validation: For restricting options in drop-down user interactive elements.

## Dashboard Build

### Charts

**Data Science Job Salaries Bar Chart**
![Job Title Salaries Bar Chart](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/Job_title_graph_and_dropdown.png)

* Utitlized bar chart (with formatted salary values) na doptimized layour for clarity
* Horizontal bar chart for visual comparison of median salaries.
* Sorted job titles by descending slaary for improved readability.
* This chart enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

**Median Salary by Country Map Chart**
![Map Chart of Median Salaries](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/Country_graph_dropdown.png)

* Utilized Excel's map chart feature to plot median salaries globally.
* Color-coded map to visually differentiate salary levels across countries.
* Plotted median salary for each country with available data.
* Improved visual and immediate understanding of geographic salary trends.
* Enables quick visual of global salary disparities and highlights higher and lower areas.

### Formulas and Functions

**Median Salary by Job Titles**
``` excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[salary_year_avg]<>0)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
    jobs[salary_year_avg]
  )
)
```
* Filtering Multi-Item: CHecks job title, country, schedule type, and excludes any blank salary values.
* Array Formula: Utilizes Median() function with nested IF() statement to analyze an array.
* Insights: Provides the salary information for specific chosen job titles, countries, and schedule types.
* Formula: This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table
!(https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/Job-title_table.png)  

Dashboard Implementation

!()
