**TechTFQ_SQL_Interview_Query_8**

In the given input table, there are rows with missing JOB_ROLE values. Write a query to fill in those blank fields with appropriate values.
Assume row_id is always in sequence and job_role field is populated only for the first skill.
Provide two different solutions to the problem.

```sql

DROP TABLE IF EXISTS job_skills;

CREATE TABLE job_skills (row_id INT, job_role VARCHAR(20), skills VARCHAR(20));

INSERT INTO job_skills VALUES (1, 'Data Engineer', 'SQL');
INSERT INTO job_skills VALUES (2, null, 'Python');
INSERT INTO job_skills VALUES (3, null, 'AWS');
INSERT INTO job_skills VALUES (4, null, 'Snowflake');
INSERT INTO job_skills VALUES (5, null, 'Apache Spark');
INSERT INTO job_skills VALUES (6, 'Web Developer', 'Java');
INSERT INTO job_skills VALUES (7, null, 'HTML');
INSERT INTO job_skills VALUES (8, null, 'CSS');
INSERT INTO job_skills VALUES (9, 'Data Scientist', 'Python');
INSERT INTO job_skills VALUES (10, null, 'Machine Learning');
INSERT INTO job_skills VALUES (11, null, 'Deep Learning');
INSERT INTO job_skills VALUES (12, null, 'Tableau');

SELECT * FROM job_skills;
```

| row_id | job_role | skills |
|--------|----------|--------|
| 1  | Data Engineer | 	 SQL |
| 2 |		|                   Python |
| 3 |		 |                  AWS |
| 4 |		  |              Snowflake |
| 5 |		   |            Apache Spark |
| 6 |  Web Developer |	         Java |
| 7 |		           |         HTML |
| 8 |		           |         CSS |
| 9 |  Data Scientist |	         Python |
| 10 |		        |   Machine Learning |
| 11 |		        |     Deep Learning |
| 12 |		         |           Tableau |

