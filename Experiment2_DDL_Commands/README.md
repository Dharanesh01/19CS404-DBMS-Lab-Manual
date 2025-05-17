# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

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
---
![Screenshot 2025-05-17 201705](https://github.com/user-attachments/assets/a279c2a9-58bb-437e-bc02-6ab23237bf74)

```
create table Products(
ProductID integer primary key,
ProductName text NOT NULL,
Price real check(Price >0),
Stock integer check(Stock >=0)
);
```

**Output:**
![Screenshot 2025-05-17 201827](https://github.com/user-attachments/assets/eb54e399-5176-4465-8dac-624ca3153273)

**Question 2**
---
![Screenshot 2025-05-17 202109](https://github.com/user-attachments/assets/159b8d48-90c6-45b9-abb2-924ad9b8407b)

```sql
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)
values(205,'Olivia Green','F',NULL,NULL);
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)
values(207,'Liam Smith','M','Mathematics',85);
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)
values(208,'Sophia Johnson','F','Science',NULL);
```

**Output:**
![Screenshot 2025-05-17 202132](https://github.com/user-attachments/assets/1c211e0a-c428-47f2-a8e1-bf13fbdf1a42)

**Question 3**
---
![Screenshot 2025-05-17 202302](https://github.com/user-attachments/assets/7609915f-8021-4909-962e-160884e2015b)

```sql
insert into Books( ISBN, Title, Author, Publisher, YearPublished)
select  ISBN, Title, Author, Publisher, YearPublished
from Out_of_print_books
```

**Output:**
![Screenshot 2025-05-17 202319](https://github.com/user-attachments/assets/92996dc8-c2fc-43ac-a0d4-b4bc01af90d9)

**Question 4**
---
![Screenshot 2025-05-17 202447](https://github.com/user-attachments/assets/5b6c4553-4132-4b38-a20a-cf6e716c3ee0)

```sql
create table item(
item_id text primary key,
item_desc text not null,
rate integer not null,
icom_id text check(length(icom_id)=4),
foreign key (icom_id) references company(com_id)on update set null on delete set null
);
```

**Output:**
![Screenshot 2025-05-17 202515](https://github.com/user-attachments/assets/4207b375-3491-425d-9e6c-14310a38b57a)

**Question 5**
---
![Screenshot 2025-05-17 202724](https://github.com/user-attachments/assets/58d589de-3a04-4203-89b4-a8fe0943330e)

```sql
alter table Student_details
add column Date_of_birth Date;
```

**Output:**
![Screenshot 2025-05-17 202742](https://github.com/user-attachments/assets/457cc408-b846-441e-8192-c5dbecd5c4f1)

**Question 6**
---
![Screenshot 2025-05-17 202902](https://github.com/user-attachments/assets/5a92829d-77bb-415e-be26-699292d97762)

```sql
alter table customer
add column discount DECIMAL(5,2);
```

**Output:**

![Screenshot 2025-05-17 202916](https://github.com/user-attachments/assets/5c7f8d8b-40e6-460d-bb2f-0e6b45565258)

**Question 7**
---
![Screenshot 2025-05-17 203107](https://github.com/user-attachments/assets/30a8f2fc-c3c8-4891-adae-945d3b75b329)

```sql
create table contacts(
contact_id integer primary key,
first_name text not null,
last_name text not null,
email text,
phone text not null check(length(phone)>=(10))
);
```

**Output:**

![Screenshot 2025-05-17 203118](https://github.com/user-attachments/assets/c757207f-8dc6-4bdb-b9e9-0adb481fb2ff)

**Question 8**
---
![Screenshot 2025-05-17 203408](https://github.com/user-attachments/assets/544dfea1-59ea-4bc3-87c6-80ebef6e4a9a)

```sql
create table Shipments(
ShipmentID integer primary key,
ShipmentDate date,
SupplierId integer,
OrderID integer,
foreign key (SupplierId) references Suppliers(SupplierID),
foreign key (OrderId) references Orders(OrderID)
);
```

**Output:**
![Screenshot 2025-05-17 203423](https://github.com/user-attachments/assets/f8da5273-68c0-4080-ba8c-71c0cdad7430)

**Question 9**
---
![Screenshot 2025-05-17 203515](https://github.com/user-attachments/assets/32593d7d-a410-4167-954e-5a0a7e227627)

```sql
insert into Employee(EmployeeID,Name,Position)
values(4,'Emily White','Analyst');
```

**Output:**

![Screenshot 2025-05-17 203524](https://github.com/user-attachments/assets/aa303172-7169-4109-9de4-6029fab4887d)

**Question 10**
---
![Screenshot 2025-05-17 203727](https://github.com/user-attachments/assets/d478f7f4-c7c1-4eea-94d3-a53107b1e4f8)

```sql
create table Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**
![Screenshot 2025-05-17 203805](https://github.com/user-attachments/assets/ff16d3ca-6669-4180-828c-b51ae08a2f27)

**SEB GRADE**
---
![image](https://github.com/user-attachments/assets/be4c66ab-2ca2-48dd-a256-d5328c4d9955)

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
