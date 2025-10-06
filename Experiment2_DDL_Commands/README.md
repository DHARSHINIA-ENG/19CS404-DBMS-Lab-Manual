# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table)

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1218" height="334" alt="image" src="https://github.com/user-attachments/assets/7256c461-7cd3-4e31-a272-0ec9dba1e09d" />



```sql
Create table ProjectAssignments(
AssignmentID  int primary key,
EmployeeID int,
ProjectID int,
AssignmentDate DATE NOT NULL,
foreign key(EmployeeID) references Employees(EmployeeID)
foreign key(ProjectID) references Projects(ProjectID));

```

**Output:**
<img width="1197" height="307" alt="image" src="https://github.com/user-attachments/assets/968287bb-84c9-4290-8b48-539f58b19c5c" />


**Question 2**
---
<img width="1083" height="255" alt="image" src="https://github.com/user-attachments/assets/14afbf6c-5671-47b7-ad5d-647a93cb5b27" />


```sql
insert into Products(ProductID   ,Name ,   Category ,  Price,  Stock )
values(101 , 'Laptop' , 'Electronics' ,1500,   50 );
```

**Output:**
<img width="1217" height="316" alt="image" src="https://github.com/user-attachments/assets/317e0c11-2cd2-4258-88a1-9093e53e1458" />


**Question 3**
---
<img width="1186" height="500" alt="image" src="https://github.com/user-attachments/assets/96835d39-3042-4683-bfb8-d6a825f0f8a9" />


```sql
alter table employee add column department_id INTEGER;
alter table employee add column manager_id INTEGER DEFAULT NULL;
```

**Output:**

<img width="1225" height="375" alt="image" src="https://github.com/user-attachments/assets/caf639de-ae0e-4cf9-a83a-5e7c7371ea9f" />


**Question 4**
---
<img width="1049" height="397" alt="image" src="https://github.com/user-attachments/assets/b3a54461-4ad2-4943-96e0-c9dc71166b78" />


```sql
alter table Student_details add column Date_of_birth  Date ;
```

**Output:**

<img width="1208" height="369" alt="image" src="https://github.com/user-attachments/assets/1e542fb8-7304-4e9a-ae4c-46dd6f8479ce" />


**Question 5**
---
<img width="998" height="463" alt="image" src="https://github.com/user-attachments/assets/a0f5de18-d9f0-48f5-9558-51fbe5f46d4f" />


```sql
create table Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT); 
```

**Output:**

<img width="1209" height="441" alt="image" src="https://github.com/user-attachments/assets/02cfef70-4fc3-4ba7-aa7b-c445341543ab" />


**Question 6**
---
<img width="782" height="362" alt="image" src="https://github.com/user-attachments/assets/165752ca-f450-4cb4-b76f-d1ab6546499e" />


```sql
insert into Products(ProductID ,ProductName,Price,Stock )
select ProductID ,ProductName,Price,Stock 
from Discontinued_products;
```

**Output:**

<img width="1196" height="322" alt="image" src="https://github.com/user-attachments/assets/b5819656-7d11-438c-b0c3-354166bf6842" />


**Question 7**
---
<img width="1228" height="550" alt="image" src="https://github.com/user-attachments/assets/8c6dd346-64e7-4821-bad1-2dcc95a15093" />


```sql
create table products(
product_id INTEGER primary key,
product_name TEXT not NULL,
list_price DECIMAL (10, 2) not NULL,
discount DECIMAL (10, 2)  default 0  not NULL,
check(list_price>=discount and discount>=0 and list_price>=0));
```

**Output:**

<img width="1207" height="329" alt="image" src="https://github.com/user-attachments/assets/558b373a-1e6d-4a0a-a477-0eccd963cbd9" />


**Question 8**
---
<img width="1220" height="516" alt="image" src="https://github.com/user-attachments/assets/eb6fbe30-9c74-4ed7-b976-29a6c7dcced7" />


```sql
insert into Employee(EmployeeID , Name ,Position , Department, Salary )
values(5, 'George Clark',  'Consultant', null,null),(7  ,'Noah Davis'  ,'Manager' ,'HR', 60000),(8 , 'Ava Miller', 'Consultant',  'IT',null); 
```

**Output:**

<img width="1213" height="333" alt="image" src="https://github.com/user-attachments/assets/13d46323-93ec-47a2-9261-cbc81695498b" />


**Question 9**
---


```sql
create table item(
item_id TEXT primary key,
item_desc TEXT not null,
rate INTEGER not null,
icom_id TEXT check(length(icom_id)=4),
foreign key(icom_id) references company(com_id) 
On update cascade
On delete cascade
);

```

**Output:**



**Question 10**
---
<img width="1224" height="449" alt="image" src="https://github.com/user-attachments/assets/33d0dfbf-5c3c-458a-a1ce-7022857d69fc" />


```sql
create table contacts(
contact_id INTEGER  primary key,
first_name  TEXT  not NULL,
last_name TEXT not null,
email TEXT,
phone text not null check(length(phone)>=10));
```

**Output:**

<img width="1217" height="382" alt="image" src="https://github.com/user-attachments/assets/34c629e3-85d1-43a2-861d-e6e749326d4f" />


## Module Examination (SEB)
<img width="1104" height="72" alt="image" src="https://github.com/user-attachments/assets/80fd53d9-ea37-4d81-83a7-82d84d62a633" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
