# Excel Data Science Salary Dashboard
! [using.gif]
(/images/using.gif)

## Introduction
A dashboard to help guide job seekers in data-driven fields towards their career and salary goals. 
(by filtering on various job criteria.) 
The dashboard allows the ability to select different job titles, locations, and schedule types, and then returns their median salaries, the top platform the job was posted on, and the job posting count. The results are presented through palatable mediums like graphs, maps, and KPI cards.

# Dashboard File
jgugugu


# Excel Skills Used:
- Data validation
- Data visualization with charts
- Functions and formulas such as XLOOKUP, COUNTIFS, MEDIAN, SORT, UNIQUE


# Dataset
- The dataset used for this project employs real-world job posting information from 2023, web-scraped by a third party (see acknowledgments). The collection of job postings were biased towards the United States. Fields include: 
- Job titles
- Salaries 
- Locations 
- Skills
- Platforms

##Dashboard Design
###Formuals and Functions

Background Table
(INSERT PICTURE OF TABLE)



###Charts and Graphs


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

Findings:
- Senior Data Scientists in the United States have the highest median salaries at 155K followed closely by Machine Learning Engineers and Senior Data Engineers at 150K
- Most job titles in the United States have the highest job type count when the schedule is "full time," meaning, applicants have a higher likelihood of landing a job quicker if they are searching for full time positions. 
- The most frequently occurring top job platform for a Business Analyst in Germany and the United Kingdom is Ai-Jobs.net.

Future Improvements
- A way to improve this dashboard could be to filter to remove outlying data past a certain threshold before its calculated into medians or plotted on the map. For instance, there are job postings with salary_year_avgs of upwards of 960K in the dataset with only one instance of that salary listed. While this is a great dream to have, its not necessarily in the realm of realistic. A fix for this would be to add a clause that removes values of salary_year_avg > 350,000 before aggregating. Another approach would be to eliminate jobs based on salary frequency in intervals. If there are less than 3 jobs with a salary between 950K-1M then they're removed, but if there are more than 15 jobs with salaries between 300K-350K, then they're kept. 

- Other improvements one could make is to pull in the salary_hour_avg or the job_skills fields so the user can view median hourly rates or input the skills they possess to further filter down and personalize results. 

Conclusion: 
With this dashboard, job seekers can gain better insight into their desired careers which will help carve out a clearer path on their journeys through the vast ether of job postings. They can use this dashboard as an optimization guide, whether it be for which platform they should spend most time searching on, or for salary negotiations to earn what they deserve in relation to median data. 

