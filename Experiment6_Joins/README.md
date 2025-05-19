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
![Screenshot 2025-05-19 105423](https://github.com/user-attachments/assets/68bd6056-5fe2-4d9c-822c-7e467ba5bca6)


```sql
select s.name as Salesman,c.cust_name,s.city
from salesman s
inner join customer c on s.city=c.city;
```

**Output:**

![Screenshot 2025-05-19 105436](https://github.com/user-attachments/assets/affbb51b-3a3f-40f1-b864-049c813d47f0)


**Question 2**
---
![Screenshot 2025-05-19 105449](https://github.com/user-attachments/assets/b5fba8b8-5d80-4685-9a8b-546b1cbf6d12)


```sql
select c.*
from customer as c
left join orders as o on c.salesman_id=o.salesman_id
where o.ord_date between '2012-08-01' and '2012-08-30';
```

**Output:**

![Screenshot 2025-05-19 105500](https://github.com/user-attachments/assets/be870f73-a4ef-4e80-8bbb-4fe5d8338847)


**Question 3**
---
![Screenshot 2025-05-19 105511](https://github.com/user-attachments/assets/8963824f-f614-4930-be95-993132ca2c19)


```sql
SELECT 
    c.cust_name AS "Customer Name", 
    c.city, 
    s.name AS "Salesman", 
    s.commission
FROM 
    customer c
JOIN 
    salesman s 
ON 
    c.salesman_id = s.salesman_id;
```

**Output:**

![Screenshot 2025-05-19 105532](https://github.com/user-attachments/assets/fc3265e0-ed07-4eba-bb11-27c3fea3d395)


**Question 4**
---
![Screenshot 2025-05-19 105547](https://github.com/user-attachments/assets/c1778f23-2cc1-4a67-a487-6574ff990821)


```sql
select n.nurse_id,n.first_name,n.last_name,d.department_id,d.department_name
from nurses as n
inner join departments as d on n.department_id=d.department_id;
```

**Output:**

![Screenshot 2025-05-19 105556](https://github.com/user-attachments/assets/fb7bb187-5288-4aba-a911-61b9e2402f65)


**Question 5**
---
![Screenshot 2025-05-19 105615](https://github.com/user-attachments/assets/4f2e9bad-7cd8-4e99-a7f6-76de0684e72d)


```sql
select c.cust_name,c.city,c.grade,s.name as Salesman,s.city
from customer as c
inner join salesman as s on c.salesman_id=s.salesman_id
order by c.customer_id asc;
```

**Output:**

![Screenshot 2025-05-19 105629](https://github.com/user-attachments/assets/68b76e43-8e1f-454f-90dd-4850f8e521c1)


**Question 6**
---
![Screenshot 2025-05-19 105701](https://github.com/user-attachments/assets/3bc861ba-e18c-4bcd-a682-3509a0bb477a)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![Screenshot 2025-05-19 105716](https://github.com/user-attachments/assets/ed3e8c2d-087f-422b-ad17-8aebb2dac8d8)


**Question 7**
---
![Screenshot 2025-05-19 105727](https://github.com/user-attachments/assets/93cd6729-fa1c-4979-b194-841e22ce37e0)


```sql
SELECT 
    t.*
FROM 
    test_results t
INNER JOIN 
    patients p ON t.patient_id = p.patient_id
WHERE 
    p.first_name = 'Alice';
```

**Output:**
![Screenshot 2025-05-19 105740](https://github.com/user-attachments/assets/e8399e36-6195-4d2a-b96d-a993d8f9d545)



**Question 8**
---
![Screenshot 2025-05-19 105753](https://github.com/user-attachments/assets/bbcace64-1b3f-418e-b44f-db555235d803)

```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM 
    patients p
INNER JOIN 
    doctors d ON p.doctor_id = d.doctor_id
WHERE 
    p.discharge_date IS NOT NULL;
```

**Output:**

![Screenshot 2025-05-19 105801](https://github.com/user-attachments/assets/54c0adca-0c0e-4357-91c6-4c1e6c890d89)


**Question 9**
---
![Screenshot 2025-05-19 105815](https://github.com/user-attachments/assets/7c507f73-f9e4-4339-89a2-59b480ccc0e2)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

![Screenshot 2025-05-19 105832](https://github.com/user-attachments/assets/f3df8676-de76-4bb0-a043-8dab9d08b722)


**Question 10**
---
![Screenshot 2025-05-19 105845](https://github.com/user-attachments/assets/a593db9b-55dd-46af-94b0-b43e9ae39404)


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.purch_amt > 1000;
```

**Output:**

![Screenshot 2025-05-19 105859](https://github.com/user-attachments/assets/9507f981-3b59-456d-b0e0-ab969e2a2a38)
**SEB GRADE**
![Screenshot 2025-05-19 111930](https://github.com/user-attachments/assets/3bbc11b0-d2c5-44d7-8b98-3512fbcaa8ef)

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
