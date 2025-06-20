# Excel Salary Dashboard

![Dashboard Preview](Project_1_Dashboard/excel_dashboard.png)

## Introduction

This data jobs dashboard served to both help me find which data career I should focus on as well as taught me the foundations of analyzing data using excel. This dashboard was a part of an 11 hour excel boot camp course create by Luke Barousse who gave an in-depth overview off all the skills used to create this dashboard and more. His youtube channel is linked below.

https://www.youtube.com/@LukeBarousse

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project, provided by Luke Barousse, contains real-world data science job information from 2023. It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### Charts

#### Data Science Job Salaries - Bar Chart

![Salary Dashboard Bar Preview](images/job_salary.png)


- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** Enabled quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### Country Median Salaries - Map Chart

![Salary_Dashboard_Map_Chart](images/job_map.png)

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enabled quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

#### Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- **Multi-Criteria Filtering:** Checked job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilized `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provided specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populated the table below, returning the median salary based on job title, country, and type specified.


#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** This Excel formula below employed the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populated the table below, which gives us a list of unique job schedule types.

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implemented the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced


## Conclusion

I created this dashboard to learn new excel tricks and showcase insights into salary trends across various data-related job titles. Utilizing data from my Luke Barousse, this dashboard helped me gain a better insight into salaries associated with different data jobs. 
