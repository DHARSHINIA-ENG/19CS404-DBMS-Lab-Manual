# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1217" height="810" alt="image" src="https://github.com/user-attachments/assets/275ab1e3-177b-4472-908a-68f8c7887ed8" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in 
(select salesman_id from salesman
where city="New York");
```

**Output:**

<img width="1259" height="547" alt="image" src="https://github.com/user-attachments/assets/de5ef4b4-2da1-4915-bcdd-bab569ffc9fd" />


**Question 2**
---
<img width="1010" height="758" alt="image" src="https://github.com/user-attachments/assets/4e58f2c5-50ec-41fb-8807-5e08376c7be7" />


```sql
select * from CUSTOMERS
where SALARY > 1500;
```

**Output:**

<img width="1251" height="686" alt="image" src="https://github.com/user-attachments/assets/3df59797-2a9f-42eb-b1d2-cc04fdd2149a" />


**Question 3**
---
<img width="1170" height="752" alt="image" src="https://github.com/user-attachments/assets/ee221efc-7903-4913-bde2-fe48a878e187" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in 
(select salesman_id from salesman
where name="Paul Adam");
```

**Output:**

<img width="1261" height="479" alt="image" src="https://github.com/user-attachments/assets/c8993e00-4903-41d8-8da4-95bfac3b8890" />


**Question 4**
---
<img width="1246" height="637" alt="image" src="https://github.com/user-attachments/assets/3c412e1b-a895-4928-bbb3-0fadb87d869d" />


```sql
select *
from GRADES g
where grade=(
select max(grade) from GRADES
WHERE subject=g.subject);
```

**Output:**

<img width="1254" height="522" alt="image" src="https://github.com/user-attachments/assets/a42130ef-e2ee-4147-a3f1-6170f9fc9d89" />


**Question 5**
---
<img width="997" height="686" alt="image" src="https://github.com/user-attachments/assets/1ec474fa-211c-4bb7-ae77-f7e41e3080cc" />


```sql
select commission
from salesman
where salesman_id in (
select salesman_id from customer
where city ='Paris');
```

**Output:**

<img width="540" height="445" alt="image" src="https://github.com/user-attachments/assets/2161f58d-4892-4ca2-9402-487507a01e99" />


**Question 6**
---
<img width="1227" height="811" alt="image" src="https://github.com/user-attachments/assets/2fef94ac-39bb-4495-bcbb-09c3433406e1" />


```sql
select ord_no, purch_amt, ord_date, customer_id ,salesman_id
from ORDERS
where salesman_id in (
select salesman_id from SALESMAN
where city ='New York');
```

**Output:**

<img width="1262" height="579" alt="image" src="https://github.com/user-attachments/assets/0d03f4d3-983c-450c-a6bf-58ad191b711d" />


**Question 7**
---
<img width="1004" height="755" alt="image" src="https://github.com/user-attachments/assets/3ae953fb-0c28-4124-a2dc-5fe34c174198" />


```sql
select * from CUSTOMERS
WHERE age<30;
```

**Output:**

<img width="1265" height="598" alt="image" src="https://github.com/user-attachments/assets/09cc30d7-70d5-41b1-8ad1-1f04272b6705" />


**Question 8**
---
<img width="1285" height="814" alt="image" src="https://github.com/user-attachments/assets/6afcacb2-6928-4fe2-be1a-50e79069259d" />


```sql
select ord_no, purch_amt, ord_date, salesman_id
from orders
where salesman_id in (
select salesman_id from salesman
where commission = (select MAX(commission) from salesman)
);
```

**Output:**

<img width="1025" height="563" alt="image" src="https://github.com/user-attachments/assets/7ad2480d-b9c2-4bad-aeb8-a0efa823869c" />


**Question 9**
---
<img width="1222" height="676" alt="image" src="https://github.com/user-attachments/assets/65a6f5bb-3a03-44bd-8ed0-849e2175e15b" />


```sql
select * from Employee
where age <(
select avg(age) from Employee
where income>250000);
```

**Output:**

<img width="1256" height="611" alt="image" src="https://github.com/user-attachments/assets/848dafbd-9b61-415a-8736-0ac4d7d6d4bf" />

**Question 10**
---
<img width="1260" height="692" alt="image" src="https://github.com/user-attachments/assets/1cc7d11f-24e4-4d56-b42f-f2a50add734f" />


```sql
select student_name, grade
from GRADES g
where grade=(
select max(grade) from GRADES
WHERE subject=g.subject);
```

**Output:**

<img width="861" height="514" alt="image" src="https://github.com/user-attachments/assets/495e94a8-af4e-43f5-a7da-f6f2b95e6d2c" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
