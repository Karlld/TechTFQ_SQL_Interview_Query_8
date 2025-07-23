
```sql

WITH RECURSIVE filled_roles AS (SELECT *
                                   FROM job_skills
                                   WHERE row_id = (SELECT MIN(row_id) FROM job_skills)

                           UNION ALL
   
	           SELECT j.row_id,
                          COALESCE(j.job_role, f.job_role) AS job_role,
	                  j.skills
               FROM job_skills j
               JOIN filled_roles f ON j.row_id = f.row_id + 1
                              )
	   
   SELECT * FROM filled_roles;
```

| row_id | job_role | skills |
|--------|----------|--------|
| 1	| Data Engineer |	SQL |
| 2	| Data Engineer |	Python |
| 3	| Data Engineer |	AWS |
| 4	| Data Engineer |	Snowflake |
| 5	| Data Engineer |	Apache Spark |
| 6	| Web Developer |	Java |
| 7	| Web Developer |	HTML |
| 8	| Web Developer |	CSS |
| 9	| Data Scientist |	Python |
| 10	 | Data Scientist |	Machine Learning |
| 11	| Data Scientist |	Deep Learning |
| 12	| Data Scientist | Tableau| 

```sql

SELECT row_id,
       CASE WHEN row_id < 6 THEN 'Data Engineer'
            WHEN row_id < 9 THEN 'Web Developer'
            ELSE 'Data Scientist'
            END AS job_role,
       skills
   FROM job_skills;

```

| row_id | job_role | skills |
|--------|----------|--------|
| 1	| Data Engineer |	SQL |
| 2	| Data Engineer |	Python |
| 3	| Data Engineer |	AWS |
| 4	| Data Engineer |	Snowflake |
| 5	| Data Engineer |	Apache Spark |
| 6	| Web Developer |	Java |
| 7	| Web Developer |	HTML |
| 8	| Web Developer |	CSS |
| 9	| Data Scientist |	Python |
| 10	 | Data Scientist |	Machine Learning |
| 11	| Data Scientist |	Deep Learning |
| 12	| Data Scientist | Tableau| 
