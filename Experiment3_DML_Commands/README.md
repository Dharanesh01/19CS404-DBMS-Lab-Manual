# Experiment 3: DML Commands

**REG NO:212222060042**

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
![image](https://github.com/user-attachments/assets/0b5b4cd0-6652-47db-a19a-e2e67b3f2e78)


```sql
UPDATE products
SET availability=availability*2
WHERE product_id=1;
```

**Output:**

![image](https://github.com/user-attachments/assets/00e1cf05-e944-4cff-8426-2a2e0a35d044)


**Question 2**
---
![image](https://github.com/user-attachments/assets/efa4aa56-9331-4360-8909-ad3964807711)


```sql
UPDATE Employees
SET SALARY = SALARY * 2
WHERE job_id ='MK_MAN' and department_id=20;
```

**Output:**

![image](https://github.com/user-attachments/assets/4fb430c0-2908-4f48-9620-7393b106f7c1)


**Question 3**
---
![image](https://github.com/user-attachments/assets/5a1e2ee6-6f5d-4161-af01-4ace33785b1d)


```sql
UPDATE suppliers
SET supplier_name=UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%'
```

**Output:**

![image](https://github.com/user-attachments/assets/d71bcee3-5675-490e-bcef-b6877ab69b5e)

**Question 4**
---
![image](https://github.com/user-attachments/assets/ca19d281-1c65-40d9-8229-e7f969321f05)


```sql
UPDATE Products
SET sell_price=CAST(cost_price*1.35 AS INTEGER)
WHERE((sell_price-cost_price)/sell_price)<0.30;
```

**Output:**

![image](https://github.com/user-attachments/assets/56fd161b-eca3-4709-8927-8cd3086efb08)


**Question 5**
---
![image](https://github.com/user-attachments/assets/ed9a2f5d-6212-4d97-9f65-d12bce310baa)


```sql
DELETE FROM Customer
WHERE (GRADE IS '2' AND CUST_NAME LIKE 'M%') AND PAYMENT_AMT <5000;
```

**Output:**
![image](https://github.com/user-attachments/assets/786ca60a-eb30-4e70-8ebe-e59398a71128)



**Question 6**
---
![Screenshot 2025-05-19 131457](https://github.com/user-attachments/assets/95190ee1-7133-402d-b9da-c42136009c78)

```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('UK','USA','Canada') AND GRADE >=3;
```

**Output:**
![Screenshot 2025-05-19 131541](https://github.com/user-attachments/assets/a214f2c4-5000-4fe2-a410-f13ce46b54e0)


**Question 7**
---
![Screenshot 2025-05-19 131555](https://github.com/user-attachments/assets/451f51c9-f63c-4699-9fa7-344f8db4f905)


```sql
DELETE FROM Doctors
WHERE doctor_id =1;
```

**Output:**

![Screenshot 2025-05-19 131654](https://github.com/user-attachments/assets/23563222-8625-493c-a5bc-57342f9a0ea3)


**Question 8**
---
![Screenshot 2025-05-19 131705](https://github.com/user-attachments/assets/276dba46-aa91-420a-8c34-7c348219ac4d)


```sql
DELETE FROM Customer
WHERE CUST_CITY <> 'New York' AND OUTSTANDING_AMT>5000;
```

**Output:**

![Screenshot 2025-05-19 131714](https://github.com/user-attachments/assets/d490a7a2-a2e3-409e-88f6-5bffc177316a)


**Question 9**
---

![Screenshot 2025-05-19 131723](https://github.com/user-attachments/assets/3d14a18f-8ed9-4d02-93a6-03adf0d492ba)

```sql
SELECT EmpID, EmpFname,EmpLname,Department,Project,Address,DOB,Gender
FROM EmployeeInfo
WHERE EmpLname LIKE '____A'  ;
```

**Output:**

![Screenshot 2025-05-19 131730](https://github.com/user-attachments/assets/7023ad6a-7b3c-4682-bdbd-ea4c6c62190c)


**Question 10**
---
![Screenshot 2025-05-19 131740](https://github.com/user-attachments/assets/d3456540-c1ff-483d-b639-99bc71e9ccb6)

```sql
SELECT salesman_id,name,city,commission
FROM salesman
WHERE commission BETWEEN 0.12 AND 0.14;
```

**Output:**

![Screenshot 2025-05-19 131749](https://github.com/user-attachments/assets/83d81cda-ef2e-462c-b0ca-3a12099555e5)

**SEB GRADE**

![Screenshot 2025-05-19 112946](https://github.com/user-attachments/assets/5aa0995d-1522-4b81-9968-e5c2ff1a3987)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
