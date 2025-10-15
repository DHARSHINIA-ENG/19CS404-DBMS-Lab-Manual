# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="1204" height="633" alt="image" src="https://github.com/user-attachments/assets/9d8374c3-654c-4cfb-8700-33972f1b482a" />


```sql
update purchases
set per_unit_price= 25,total_price=Quantity*25
where purchase_date = '2022-08-15' and product_id = 12;
```

**Output:**

<img width="1213" height="548" alt="image" src="https://github.com/user-attachments/assets/98e60d46-cb65-4616-b927-15655375abe2" />


**Question 2**
---
<img width="1167" height="522" alt="image" src="https://github.com/user-attachments/assets/b467e5df-6d1f-4202-a3b9-4e84ba276ee1" />


```sql
update Products
set reorder_lvl=20
where quantity<10 and category='Snacks';
```

**Output:**

<img width="1210" height="582" alt="image" src="https://github.com/user-attachments/assets/5cb03d36-ce3c-4f68-b672-6577ba083f14" />


**Question 3**
---
<img width="883" height="470" alt="image" src="https://github.com/user-attachments/assets/c95438cb-84d7-4d16-8305-2a6ab26181d4" />


```sql
update suppliers
set supplier_name= upper(supplier_name)
where contact_person like '%Singh%'
```

**Output:**

<img width="1207" height="383" alt="image" src="https://github.com/user-attachments/assets/c01cb37f-f7a8-4f16-8051-9264436396d2" />


**Question 4**
---
<img width="986" height="486" alt="image" src="https://github.com/user-attachments/assets/49500145-8740-4b37-9eab-81ab951a67ad" />


```sql
update Suppliers
set address='58 Lakeview, Magnolia'
where supplier_id=5;
```

**Output:**

<img width="1221" height="488" alt="image" src="https://github.com/user-attachments/assets/46ad46b7-143a-41cc-88f9-b3f2c08a9c21" />


**Question 5**
---
<img width="1185" height="571" alt="image" src="https://github.com/user-attachments/assets/33736943-a23b-4d68-9b26-759edd28db44" />


```sql
update Products
set reorder_lvl= reorder_lvl*0.7
where cost_price>50 and quantity<100;
```

**Output:**

<img width="1206" height="516" alt="image" src="https://github.com/user-attachments/assets/2fb71a07-9967-4345-ac94-99a212fb2dc5" />


**Question 6**
---
<img width="824" height="498" alt="image" src="https://github.com/user-attachments/assets/c95ac884-5cae-439d-9113-367c599df77b" />


```sql
delete from Doctors
where doctor_id between 2 and 4
```

**Output:**

<img width="1206" height="806" alt="image" src="https://github.com/user-attachments/assets/b40196bc-3c86-46f1-8688-423ea9f86840" />


**Question 7**
---
<img width="802" height="564" alt="image" src="https://github.com/user-attachments/assets/f766bfdb-f04b-4a85-bf97-72d98f953184" />


```sql
delete from doctors
where last_name is null
```

**Output:**

<img width="1235" height="750" alt="image" src="https://github.com/user-attachments/assets/022d2836-3213-4a08-bcd6-0e9fa7401635" />


**Question 8**
---
<img width="1202" height="490" alt="image" src="https://github.com/user-attachments/assets/2b71f7b7-c4bb-4d3b-a112-e01c73368a65" />


```sql
delete from Customer
where grade%2!=0
```

**Output:**

<img width="1230" height="485" alt="image" src="https://github.com/user-attachments/assets/d7849c5d-4db2-4921-b989-b918407df85a" />


**Question 9**
---
<img width="1200" height="524" alt="image" src="https://github.com/user-attachments/assets/9216616a-d8c4-4079-97f7-594947ed2457" />


```sql
delete from Customer
where GRADE=3 and CUST_NAME like '%BBB%'and PAYMENT_AMT>2000
```

**Output:**

<img width="1205" height="515" alt="image" src="https://github.com/user-attachments/assets/89dd98e4-dec3-478c-929a-8f312268d92f" />


**Question 10**
---
<img width="1130" height="466" alt="image" src="https://github.com/user-attachments/assets/b924a4f0-fbbc-4779-83c1-95ac8d3e068a" />


```sql
select* from EmployeeInfo
where NOT EmpFname in ('Sanjay','Sonia') 
```

**Output:**

<img width="1206" height="345" alt="image" src="https://github.com/user-attachments/assets/51c68f4f-5a7b-467d-9145-ff67f055e386" />



END SEB EXAMINATION :
<img width="1173" height="83" alt="image" src="https://github.com/user-attachments/assets/faae72dd-6d79-4a47-90ef-3281b58d2774" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
