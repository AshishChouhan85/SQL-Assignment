# SQL-Assignment

![image](https://user-images.githubusercontent.com/120089356/218325548-d4b9d5da-9388-4a32-bb32-c1efb9bd77af.png)

```SQL
# CREATING A DATABASE
CREATE SCHEMA DB;
USE DB;

# CREATING THE TABLE
CREATE TABLE TABLE1(EmpID INT PRIMARY KEY, Name_ VARCHAR(1),
Gender VARCHAR(15), Department VARCHAR(20));

# ENTERING THE VALUES
INSERT INTO TABLE1 VALUES(1,'X','Female','Finance');
INSERT INTO TABLE1 VALUES(2,'Y','Male','IT');
INSERT INTO TABLE1 VALUES(3,'Z','Male','HR');
INSERT INTO TABLE1 VALUES(4,'W','Female','IT');

# VIEWING THE TABLE
SELECT * FROM TABLE1;

# ANSWER 1
SELECT Department,
COUNT(CASE WHEN Gender = 'Male' THEN 1 END) AS Num_of_male,
COUNT(CASE WHEN Gender = 'Female' THEN 1 END) AS Num_of_Female
FROM TABLE1
GROUP BY Department;
```

OUTPUT:

![image](https://user-images.githubusercontent.com/120089356/218325697-48a2cbea-e728-4bc7-a3bc-4c29cf542a97.png)
