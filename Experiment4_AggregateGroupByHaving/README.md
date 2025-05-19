# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

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
![Screenshot 2025-05-19 101532](https://github.com/user-attachments/assets/78d60dd9-b17e-440d-875d-3edd2b2a223a)

```sql
select Diagnosis,count(*) as DiagnosisCount
from MedicalRecords 
group by Diagnosis
order by DiagnosisCount desc
limit 1;
```

**Output:**
![Screenshot 2025-05-19 101549](https://github.com/user-attachments/assets/cc3d4ad1-df1f-49d9-9e2e-eecca0684aff)

**Question 2**
---
![Screenshot 2025-05-19 101747](https://github.com/user-attachments/assets/88ed3521-572a-4880-a6d4-517093869be5)


```sql
select count(*) as COUNT
from customer
where city<>'Noida';
```

**Output:**

![Screenshot 2025-05-19 101859](https://github.com/user-attachments/assets/36a71fae-a051-461c-8633-b355da7d7820)

**Question 3**
---
Write a SQL query to find the difference between the maximum and minimum price of fruits?

Table: fruits

name        type
----------  ----------
id          INTEGER
name        TEXT
unit        TEXT
inventory   INTEGER
price       REAL
 

For example:

Result
price_diff
----------
4.65


```sql
select MAX(price)-MIN(price) as price_diff
from fruits;
```

**Output:**

![Screenshot 2025-05-19 102028](https://github.com/user-attachments/assets/4678b64b-5341-4ee6-a398-15f9c2bb5324)

**Question 4**
---
![Screenshot 2025-05-19 102038](https://github.com/user-attachments/assets/181f202e-8947-417a-a5fd-2d6d4bc34a96)


```sql
select SUM(workhour) as 'Total working hours' from employee1
```

**Output:**

![Screenshot 2025-05-19 102047](https://github.com/user-attachments/assets/ca47c888-428d-42a2-905d-f7d249e24618)


**Question 5**
---
![Screenshot 2025-05-19 102056](https://github.com/user-attachments/assets/2eea2987-947c-4cef-9d9b-ec56eac3e5c2)


```sql
select AVG(purch_amt) as AVERAGE
from orders;
```

**Output:**

![Screenshot 2025-05-19 102103](https://github.com/user-attachments/assets/826acd89-46f7-45d2-8f1a-138f2815eb72)


**Question 6**
---
![Screenshot 2025-05-19 102114](https://github.com/user-attachments/assets/10b6b21d-0e83-4287-8070-3c36f7564aa2)


```sql
select city ,AVG(income)
from employee
group by city
having AVG(income)>500000
```

**Output:**
![Screenshot 2025-05-19 102121](https://github.com/user-attachments/assets/22e48860-932c-42f4-9fb9-65411889b467)



**Question 7**
---
![Screenshot 2025-05-19 102134](https://github.com/user-attachments/assets/6323fe60-c48b-4c9c-b7bd-6097c0ba247d)


```sql
select occupation,AVG(workhour)
from employee1
group by occupation
having AVG(workhour) between 10 and 12;
```

**Output:**

![Screenshot 2025-05-19 102143](https://github.com/user-attachments/assets/c42f1dfb-53dc-4639-8e2f-ac44210bcc2e)


**Question 8**
---
![Screenshot 2025-05-19 102153](https://github.com/user-attachments/assets/8cf859e6-78c2-42e1-a5c2-02e7cf9de35f)


```sql
select occupation ,MIN(workhour)
from employee1
group by occupation
having MIN(workhour)>8;
```

**Output:**

![Screenshot 2025-05-19 102200](https://github.com/user-attachments/assets/873de643-ed24-4a6a-9618-45311c9e5b28)

**Question 9**
---
-- Paste Question 9 here

```sql
select Medication, COUNT(*)as TotalPrescriptions
from Prescriptions
group by Medication;
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
select Frequency,COUNT(*)as TotalPrescriptions
from Prescriptions 
group by Frequency
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
