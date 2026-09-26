# SQL Data Analytics Project

## About This Project

This project focuses on analyzing real-world job posting data using **PostgreSQL and SQL**.

The objective is to explore the job market through job titles, salaries, companies, locations, and required skills, while developing practical SQL and data analysis skills.

---

## Tools & Technologies

* PostgreSQL
* SQL
* pgAdmin 4
* VS Code
* Git & GitHub

---

## Project Structure

```text
SQL Workspace
│
├── csv_files
│   └── Source CSV datasets
│
├── sql_load
│   └── SQL scripts used to load the datasets
│
├── Project_SQL
│   └── SQL analysis queries
│
└── Readme
    └── Project documentation
```

---

## Dataset

The dataset contains job posting information including:

* Job titles
* Companies
* Locations
* Salaries
* Job skills
* Job posting details

The data is organized into multiple relational tables, allowing SQL joins and aggregations to be used for analysis.

---

## Key Analysis Performed

The project explores questions such as:

* Which data analyst jobs offer the highest salaries?
* Which companies have the most job postings?
* Which skills are most frequently requested?
* Which locations have the highest number of opportunities?
* What are the highest-paying remote data analyst positions?
* How do different job titles compare in terms of salary?
* Which skills are associated with higher-paying positions?

---

## Key Insights

### 1. High-Paying Data Analyst Jobs

The analysis identified high-paying Data Analyst opportunities by filtering job postings based on salary and sorting them in descending order.

For example, remote Data Analyst positions with available salary information were analyzed to identify the highest-paying opportunities.

### 2. Salary-Based Analysis

Salary information was filtered to remove missing values before comparing compensation across job postings.

This helped identify positions offering salaries above **$70,000 per year** and allowed higher-paying opportunities to be examined separately.

### 3. Remote Job Opportunities

The dataset contains job postings where the location is listed as **"Anywhere"**, allowing remote Data Analyst opportunities to be analyzed separately from location-specific jobs.

### 4. Skills Analysis

Job postings were connected with the skills tables using relational joins.

This allowed the project to investigate:

* Which skills appear most frequently in Data Analyst postings
* Which skills are associated with individual job postings
* How skills can be connected to salary and job title information

### 5. Company Analysis

Company information was connected to job postings using `company_id`.

This makes it possible to identify companies with large numbers of job postings and analyze their hiring activity.

---

## SQL Concepts Used

This project covers a wide range of SQL concepts, including:

* `SELECT`
* `WHERE`
* `BETWEEN`
* `IN`
* `LIKE`
* `ORDER BY`
* `LIMIT`
* `DISTINCT`
* `COUNT()`
* `SUM()`
* `AVG()`
* `MIN()`
* `MAX()`
* `GROUP BY`
* `HAVING`
* `CASE`
* `INNER JOIN`
* `LEFT JOIN`
* `UNION`
* `UNION ALL`
* Common Table Expressions (CTEs)
* Subqueries
* Date functions
* String functions
* Filtering
* Aggregation

---

## Example Analysis

One example from the project is identifying the highest-paying remote Data Analyst jobs:

```sql
SELECT
    job_id,
    job_title,
    salary_year_avg,
    name AS company_name
FROM job_postings_fact
LEFT JOIN company_dim
    ON job_postings_fact.company_id = company_dim.company_id
WHERE
    job_title_short = 'Data Analyst'
    AND job_location = 'Anywhere'
    AND salary_year_avg IS NOT NULL
ORDER BY salary_year_avg DESC
LIMIT 10;
```

The analysis can then be extended by joining the job postings with the skills tables to understand the skills associated with these positions.

---

## What I Learned

Through this project, I developed practical experience in:

* Working with relational databases
* Writing SQL queries for real-world datasets
* Joining multiple tables
* Filtering and sorting large datasets
* Using aggregate functions
* Grouping data and generating summaries
* Using CTEs to structure complex queries
* Connecting job postings with companies and skills
* Extracting useful insights from raw data

---

## Future Improvements

Future versions of this project may include:

* More advanced SQL analysis
* Salary and skill comparisons
* Additional job-market insights
* Python-based analysis
* Excel analysis
* Power BI dashboards
* Data visualizations

---

## Author

**Uday Gupta**

BMS Student | Aspiring Data Analyst

---

*This project was created for learning, practical SQL development, and portfolio building.*
