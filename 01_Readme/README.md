# SQL Data Analytics Project

## About This Project

This project is a **SQL-based data analytics project** focused on analyzing real-world job posting data using **PostgreSQL**.

The main objective of the project is to explore the job market from a data analyst's perspective by analyzing **job titles, salaries, companies, locations, and required skills**.

The project uses a relational database containing multiple interconnected tables. By combining these tables with SQL joins, filtering, aggregation, and other analytical techniques, the project transforms raw job posting data into meaningful information about employment opportunities and skill requirements.

This project was also created to develop practical experience with SQL and understand how SQL can be applied to **real-world data analysis problems** rather than only working with small theoretical datasets.

---

## Project Objectives

The key objectives of this project are to:

* Analyze Data Analyst job postings using SQL
* Identify high-paying job opportunities
* Explore salary differences across job titles
* Analyze companies and their hiring activity
* Identify frequently requested skills
* Examine remote job opportunities
* Understand the relationship between job postings, companies, and skills
* Practice working with relational databases and multiple tables
* Develop SQL queries that answer practical business and analytical questions
* Extract useful insights from large datasets

---

## Tools & Technologies

The project was developed using:

* **PostgreSQL** — Relational database management system
* **SQL** — Data querying and analysis
* **pgAdmin 4** — Database management and query execution
* **VS Code** — SQL development and project management
* **Git** — Version control
* **GitHub** — Project documentation and portfolio

---

## Dataset

The dataset contains real-world job posting information and is divided into multiple relational tables.

The data includes information such as:

* Job titles
* Job descriptions
* Companies
* Locations
* Salaries
* Job posting details
* Required skills
* Company information
* Skill-to-job relationships

The relational structure of the dataset makes it possible to connect information across different tables using keys such as `job_id`, `company_id`, and skill-related identifiers.

This allows more detailed analysis than would be possible from a single standalone table.

---

## Data Analysis Performed

The project explores several aspects of the data analyst job market.

### 1. Salary Analysis

Salary information was analyzed to identify high-paying job opportunities.

The analysis includes:

* Comparing salaries across job postings
* Identifying the highest-paying positions
* Filtering jobs with available salary information
* Finding jobs above specific salary thresholds
* Comparing average salaries across different categories
* Examining salary differences between job titles

Missing salary values were excluded where necessary to ensure that salary comparisons were based on available compensation data.

---

### 2. High-Paying Data Analyst Jobs

One of the analyses focuses on identifying Data Analyst positions with the highest reported annual salaries.

The query filters the dataset to:

* Data Analyst positions
* Jobs with available salary information
* Remote positions
* Salary sorted from highest to lowest

This provides a practical example of using multiple filtering conditions together with sorting and limiting results.

---

### 3. Remote Job Analysis

The project separately analyzes remote Data Analyst opportunities.

Job postings where the location is listed as **"Anywhere"** are used to identify positions that are not restricted to a specific physical location.

This allows the dataset to be explored from a remote-work perspective and provides an example of how categorical fields can be used to segment data.

---

### 4. Company Analysis

Company information is connected to job postings using `company_id`.

This makes it possible to analyze:

* Number of job postings by company
* Companies with a large number of postings
* Hiring activity across organizations
* Companies associated with Data Analyst opportunities
* Company-level job posting patterns

Aggregation functions such as `COUNT()` and clauses such as `GROUP BY` and `HAVING` are used to generate these summaries.

---

### 5. Skills Analysis

The dataset contains separate tables for job postings and skills.

These tables are connected using relational joins, allowing the project to investigate the skills requested by employers.

The analysis can be used to identify:

* Most frequently requested skills
* Skills associated with Data Analyst positions
* Skills appearing across multiple job postings
* Skills connected to specific jobs
* Relationships between skills and salary information

This demonstrates how relational databases can combine information stored across multiple tables.

---

### 6. Job Title Analysis

Different job titles were analyzed to understand how opportunities vary across roles.

The analysis can compare:

* Number of job postings
* Salary ranges
* Average salaries
* Job titles with higher reported compensation
* Differences between Data Analyst-related positions

This provides a broader view of how job titles and compensation vary within the dataset.

---

### 7. Location Analysis

Job locations were analyzed to understand where opportunities are concentrated.

The analysis can be used to identify:

* Locations with the highest number of job postings
* Remote opportunities
* Job distribution across different locations
* Differences in job availability between locations

Grouping and aggregation techniques are used to summarize the location data.

---

