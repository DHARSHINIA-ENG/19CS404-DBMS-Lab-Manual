# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1277" height="507" alt="image" src="https://github.com/user-attachments/assets/87bd9114-4ab9-4b7e-8952-30ce039b3e8f" />


```sql
select c.cust_name,o.ord_no,o.ord_date,o.purch_amt
from orders o
left join customer c on c.customer_id=o.customer_id
where o.purch_amt>1000;
```

**Output:**

<img width="1277" height="744" alt="image" src="https://github.com/user-attachments/assets/3f64fcb1-83e1-440c-a775-29ec0714e037" />


**Question 2**
---
<img width="1266" height="836" alt="image" src="https://github.com/user-attachments/assets/d6578f8c-c595-4aad-bb5f-34979356990a" />


```sql
select c.cust_name,c.city,c.grade,s.name as 'Salesman', s.city 
from salesman s
join customer c on c.salesman_id=s.salesman_id
where c.grade<300
order by c.customer_id;

```

**Output:**

<img width="1240" height="745" alt="image" src="https://github.com/user-attachments/assets/1f3f2a82-703e-4bf4-9fc8-5d48bf53a4bc" />


**Question 3**
---
<img width="1266" height="459" alt="image" src="https://github.com/user-attachments/assets/c3f6c788-4da7-4f2e-8b49-5409b0139f70" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt
from orders o
left join customer c on c.customer_id=o.customer_id
where c.city='London';
```

**Output:**

<img width="1262" height="579" alt="image" src="https://github.com/user-attachments/assets/d0c32c32-d080-497f-8f63-361e2728492f" />


**Question 4**
---
<img width="1222" height="761" alt="image" src="https://github.com/user-attachments/assets/0b02430b-c6a3-43a4-903f-cb440dc942c5" />


```sql
select c.cust_name as 'Customer Name',c.city,s.name as 'Salesman',s.commission
from salesman s 
join customer c on c.salesman_id =s.salesman_id 
where s.commission>0.12;

```

**Output:**

<img width="1268" height="807" alt="image" src="https://github.com/user-attachments/assets/e69ac6b1-e992-46f4-b9a5-bc8a5ab19b22" />


**Question 5**
---
<img width="1226" height="871" alt="image" src="https://github.com/user-attachments/assets/45ff9b05-5668-4cda-b520-02929de6b2a0" />


```sql
select c.cust_name as 'Customer Name',c.city,s.name as 'Salesman',s.commission
from salesman s 
join customer c on c.salesman_id =s.salesman_id 

```

**Output:**

<img width="1262" height="806" alt="image" src="https://github.com/user-attachments/assets/9daa0551-951b-4178-9c69-eaab78591cee" />


**Question 6**
---
<img width="1209" height="778" alt="image" src="https://github.com/user-attachments/assets/aac43c03-8140-4021-91e6-eac1eee4ab5f" />


```sql
select o.ord_no,o.ord_date,o.purch_amt,c.cust_name as 'Customer Name',c.grade,s.name as 'Salesman',s.commission
from salesman s
join customer c on c.salesman_id=s.salesman_id
join orders o on o.customer_id=c.customer_id;
```

**Output:**

<img width="1234" height="748" alt="image" src="https://github.com/user-attachments/assets/7a8c7fa3-2cf3-4a0c-aaf5-7ccdec51bb44" />


**Question 7**
---
<img width="1272" height="811" alt="image" src="https://github.com/user-attachments/assets/f08db1d8-2d27-4068-96ad-99d4aaab81a6" />


```sql
select p.first_name,s.*
from surgeries s
join patients p on p.patient_id=s.patient_id
where p.discharge_date between '2024-03-01' and '2024-03-31';
```

**Output:**

<img width="1257" height="518" alt="image" src="https://github.com/user-attachments/assets/c96f41ce-5db6-417a-b7d0-7e0489e67c11" />


**Question 8**
---
<img width="1235" height="735" alt="image" src="https://github.com/user-attachments/assets/958cc0b8-ac49-47c7-afe3-5b833f5a5d30" />


```sql
select p.first_name as 'patient_name',t.*
from test_results t
join patients p on p.patient_id=t.patient_id
where p.admission_date between '2024-01-01' and '2024-01-31';
```

**Output:**

<img width="1264" height="504" alt="image" src="https://github.com/user-attachments/assets/042496ec-0213-4924-a23c-78d24435df39" />


**Question 9**
---
<img width="1046" height="857" alt="image" src="https://github.com/user-attachments/assets/84619cc7-5522-4dd8-be8f-f08730bef303" />


```sql
select s.name as 'Salesman', c.cust_name,s.city
from salesman s
join customer c on s.city=c.city;
```

**Output:**

<img width="1119" height="718" alt="image" src="https://github.com/user-attachments/assets/43566928-c06d-4adb-a9b7-e1d81219e8fa" />


**Question 10**
---<img width="1230" height="787" alt="image" src="https://github.com/user-attachments/assets/20e67677-14e7-4e47-ab53-b50ae1ca270b" />


```sql
select p.first_name from patients p
join surgeries s on p.patient_id=s.patient_id
where s.surgery_date='2024-01-15';
```

**Output:**

<img width="591" height="504" alt="image" src="https://github.com/user-attachments/assets/5661d7d9-d187-4789-9db9-d69e754580f4" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
