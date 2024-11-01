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

![Job Title Salaries Bar Chart](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/job_title_graph.png)

* Utitlized bar chart (with formatted salary values) na doptimized layour for clarity
* Horizontal bar chart for visual comparison of median salaries.
* Sorted job titles by descending slaary for improved readability.
* This chart enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.
  

**Median Salary by Country Map Chart**

![Map Chart of Median Salaries](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/DS_Salary_Calculator_Map.gif)


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

Background Table:

![Job Title Median Salary Table](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/Job-title_table.png)  

Dashboard Implementation:

![Dashboard Image with Dropdown, Chart, and KPI](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/job_title_dd_kpi.png)

**Count of Job Schedule Type**

``` excel
=FILTER(J2#,NOT(ISNUMBER(SEARCH("and", J2#)))*(J2#<>0))
```
* Unique List Generation: This Excel formula above employs the FILTER() function to exclude entries containing "and" or commas, and omit zero values.
* Formula: This formula populates the table below, which gives us a list of unique job schedule types that are not combined with other job types.

Background Table:

![Job Schedule Type Table](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/job_schedule_type_table.png)


Dashboard Implementation:

![Job Schedule Type Dropdown Chart KPI](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/job_schedule_type_dd_graph_kpi.png)


### Data Validation

**Filtered List**
* Enhanced Data Validation: Implemented the fltered list as a data validation rule undr the Job Title, COuntry, and Type option in the Data tab ensures:
    * User input is restricted to the predefined, and validated schedule types.
    * Incorrect or inconsistent entries are prevented.
    * Overall usability of the dashboard is enhanced.


![Job Title Dropdown selection](https://github.com/robbrody/Data_Science_Salary_Calculator/blob/main/DS_Salary_Calculator_DD_title.gif)


## Conclusion

The Data Job Salary Calculator Dashboard was developed to strengthen my Excel proficiency while enabling more efficient and insightful analysis of job posting data. This tool provides stakeholders with accessible, data-driven insights to support informed decision-making based on comprehensive job market trends. Key findings reveal that median salaries are generally higher for Data Scientist and Engineer roles compared to Analyst positions, and full-time roles tend to offer greater compensation than other job types. Indeed and LinkedIn emerge as the top platforms for U.S.-based job postings, and the United States stands out with a significantly higher job count than other countries in this dataset.