## Example SQL Analysis

The following query identifies the **10 highest-paying remote Data Analyst jobs with available salary information**:

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

This query demonstrates several important SQL concepts:

* `SELECT` to choose required columns
* `LEFT JOIN` to connect job postings with company information
* `WHERE` to filter the required job postings
* `IS NOT NULL` to exclude missing salary values
* `ORDER BY` to rank salaries from highest to lowest
* `LIMIT` to return the top 10 records

The analysis can then be extended by joining the results with the skills tables to investigate the skills associated with these positions.

---

## SQL Concepts Used

This project provides practical experience with a wide range of SQL concepts, including:

### Basic Querying

* `SELECT`
* `WHERE`
* `DISTINCT`
* `ORDER BY`
* `LIMIT`

### Filtering

* `BETWEEN`
* `IN`
* `LIKE`
* Comparison operators
* Multiple filtering conditions
* `IS NULL`
* `IS NOT NULL`

### Aggregation

* `COUNT()`
* `SUM()`
* `AVG()`
* `MIN()`
* `MAX()`

### Grouping

* `GROUP BY`
* `HAVING`

### Joins

* `INNER JOIN`
* `LEFT JOIN`
* Joining multiple tables
* Joining tables using primary and foreign key relationships

### Advanced SQL

* Common Table Expressions (CTEs)
* Subqueries
* `CASE` statements
* `UNION`
* `UNION ALL`
* Date extraction and date functions
* String functions
* Conditional filtering
* Multi-table analysis

---

## Database Relationships

A major part of this project was understanding how different tables in a relational database work together.

For example:

**Job Postings → Companies**

Job postings can be connected to companies using `company_id`.

**Job Postings → Skills**

Job postings can be connected to their required skills through the skills relationship tables.

This structure allows information from different parts of the database to be combined and analyzed using SQL joins.

Understanding these relationships was an important part of developing practical database and SQL skills.

---

## What I Learned

Working on this project helped me develop practical experience in several areas of SQL and data analysis.

### SQL & Database Skills

* Writing SQL queries to solve analytical problems
* Working with PostgreSQL
* Understanding relational database structures
* Connecting multiple tables using joins
* Filtering large datasets
* Aggregating and summarizing data
* Using CTEs to organize more complex queries
* Using subqueries for multi-step analysis
* Working with dates and text fields
* Understanding primary and foreign key relationships

### Data Analysis Skills

* Translating analytical questions into SQL queries
* Identifying useful patterns within raw data
* Comparing salaries and job opportunities
* Analyzing company hiring activity
* Exploring job-market skill requirements
* Working with missing data
* Creating structured summaries from large datasets

### Practical Development Skills

The project also provided experience with:

* PostgreSQL database workflows
* pgAdmin 4
* VS Code
* Git
* GitHub
* Organizing SQL scripts
* Documenting an analytics project
* Building a portfolio project around a real-world dataset

---

## Key Takeaways

The project demonstrates how SQL can be used to move from **raw job posting data to structured analysis**.

Instead of looking at individual records manually, SQL makes it possible to:

**Filter → Join → Group → Aggregate → Compare → Analyze**

This approach allows large datasets to be explored efficiently and helps answer practical questions about salaries, companies, locations, job titles, and skills.

The project also helped strengthen my understanding of how SQL is used as an analytical tool rather than simply as a way to retrieve database records.

---

## Future Improvements

The project can be further expanded by adding additional analytical and visualization components.

Possible future improvements include:

* More advanced salary analysis
* Skill-to-salary comparisons
* Analysis of salary distributions
* Company-level salary comparisons
* More detailed location analysis
* Analysis of job posting trends over time
* Python-based exploratory data analysis
* Excel-based analysis
* Power BI dashboards
* Data visualizations
* More advanced SQL queries
* Additional CTE and subquery-based analysis

These additions would allow the project to evolve from a SQL-focused analysis into a more complete **end-to-end data analytics project**.

---

## Conclusion

This project provided hands-on experience in using **PostgreSQL and SQL to analyze real-world job posting data**.

By working with multiple relational tables, I was able to practice data extraction, filtering, aggregation, joins, and analytical querying while exploring practical questions about the job market.

The project represents my ongoing development in **SQL and data analytics** and serves as part of my portfolio as I continue building practical skills in data analysis.

---

## Author

**Uday Gupta**

BMS Student | Aspiring Data Analyst

---

*This project was created for learning, practical SQL development, data analysis practice, and portfolio building.*
