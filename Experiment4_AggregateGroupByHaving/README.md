# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value..

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="991" height="635" alt="Screenshot 2025-10-27 132131" src="https://github.com/user-attachments/assets/e2a656ee-b233-4f4c-a7d9-5363c598fc26" />


```sql
select Medication ,AVG(Dosage) as "AvgDosage"
from Prescriptions
group by Medication;
```

**Output:**

<img width="776" height="756" alt="image" src="https://github.com/user-attachments/assets/83ace68c-b9a1-4891-a35b-d5e2e094d235" />


**Question 2**
---
<img width="1031" height="652" alt="image" src="https://github.com/user-attachments/assets/54c33c08-1847-4b52-a7e5-4caadfe03494" />


```sql
select InsuranceCompany, count(*) as 'TotalExpiredPatients'
from Insurance
GROUP BY InsuranceCompany ;
```

**Output:**

<img width="911" height="751" alt="image" src="https://github.com/user-attachments/assets/bb6ef183-19e4-4a89-be03-0a47878b9534" />


**Question 3**
---
<img width="609" height="615" alt="image" src="https://github.com/user-attachments/assets/d968bacb-a3f0-4fda-9f2e-45e13580a6e0" />


```sql
select PatientID, count(*) as TotalAppointments
from  Appointments
Group by PatientID
```

**Output:**

<img width="767" height="710" alt="image" src="https://github.com/user-attachments/assets/874b1aec-4771-4cc7-b083-a6174067a985" />


**Question 4**
---
<img width="1081" height="482" alt="image" src="https://github.com/user-attachments/assets/8dfffb4a-a266-4adb-8907-fa0e904d048e" />


```sql
select count(distinct age) as COUNT
FROM employee
```

**Output:**

<img width="601" height="412" alt="image" src="https://github.com/user-attachments/assets/6b163539-6a13-43f6-884c-3557c38cbf9b" />


**Question 5**
---
<img width="756" height="563" alt="image" src="https://github.com/user-attachments/assets/f78878d2-3a3d-4315-8980-5f04b4d089ff" />


```sql
select name as fruit_name, min(inventory) as lowest_quantity
from fruits

```

**Output:**

<img width="766" height="413" alt="image" src="https://github.com/user-attachments/assets/4d059021-729b-4329-96e5-1e3be79d67ad" />


**Question 6**
---
<img width="731" height="498" alt="image" src="https://github.com/user-attachments/assets/e31ea40f-e09c-44f2-904b-4da55048b17e" />


```sql

select name,email, min(length(email)) as min_email_length
from customer
```

**Output:**

<img width="1048" height="407" alt="image" src="https://github.com/user-attachments/assets/49ae2adc-96f2-4f8b-a80d-4772c5f56735" />


**Question 7**
---
<img width="1036" height="474" alt="image" src="https://github.com/user-attachments/assets/9220e88c-a479-4fb1-b901-dafc0df64734" />


```sql
select max(age)-min(age) as age_difference
from employee
```

**Output:**

<img width="538" height="368" alt="image" src="https://github.com/user-attachments/assets/7522411a-403b-4285-9ee3-5d9cb630f988" />


**Question 8**
---
<img width="1197" height="467" alt="image" src="https://github.com/user-attachments/assets/0bbf3b61-a4bb-4ad8-b217-e24d42c51026" />


```sql
SELECT jdate, AVG(workhour)
from employee1
group by jdate
having avg(workhour) < 10;
```

**Output:**

<img width="698" height="416" alt="image" src="https://github.com/user-attachments/assets/a2413029-8ced-44c8-be30-f70edbeeb390" />


**Question 9**
---
<img width="1218" height="490" alt="image" src="https://github.com/user-attachments/assets/f9336b08-fecb-44c6-8952-df4537bebd87" />


```sql
select (age/5)*5 as 'age_group',sum(salary) as 'SUM(salary)'
from customer1
group by (age/5)*5
having sum(salary)>5000
```

**Output:**

<img width="776" height="452" alt="image" src="https://github.com/user-attachments/assets/3af430e9-1c31-40d3-975c-fb6131444a4c" />


**Question 10**
---
<img width="1132" height="527" alt="image" src="https://github.com/user-attachments/assets/322ccb9a-52cb-4b98-a2b4-119aed0f4434" />


```sql
select address,SUM(salary) as 'SUM(salary)'
from customer1
group by address
having SUM(salary) > 2000
```

**Output:**

<img width="673" height="564" alt="image" src="https://github.com/user-attachments/assets/9c8dd302-5f95-4c9a-98b0-31d042b32605" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
