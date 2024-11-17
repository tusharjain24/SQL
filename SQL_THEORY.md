# DATA

EXAMPLE: A person's name is Tushar, then

Arpit -> Data
name -> property/attribute
person -> Object/Entity

properties of that person:
Name:
Age
Gender
Height
Weight
Occupation
DOB

Conclusion:

i> Data is raw fact which describes properties/attributes of an object/entity.
ii> An Entity is anything that exists in real world.
iii> A Raw fact is truth about an object/world that cannot be changed.

# DATABASE

i> Database is a place where data is stored in systemetic and organised manner. Database stores files inside it.

```
        Data ___________
                        |
                        |
                        |
     +organised     |   |      |<- C
     +systemetic    |   \/     |-> R
                    |          |<- U
                    |          |-> D
                    |          |
                    |__________|
                      DATABASE
```

ii> Basic operations performed on database:
Create/Insert
Read/Retrieve
Update/Modify
Delete/Drop

also universally reffered as CRUD.

# DBMS(Database Management System)

```
              ______________________
              |                     |   Two factors of provided by DBMS:
              |                     |   + Security
              |      |          |   |   + Authorizations
              |      |          |   |
              |      |          |   |
              |      |          |   |
              |      |          |   |
              |      |__________|   |
       QL --->|       DATABASE      |
              |_____________________|
                        DBMS
```

- DBMS:- It is a software which is used to maintain and manage the database.
- In DBMS data stores in the form of files.
- It provides two factors(features) :
  i> Security
  ii> Authorization
- We use QL(Query Language) to communicate with the DBMS.

There are four types of DBMS:
i> NDBMS (Network Database Management System)
ii> HDBMS (Hierarchical Database Management System)
iii>RDBMS (Relational Database Management System)
iv> OODBMS (Object Oriented Database Management System)

- 70% of the industry uses RDBMS.

# RDBMS(Relational Database Management System)

```
              ______________________
              |                     |   Two factors of provided by DBMS:
              |                     |   + Security
              |      |          |   |   + Authorization
              |      |   _ _ _  |   |
              |      |  |_|_|_| |   |
              |      |  |_|_|_| |   |
              |      |  |_|_|_| |   |
              |      |  Table   |   |
              |      |__________|   |
       SQL--->|       DATABASE      |
              |_____________________|
                        RDBMS
```

- It is a type of DBMS software.
- In RDBMS data stores in the form of tables.
- It provides two factors:
  i> Security
  ii> Authorization
- We use SQL(Structured Query Language) to communicate with RDBMS.

- Relational Model is designed by a data scientist called as "E.F. Codd" (Edger Frank Codd) working in IBM.
- In relational model data stores in the form of tables.

- Any DBMS that follows relational model it will become RDBMS
  follows
  DBMS ------------> Relational Model ----------> RDBMS

- Any DBMS that follows of rules of E.F. Codd it will become RDBMS.
  follows
  DBMS ------------> Rules of E.F. Codd ----------> RDBMS

# Terminology in SQL

## Table

- Table: It is a combination of rows and columns.
  |
  \/
  Table_Name
  ```
  _ _ _ _
  |_|_|_|_|_| --> contains Column_Name
  |_|_|_|_|_| --> Rows or Records or Tuple
  |_|_|_|_|_| --> Rows or Records or Tuple
  |_|_|_|_|_| --> Rows or Records or Tuple
  |_|_|_|_|_| --> Rows or Records or Tuple
  |_|_|_|_|_| --> Rows or Records or Tuple
  | |
   \/ \/
  Columns/ properties/ attributes
  ```

## Columns

- It is also reffered as properties, attributes, and fields.
- It represents single property of all the entities.

## Rows

- It is also reffered as tuples and records.
- It represents all the properties of a single entity.

## Cell

- Cell: A cell is the smallest unit of table.
  OR
- We can also say the intersection of rows and columns will generate a cell.

  ```
  _
  |_| ---> Cell
  ```

- In cell we store the data.

# Rules of E.F. Codd

1> The data entered into a cell must be a single valued data to avoid data loss.(Because an operation can be performed on the entire cell so in the following example the cell with two numbers will be replaced by one M. No.)

```
    Student
     _ _ _ _ _ _ _ _ _
    |SID|Sname| M.No. |
    |_ _|_ _ _|_ _ _ _|
    | 1 |Sallu| 123   |
    |_ _|_ _ _|_ _ _ _|
    | 2 |Allu |124,125|->want to replace 125 with 129 but as cell contains 2 no both will be replaced to129.
    |_ _|_ _ _|_ _ _ _|
    | 3 |Kallu|  126  |
    |_ _|_ _ _|_ _ _ _|
          |
          |
          | Can be solved like this
          |
          \/
          Student
     _ _ _ _ _ _ _ _ _ _ _ _ _
    |SID|Sname| M.No. |AL No. |
    |_ _|_ _ _|_ _ _ _|_ _ _ _|
    | 1 |Sallu|  123  |  -    |
    |_ _|_ _ _|_ _ _ _|_ _ _ _|
    | 2 |Allu |  124  |  125  |
    |_ _|_ _ _|_ _ _ _|_ _ _ _|
    | 3 |Kallu|  126  |  -    |
    |_ _|_ _ _|_ _ _ _|_ _ _ _|
```

2> In RDBMS we store everything in the form of table including meta data.

```
     _ _ _ _ _ _ _ _ _
    |SID|Sname| Image |
    |_ _|_ _ _|_ _ _ _|
    | 1 |Sallu|   <>  |
    |_ _|_ _ _|_ _ _ _|
    | 2 |Allu |   <>  |
    |_ _|_ _ _|_ _ _ _|
    | 3 |Kallu|   <>  |
    |_ _|_ _ _|_ _ _ _|

    Details of the Image: ---> (Meta Data generated automatically)

    Img_Name: Img_001
    Size: 2 MB
    Time: 05:17 PM
    Dimension: 400x600
    Device:  Samsung
    Location: CG Road
    Format: JPEG
```

META DATA: (i) Data about the data.(OR) Details about the data.
(ii) Meta Dara is auto-generated
(iii) Meta Data is stored in Meta-Table

```
    Meta-Table
     _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
    |Img_Name|Size|Time |Dimension| Device  |Location | Format  |
    |_ _ _ _ |_ _ |_ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|
    |        |    |     |         |         |         |         |
    |_ _ _ _ |_ _ |_ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|
    |        |    |     |         |         |         |         |
    |_ _ _ _ |_ _ |_ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|_ _ _ _ _|
```

3> According to E.F. Codd we can store the data in multiple tables if needed we can establish connection between the tables by using key attributes.

```
    EMP
     _ _ _ _ _ _ _ _ _
    |EID|EName|  DNo  |
    |_ _|_ _ _|_ _ _ _|
    | 1 |Stark|   20  |
    |_ _|_ _ _|_ _ _ _|
    | 2 |Steve|   30  |
    |_ _|_ _ _|_ _ _ _|
    | 3 |NATS |   10  |
    |_ _|_ _ _|_ _ _ _|

      DEPT
     _ _ _ _ _ _ _ _ _
    |DNo|DName|  LOC  |
    |_ _|_ _ _|_ _ _ _|
    | 10| D1  |  AHM  |
    |_ _|_ _ _|_ _ _ _|
    | 20| D2  | BNGLR |
    |_ _|_ _ _|_ _ _ _|
    | 30| D3  |  MUM  |
    |_ _|_ _ _|_ _ _ _|
```

Key Attributes in the above table DNo.

4> The data entered into a table can be verified in two steps:
i> By assigning data types.
ii> By assigning constraints.

# STATEMENTS

- Statements helps us to perform CRUD operations in the SQL.
- There are five Statements in SQL:
  1> DDL(Data Definition Language)
  2> DML(Data Manipulation Language)
  3> TCL(Transaction Control Language)
  4> DCL(Data Control Language)
  5> DQL(Data Query Language)

```
            ___________
           |           |
           |           |
           |           |
           |        |  |      |<- C
         Data       |  \/     |-> R
                    |         |<- U
                    |         |-> D
                    |         |
                    |_________|
                      Database
```

## DQL(Data Query Language)

- This statement is used to retrieve the data from the database.
- There are four statements in DQL:
  1> Select
  2> Projection
  3> Selection
  4> Joins

- Select: This statement is used to retrieve the data from the table and display it. Select statement cannot be used alone that is why it is used along with projection.
- Projection: This statement is used to retrieve the data from the table by selecting only column. In Projection, the data present under the column will be selected by default.
- Selection: This statement is used to retrieve the data from the table by selecting rows as well as columns.
- Joins: This statement is used to retrieve the data from multiple tables simultaneously.

### PROJECTION

- Definition:
- Syntax:
  SELECT \*/[Distinct] Column_Name/ EXP[Alias] From Table_Name;

- ORDER OF EXECUTION:
  1 - From
  2 - SELECT

- Statement = Clauses
  Clause -> Select, From
  'FROM' Clause executes first followed by 'SELECT' Clause.

- EXAMPLE: Q> Write a query to display names of the employes.

```
        EMP
        _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
        |EID|EName   |  SAL  |  JOB      |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 1 |ABDUL   |  650  | Salesman  |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 2 |JethaJi | 5000  | President |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 3 |Bhindi  | 1200  | CLERK     |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 4 |Babliji |  800  | Analyst   |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 5 |Madhvi  |  1500 | Analyst   |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
        | 6 |Popat   |  1700 | Analyst   |
        |_ _|_ _ _ _ |_ _ _ _|_ _ _ _ _ _|
```

-> Ans:
SELECT EName From EMP;

RESULT Table:

```
 _ _ _ _ _
| EName   |
|_ _ _ _ _|
| ABDUL   |
|_ _ _ _ _|
| JethaJi |
|_ _ _ _ _|
| Bhindi  |
|_ _ _ _ _|
| BabitaJi|
|_ _ _ _ _|
| Madhvi  |
|_ _ _ _ _|
| Popat   |
|_ _ _ _ _|
```

Q> Write a query to display EName and Salary of the employees.
-> SELECT ENAME, SAL FROM EMP;
Note: Comma acts as seperater.
Q> Write a query to display EName and JOB of the employees.
-> SELECT EName, JOB FROM EMP;

```
 _ _ _ _ _ _ _ _ _ _
| EName   | JOB     |
|_ _ _ _ _|_ _ _ _ _|
| ABDUL   | Salesman|
|_ _ _ _ _|_ _ _ _ _|
| JethaJi |President|
|_ _ _ _ _|_ _ _ _ _|
| Bhindi  | CLERK   |
|_ _ _ _ _|_ _ _ _ _|
| BabitaJi| Analyst |
|_ _ _ _ _|_ _ _ _ _|
| Madhvi  | Analyst |
|_ _ _ _ _|_ _ _ _ _|
| Popat   | Analyst |
|_ _ _ _ _|_ _ _ _ _|
```

Q> Write a query to display all the Details of the employees.
-> SELECT \* FROM EMP;

NOTES:

- In Projection, there are two clauses FROM and SELECT.
- FROM clause start the EXECUTION
- For FROM clause we can passs the table name as an argument
- The job of FROM clause is to go the database, search for the table and put the table under execution.
- SELECT clause executes after the execution of FROM clause.
- For SELECT clause we can pass Asterrisk(\*) or column_name or expression(Input) as an argument.
- The job of SELECT clause is to go to the table which is under execution and display the columns mentioned within.
- By this we can say select clause is responsible for the result table.

### DISTINCT

- DISTINCT is a clause which is used to remove duplicated or repeated values from the result table.
- For DISTINCT clause we can pass column_name or expression as an argument.
- We can pass DISTINCT clause in the SELECT clause as a first argument.
- We can pass multiple arguments in the DISTINCT clause but it will remove the duplicating combination.

Q> Write a query to display different Salaries.
-> SELECT DISTINCT SAL FROM EMP;
(OR)
-> SELECT UNIQUE SAL FROM EMP;

- RESULT of FROM clause.
  Certainly! I'll convert the entire file to Markdown format, keeping the tables intact. Here's the converted version:

````markdown
# SQL Clauses and Operations

## RESULT of FROM clause

| EID | EName    | SAL  |
| --- | -------- | ---- |
| 1   | ABDUL    | 800  |
| 2   | JethaJi  | 950  |
| 3   | Bhindi   | 1000 |
| 4   | BabitaJi | 800  |
| 5   | ABDUL    | 800  |
| 6   | Popat    | 1000 |

## RESULT of SELECT clause

| SAL  |
| ---- |
| 800  |
| 950  |
| 1000 |
| 800  |
| 800  |
| 1000 |

## RESULT of DISTINCT Clause from the result table of SELECT clause

| SAL  |
| ---- |
| 800  |
| 950  |
| 1000 |

### Query: SELECT DISTINCT ENAME, SAL FROM EMP;

## Result of FROM clause

| EID | EName    | SAL  |
| --- | -------- | ---- |
| 1   | ABDUL    | 800  |
| 2   | JethaJi  | 950  |
| 3   | Bhindi   | 1000 |
| 4   | BabitaJi | 800  |
| 5   | ABDUL    | 800  |
| 6   | Popat    | 1000 |

## Result of SELECT clause

| EName    | SAL  |
| -------- | ---- |
| ABDUL    | 800  |
| JethaJi  | 950  |
| Bhindi   | 1000 |
| BabitaJi | 800  |
| ABDUL    | 800  |
| Popat    | 1000 |

## Result of DISTINCT clause

| EName    | SAL  |
| -------- | ---- |
| ABDUL    | 800  |
| JethaJi  | 950  |
| Bhindi   | 1000 |
| BabitaJi | 800  |
| Popat    | 1000 |

## SELECTION

- SELECTION clause is used to retrieve the data from the table by selecting rows as well as columns.

### Syntax:

```sql
SELECT *|[DISTINCT] column_name|EXP [Alias] FROM Table_Name WHERE <filter_condition>;
```
````

### ORDER OF EXECUTION:

1. FROM
2. WHERE
3. SELECT

## WHERE CLAUSE

- It is used to filter the condition.
- It executes ROW-By-ROW.
- In a WHERE clause we can write filter conditions which returns a boolean value (true/false).
- WHERE clause executes after execution of FROM clause.
- In WHERE clause we can also write multiple conditions using Logical Operators.

### Example Queries:

1. Write a query to display the names of employees who works in dept 20.

   ```sql
   SELECT ENAME FROM EMP WHERE DEPTNO = 20;
   ```

2. Write a query to display annual Salary of the employee whose name is "SMITH".

   ```sql
   SELECT SAL*12 as ANNUAL_SALARY FROM EMP WHERE ENAME='SMITH';
   ```

3. Write a query to display the names of the employees working as CLERK.

   ```sql
   SELECT ENAME FROM EMP WHERE JOB='CLERK';
   ```

4. Write a query to display the salary of the employees working as Salesman.

   ```sql
   SELECT SAL FROM EMP WHERE JOB = 'SALESMAN';
   ```

5. Write a query to display details of the employee who earns salary more than 2000.

   ```sql
   SELECT * FROM EMP WHERE SAL > 2000;
   ```

6. Write a query to display details of the employees whose name is JONES.

   ```sql
   SELECT * FROM EMP WHERE ENAME = 'JONES';
   ```

7. Write a query to display details of the employees who hired after 1981.

   ```sql
   SELECT * FROM EMP WHERE HIREDATE > '31-12-81';
   ```

8. Write a query to display NAME and SALARY Along with ANNUAL_SALARY if ANNUAL_SALARY is more than 12000.

   ```sql
   SELECT ENAME, SAL, 12*SAL as ANNUAL_SALARY FROM EMP WHERE (12*SAL) > 120000;
   ```

9. Write a query to display EMPNO of the employees who are working in dept no. 30.

   ```sql
   SELECT EMPNO FROM EMP WHERE DEPTNO = 30;
   ```

10. Write a query to display details of the employees hired before 1981.

    ```sql
    SELECT * FROM EMP WHERE HIREDATE < '01-01-1981';
    ```

11. Write a query to display name and salary given to the employees if they are hired after 1982.

    ```sql
    SELECT ENAME, SAL FROM EMP WHERE HIREDATE > '31-12-1982';
    ```

12. Write a query to display details of the employees if they are hired after 2nd Month of 1981.
    ```sql
    SELECT * FROM EMP where HIREDATE >= '1-03-81';
    ```

## OPERATORS

There are 7 operators in SQL:

1. Arithmetic operator (=, -, \*, /)
2. Concatenation operator (||)
3. Comparison operators (=, != or <>)
4. Relational operators (<, >, <=, >=)
5. Logical operators (AND, OR, NOT)
6. Special operators (IN, NOT IN, BETWEEN, NOT BETWEEN, IS, IS NOT, LIKE, NOT LIKE)
7. SubQuery operators (ALL, ANY, EXISTS, NOT EXISTS)

### CONCATENATION OPERATORS

- This operator is used to join given Strings.
- Symbol: ||
- Syntax: 'STRING 1' || 'STRING 2'
- EXAMPLE: SELECT 'Mr.' || ENAME FROM EMP;

| 'MR.'     |     | ENAME |
| --------- | --- | ----- |
| Mr.JONES  |
| Mr.MARTIN |
| Mr.BLAKE  |
| Mr.CLARK  |
| Mr.SCOTT  |
| Mr.KING   |
| Mr.TURNER |

### LOGICAL OPERATORS

- It is used to write multiple conditions.
- AND, OR, NOT

#### AND

- AND operator is used whenever we have to satisfy all the conditions.
- TRUTH TABLE

| INPUTS |      | OUTPUT |
| ------ | ---- | ------ |
| CON1   | CON2 |        |
| A      | B    | Y      |
| 0      | 0    | 0      |
| 0      | 1    | 0      |
| 1      | 0    | 0      |
| 1      | 1    | 1      |

Example Query:

```sql
SELECT * FROM EMP WHERE JOB = 'MANAGER' AND DEPTNO = 20;
```

#### OR operator

- OR operator is used whenever we have to satisfy any one of the conditions.
- TRUTH TABLE

| INPUTS |      | OUTPUT |
| ------ | ---- | ------ |
| CON1   | CON2 |        |
| A      | B    | Y      |
| 0      | 0    | 0      |
| 0      | 1    | 1      |
| 1      | 0    | 1      |
| 1      | 1    | 1      |

Example Query:

```sql
SELECT * FROM EMP WHERE DEPTNO = 10 OR DEPTNO = 40;
```

#### NOT

- NOT operator is used whenever we have to Inverse or Reject the value instead of selecting it.
- TRUTH TABLE

| INPUT | OUTPUT |
| ----- | ------ |
| CON1  | \_     |
| A     | A      |
| 0     | 1      |
| 1     | 0      |

Example Queries:

```sql
SELECT * FROM EMP WHERE NOT DEPTNO = 20;
SELECT * FROM EMP WHERE DEPTNO != 20;
SELECT * FROM EMP WHERE DEPTNO <> 20;
```

## Assignment:

1. Write a query to display details of the employee if the employee works as manager in DEPTNO 20.

   ```sql
   SELECT *
   FROM EMP
   WHERE JOB = 'MANAGER' AND DEPTNO = 20;
   ```

2. Write a query to display Names of employees earning more than 2000 in DEPT 30.

   ```sql
   SELECT ENAME
   FROM EMP
   WHERE SAL > 2000 AND DEPTNO = 30;
   ```

3. Write a query to display Name and Salary of the employee if the employee is earning more than 1500 but less than 3500.

   ```sql
   SELECT ENAME, SAL
   FROM EMP
   WHERE SAL > 1500 AND SAL < 3500;
   ```

4. Write a query to display names of the employees hired after 1981 into DEPTNO 10.

   ```sql
   SELECT ENAME
   FROM EMP
   WHERE HIREDATE >= '01-01-1982' AND DEPTNO = 10;
   ```

5. Write a query to display name and deptno of the employees working in DEPTNO 10 or 20.

   ```sql
   SELECT ENAME, DEPTNO
   FROM EMP
   WHERE DEPTNO = 10 OR DEPTNO = 20;
   ```

6. Write a query to display name, job and deptno of the employees if the employee works as salesman or in DEPTNO 30.

   ```sql
   SELECT ENAME, JOB, DEPTNO
   FROM EMP
   WHERE JOB = 'SALESMAN' OR DEPTNO = 30;
   ```

7. Write a query to display details of all the employees earning more COMM than SAL in DEPTNO 20.

   ```sql
   SELECT *
   FROM EMP
   WHERE COMM > SAL AND DEPTNO = 20;
   ```

8. Write a query to display details of employees except the employee working as salesman.

   ```sql
   SELECT *
   FROM EMP
   WHERE NOT JOB = 'SALESMAN';
   ```

9. Write a query to display details of employees except the employee working in DEPTNO 10 or 20.

   ```sql
   SELECT *
   FROM EMP
   WHERE NOT DEPTNO = 10 AND NOT DEPTNO = 20;
   ```

10. Write a query to display details of the employees if the employee works in DEPTNO 10,20,30 and works as a salesman and manager and earns more than 1250.
    ```sql
    SELECT *
    FROM EMP
    WHERE (DEPTNO = 10 OR DEPTNO = 20 OR DEPTNO = 30)
      AND (JOB = 'SALESMAN' OR JOB = 'MANAGER')
      AND SAL > 1250;
    ```

# SPECIAL OPERATORS

## IN OPERATOR

- It is a special operator which accepts multiple values at RHS.
- It behaves like (=) operator.
- IN operator returns true if it satisfies any one of the values at RHS.

- Syntax: `Column_Name/ EXPRESSION IN (V1, V2, V3,......, Vn);`

- EXAMPLE: run the below query in SQL...
  ```sql
  SELECT * FROM EMP WHERE DEPTNO IN (10, 20, 30) AND JOB IN ('SALESMAN','MANAGER') AND SAL > 1250;
  ```

Q> Write a query to display details of the employees working in DEPT 20 as a CLERK or manager.

```sql
SELECT * FROM EMP WHERE DEPTNO = 20 AND JOB in ('CLERK', 'MANAGER');
```

## NOT IN OPERATOR

- It is similar to IN operator instead of selecting it will reject the values.
- Works as AND operator.
- Syntax:

  ```sql
  Column_Name/ EXPRESSION NOT IN (V1, V2, V3,....., Vn);
  ```

- EXAMPLE:

Q> Write a query to display name and DEPTNO of all the employees except the employees working in deptno 10 OR 40.

```sql
SELECT ENAME, DEPTNO FROM EMP WHERE DEPTNO NOT IN (10, 40);
```

## BETWEEN OPERATOR

- It is used whenever we have range of values. (Starting value and Ending value)
- BETWEEN operator works including the given range.
- In BETWEEN operator we cannot interchange the range.

- Syntax: `Column_Name/ EXPRESSION BETWEEN Starting value AND Ending value;`

- The range includes Starting value and Ending value

- EXAMPLES:
  Q> Write a query to display Names of the employees earning SALARY in the range 1000 to 2500.

  ```sql
  SELECT ENAME FROM EMP WHERE SAL BETWEEN 1000 AND 2500;
  ```

  Q> Write a query to display details of the employees if the employee hired in 81.

  ```sql
  SELECT * FROM EMP WHERE HIREDATE BETWEEN '01-01-81' AND '31-12-81';
  ```

  Q> Write a query to display details of the employees if the employee earns more than 1250 but less than 3000.

  ```sql
  SELECT * FROM EMP WHERE SAL BETWEEN 1250.001 AND 2999.999;
  ```

## NOT BETWEEN Operator

- NOT BETWEEN Operator is similar to BETWEEN Operator instead of selecting it rejects the range.
- Syntax:

  ```sql
  Column_Name/ EXPRESSION NOT BETWEEN Starting value AND Ending value;
  ```

- EXAMPLE:
  Q> Write a query to display details of the employees except the employees who hired in the year 1981.
  ```sql
  SELECT * FROM EMP WHERE HIREDATE NOT BETWEEN '01-01-81' AND '31-12-81';
  ```

## IS OPERATOR

- IS Operator is a special operator which is used to compare with NULL;

- Syntax:

  ```sql
  Column_Name/ EXPRESSION is NULL;
  ```

- EXAMPLE:
  Q> Write a query to display details of the employees who's commission is NULL.
  ```sql
  SELECT * FROM EMP WHERE COMM IS NULL;
  ```

## IS NOT OPERATOR

- IS NOT Operator is used to compare with not NULL.
- Syntax:
  ```sql
  Column_Name/ EXPRESSION IS NOT NULL;
  ```
- EXAMPLE:
  Q> Write a query to display details of the employees who's commission is not NULL.
  ```sql
  SELECT * FROM EMP WHERE COMM IS NOT NULL;
  ```

## LIKE OPERATOR

- LIKE Operator is used to perform pattern matching.
- To achieve pattern matching we use special character such as '%' and '\_'.
- Percentile (%) is a special character which can accept N number of characters, any number of times or No character.
- Underscore (\_) is a special character which can accept exactly one character but any one.

- Syntax:
  ```sql
  Column_Name/ EXPRESSION LIKE 'Pattern_to_Match';
  ```
- EXAMPLES:
  - Starts with character A ---> 'A%'
  - Ends with character A ---> '%A'
  - Has character A ---> '%A%'
  - Has character A present twice ---> '%A%A%'
  - Has two consecutive character A ---> '%AA%'
  - Starts with character A and ends with K ---> 'A%K'
  - Second character is character A ---> '\_A%'
  - Third character is character A ---> '\_ \_A%'
  - Second Last character is character E ---> '%E\_'
  - Third last character is character E ---> '%E\_\_'
  - Starts with K and Second Last character is N ---> 'K%N\_'
  - Has exactly 5 characters ---> '\_ \_ \_ \_ \_'

Q> Write a query to display details of the employees whose name starts with 'K'.

```sql
SELECT * FROM EMP WHERE ENAME LIKE 'K%';
```

Q> Write a query to display details of the employees whose name contains 'a'.

```sql
SELECT * FROM EMP WHERE ENAME LIKE '%A%';
```

Q> Write a query to display details of the employees whose name ends with 'V'.

```sql
SELECT * FROM EMP WHERE ENAME LIKE '%V';
```

Q> Write a query to display details of the employees whose name contains second character 'A'.

```sql
SELECT * FROM EMP WHERE ENAME LIKE '_A%';
```

## NOT LIKE Operator

- NOT LIKE OPERATOR is similar to like operator instead of selecting it will reject the 'Pattern_to_Match'.

# Assignment (12-06-23)

Q1> Write a query to display all the details of the employees who works as salesman and working in deptno 30 and earns more than 1500.

```sql
SELECT *
FROM EMP
WHERE JOB = 'SALESMAN' AND DEPTNO = 30 AND SAL > 1500;
```

Q2> Write a query to display all the details of the employees whose name starts with 'A' or 'S'.

```sql
SELECT *
FROM EMP
WHERE ENAME LIKE '%A' OR ENAME LIKE 'S%';
```

Q3> Write a query to display all the details of the employees whose name does not start with 'S'.

```sql
SELECT *
FROM EMP
WHERE ENAME NOT LIKE 'S%';
```

Q4> Write a query to display all the details of the employees whose commission is NULL and working in deptno 30.

```sql
SELECT *
FROM EMP
WHERE COMM IS NULL AND JOB = 'CLERK';
```

Q5> Write a query to display ENAME, Salary and ANNUAL_SALARY of the employees except those who are working in deptno 30.

```sql
SELECT ENAME, SAL, 12*SAL AS ANNUAL_SALARY, DEPTNO
FROM EMP
WHERE NOT DEPTNO = 30;
```

Q6> Write a query to display all the details of the employees who hired after 81.

```sql
SELECT *
FROM EMP
WHERE HIREDATE > '31-12-81';
```

Q7> Write a query to display names of the employees whose name starts with vowels.

```sql
SELECT ENAME
FROM EMP
WHERE ENAME LIKE 'A%' OR ENAME LIKE 'E%' OR ENAME LIKE 'I%' OR ENAME LIKE 'O%' OR ENAME LIKE 'U%';
```

```sql
SELECT ENAME FROM EMP WHERE ENAME LIKE IN ('A%', 'E%', 'O%', 'U%');
```

Q8> Write a query to display all the details of the employees who hired after 81 and before 83.

```sql
SELECT *
FROM EMP
WHERE HIREDATE BETWEEN '01-01-81' AND '31-12-83';
```

Q9> Write a query to display of all the employees whose job has a string 'MAN'.

```sql
SELECT *
FROM EMP
WHERE JOB LIKE '%MAN%';
```

Q10> Write a query to display ENAME, DESIGNATION and Salary of the employees whose name does not starts with vowels.

```sql
SELECT ENAME, JOB, SAL
FROM EMP
WHERE ENAME NOT LIKE 'A%' AND ENAME NOT LIKE 'E%' AND ENAME NOT LIKE 'I%' AND ENAME NOT LIKE 'O%' AND ENAME NOT LIKE 'U%';
```

Q11> Write a query to display ENAME, DESIGNATION, EMPNO and Salary of the employees if the employee hired between 80 to 87 and earns in the 1000 to 3000.

```sql
SELECT ENAME, JOB, EMPNO, SAL
FROM EMP
WHERE HIREDATE BETWEEN '01-01-80' AND '31-12-87' AND SAL BETWEEN 1000 AND 3000;
```

Q> Write a query to display name of the employees earn more than 2000.

```sql
Select ENAME FROM EMP WHERE SAL > 2000;
```

# SUBQUERY

- A Query written inside another query is known as Sub-Query.

- Working Procedure/ Principle

  - Let us consider 2 queries
    i> Outer query
    ii> Inner query / Sub Query
  - Inner query will execute first and generate the output.
  - The O/P generated by the inner query will be passed as I/P to the outer query
  - The Outer query will execute and generate an O/P.
  - This O/P will be the result.
  - By this we can say the outer query is dependent on inner query.

- When/ Why we use Sub Query?
  -> Case 1: Whenever we have Unknown value or Indirect condition we use the concept of sub query.

EMP Table:

| EID | ENAME  | SAL  |
| --- | ------ | ---- |
| 1   | SMITH  | 950  |
| 2   | ALLEN  | 1200 |
| 3   | King   | 5000 |
| 4   | Miller | 3000 |
| 5   | Scott  | 2200 |
| 6   | JONES  | 1250 |

Q> Write a query to display name of the employees who earns more than JONES.

```sql
SELECT ENAME
FROM EMP
WHERE SAL > (SELECT SAL
             FROM EMP
             WHERE ENAME = 'JONES');
```

Q> Write a query to display name and deptno of the employees if they are working in the same dept as JONES.

```sql
SELECT ENAME, DEPTNO
FROM EMP
WHERE DEPTNO = (SELECT DEPTNO
                FROM EMP
                WHERE ENAME = 'JONES');
```

Q> Write a query to display EMPNO, ENAME along with ANNUAL_SALARY of all the employees if their ANNUAL_SALARY is greater than Ward's ANNUAL_SALARY.

```sql
SELECT EMPNO, ENAME, 12*SAL as ANNUAL_SALARY
FROM EMP
WHERE 12*SAL > (SELECT 12*SAL
                FROM EMP
                WHERE ENAME = 'WARD');
```

Q> Write a query to display name and hiredate of the employees if they are hired before turner.

```sql
SELECT ENAME, HIREDATE
FROM EMP
WHERE HIREDATE < (SELECT HIREDATE
                  FROM EMP
                  WHERE ENAME = 'TURNER');
```

-> Case 2: Whenever the data to be selected and condition to be executed are present in different table we use subquery.

DEPT Table:

| DEPTNO | DNAME      | LOC      |
| ------ | ---------- | -------- |
| 10     | ACCOUNTING | NEW YORK |
| 20     | RESEARCH   | DALLAS   |
| 30     | SALES      | CHICAGO  |
| 40     | OPERATIONS | BOSTON   |

EMP Table:

| EMPNO | ENAME  | DEPTNO |
| ----- | ------ | ------ |
| 7369  | SMITH  | 20     |
| 7499  | ALLEN  | 30     |
| 7521  | WARD   | 30     |
| 7566  | JONES  | 20     |
| 7654  | MARTIN | 30     |
| 7698  | BLAKE  | 30     |
| 7782  | CLARK  | 10     |

Q> Write a query to display DNAME of BLAKE.

```sql
SELECT DNAME
FROM DEPT
WHERE DEPTNO = (SELECT DEPTNO
                FROM EMP
                WHERE ENAME = 'BLAKE');
```

Q> Write a query to display LOC of SMITH.

```sql
SELECT LOC
FROM DEPT
WHERE DEPTNO = (SELECT DEPTNO
                FROM EMP
                WHERE ENAME = 'SMITH');
```

Q> Write a query to display LOC OF THE employees whose names ends with character G.

```sql
SELECT LOC
FROM DEPT
WHERE DEPTNO IN (SELECT DEPTNO
                 FROM EMP WHERE ENAME LIKE '%G');
```

Q> Write a query to display details of the employees working in ACCOUNTING DEPT.

```sql
SELECT *
FROM EMP
WHERE DEPTNO = (SELECT DEPTNO
                FROM DEPT
                WHERE DNAME = 'ACCOUNTING');
```

## TYPES OF SUBQUERY

- SUBQUERY can be classified into 2 types:
  i> Single Row SubQuery(SRSQ)
  ii> MultiROW SubQuery(MRSQ)
- Single Row SUBQUERY: If the subquery return exactly 1 value / 1 record we call it as single row subquery.
  -> If the SUBQUERY returns only 1 value then we can either use normal operator or special operator to compare the value.

- EXAMPLE of SRSQ
  Q> Write a query to display Department name of President.

  ```sql
  SELECT DNAME
  FROM DEPT
  WHERE DEPTNO = (SELECT DEPTNO
                  FROM EMP
                  WHERE JOB = 'PRESIDENT');
  ```

- Multi Row SUBQUERY: If the SUBQUERY returns more than 1 value / 1 record we call it as Multi Row SUBQUERY
  -> If the SUBQUERY returns more than 1 value then we cannot use Normal Operator instead we must use special character

- EXAMPLE of MRSQ
  Q> Write a query to display Department name of manager.

  ```sql
  SELECT DNAME
  FROM DEPT
  WHERE DEPTNO IN (SELECT DEPTNO
                   FROM EMP
                   WHERE JOB = 'MANAGER');
  ```

- Note: It is difficult to identify whether the SUBQUERY Belongs to single row or multi row, Therefore it is recommended to use special operators to compare the values.

| EID | EName | SAL       | HIREDATE  | MOB_NO    |
| --- | ----- | --------- | --------- | --------- |
| 1   | A     | 12000     | 21-JUN-98 | 876548791 |
| B   | 2     | 18000     | 19-APR-99 | 876548782 |
| 3   | C     | 18-JAN-97 | 22000     | 812765487 |
| 4   | D     | 2900      | 21-FEB-98 | 876548792 |
| 5   | 30000 | E         | 876548792 | 18-JAN-97 |

# SQL Datatypes, Constraints, and Commands

## DATATYPES

Datatypes are used to determine what type or kind of data is going to be stored in a particular memory location.

There are 5 types of datatypes:

1. CHAR
2. VARCHAR / VARCHAR2
3. NUMBER
4. DATE
5. LARGE OBJECT
   - CHARACTER LARGE OBJECT
   - BINARY LARGE OBJECT

### CHAR

- Used to store 'A-Z', 'a-z', '0-9', SPECIAL CHARACTERS, and ALPHANUMERIC.
- Syntax: `CHAR(SIZE)`
- Characters should be enclosed within single quotes (' ').
- Size must be mentioned when using CHAR datatype.
- Stores up to 2000 characters.
- Follows fixed length memory allocation.

Example:

```
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
|_ J _|_ A _|_ I _|_ _|_ _|_ _|_ _|_ _|
   |     |     |     |  |   |   |   |
   \/    \/    \/    \/ \/  \/  \/  \/
 _ _ _ _ _ _ _ _   _ _ _ _ _ _ _ _ _ _ _ _ _
   Used MEMORY     Unused MEMORY/ Waste MEMORY
```

### VARCHAR

- Used to store 'A-Z', 'a-z', '0-9', SPECIAL CHARACTERS, and ALPHANUMERIC.
- Syntax: `VARCHAR(SIZE)`
- Should be enclosed within single quotes (' ').
- Size must be mentioned when using VARCHAR datatype.
- Stores up to 2000 characters.
- Follows variable length memory allocation.

Example:

```
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
|_ J _|_ A _|_ I _|_ _|_ _|_ _|_ _|_ _|
   |     |     |     |  |   |   |   |
   \/    \/    \/    \/ \/  \/  \/  \/
 _ _ _ _ _ _ _ _ _   _ _ _ _ _ _ _ _ _ _ _ _ _
    Used MEMORY     Unused MEMORY/ FREE MEMORY
```

### VARCHAR2

- Updated version of VARCHAR.
- Syntax: `VARCHAR2(SIZE)`
- Can store up to 4000 characters.

### NUMBER

- Used to store NUMERICAL values.
- Syntax: `NUMBER(Precision, [Scale])`
- PRECISION:
  - Used to store number of digits in integer.
  - Maximum range of precision is 38.
- SCALE:
  - Used to store number of digits in decimal.
  - Maximum range of SCALE is 127.
  - By DEFAULT, SCALE value is 0.
- Number can be positive or negative.

Examples:

1. `NUMBER(7, 2)` (Precision > Scale)

   ```
   9 9 9 9 9.9 9
   - - - - - - -
   ```

2. `NUMBER(5, 5)` (Precision == Scale)

   ```
   .9 9 9 9 9
    - - - - -
   ```

3. `NUMBER(3, 5)` (Precision < Scale)

   ```
   .0 0 9 9 9
    - - - - -
   ```

4. `NUMBER(5)` (default value of scale is 0)
   ```
   9 9 9 9 9
   - - - - -
   ```

### DATE

- Used to store dates.
- Syntax: `DATE`
- Oracle specified date formats:
  - 'DD-MON-YY'
  - 'DD-MON-YYYY'

### LARGE OBJECT

1. CHARACTER LARGE OBJECT (CLOB)

   - Used to store HUGE AMOUNT of CHARACTERS up to 4 GB.
   - Syntax: `CLOB`

2. BINARY LARGE OBJECT (BLOB)
   - Used to store images, videos, files, MP4, MP3 in the form of Binary up to 4GB.
   - Syntax: `BLOB`

Example table structure:

| Column Name | Datatype    |
| ----------- | ----------- |
| EID         | NUMBER(4)   |
| EName       | VARCHAR(15) |
| SAL         | NUMBER(8,2) |
| HIREDATE    | DATE        |
| MOB_NO      | NUMBER(10)  |

## CONSTRAINTS

Constraints are rules assigned to a column for validating the data.

Types of constraints:

1. UNIQUE
2. NOT NULL
3. CHECK
4. PRIMARY KEY
5. FOREIGN KEY

### UNIQUE

- Assigned to a particular column which should not accept duplicated or repeated values.

### NOT NULL

- Assigned to a particular column which should not accept null.

### CHECK

- Assigned to a particular column for extra VALIDATION.
- If the condition is satisfied, then only values will be accepted; else rejected.

### PRIMARY KEY

- Used to uniquely identify records from the table.
- Characteristics:
  1. Only 1 PRIMARY KEY per table.
  2. Cannot accept DUPLICATED OR REPEATED VALUES.
  3. Combination of UNIQUE and NOT NULL constraint.
  4. Cannot accept NULL.
  5. Not MANDATORY BUT HIGHLY RECOMMENDED.

### FOREIGN KEY

- Used to establish connection between tables.
- Characteristics:
  1. Multiple FOREIGN keys allowed in a table.
  2. Accepts duplicated or repeated values.
  3. Accepts NULL.
  4. Not a combination of UNIQUE and NOT NULL constraints.
  5. Must be PRIMARY KEY in its own table.
  6. Present in CHILD Table but actually belongs to PARENT table.
  7. Also referred to as REFERENTIAL Integrity constraint.

Example of table with constraints:

| Column Name | Datatype    | UNIQUE | NOT NULL | CHECK            | PRIMARY KEY | FOREIGN KEY |
| ----------- | ----------- | ------ | -------- | ---------------- | ----------- | ----------- |
| EID         | NUMBER(4)   | ✓      | ✓        | LEN(EID) = 4     | ✓           |             |
| EName       | VARCHAR(15) | ✓      | ✓        |                  |             |             |
| SAL         | NUMBER(8,2) |        | ✓        | SAL >= 0         |             |             |
| HIREDATE    | DATE        |        | ✓        |                  |             |             |
| MOB_NO      | NUMBER(10)  | ✓      | ✓        | LEN(MOB_NO) = 10 |             |             |

## DDL (DATA DEFINITION LANGUAGE)

DDL is used to CONSTRUCT, MODIFY and REMOVE an object from the Database. DDL statements are auto-commit statements.

DDL statements:

1. CREATE
2. RENAME
3. ALTER
4. TRUNCATE
5. DROP

### CREATE

Used to CONSTRUCT an object in the database.

Syntax:

```sql
CREATE TABLE Table_Name(
  column_name1 datatype constraint,
  column_name2 datatype constraint,
  column_name3 datatype constraint,
  ...
  column_nameN datatype constraint
);
```

Example:

```sql
CREATE TABLE PRODUCT(
  PID NUMBER(4) PRIMARY KEY CHECK(LENGTH(PID) = 4),
  PNAME VARCHAR(15) NOT NULL,
  PRICE NUMBER(8,2) NOT NULL CHECK(PRICE > 0),
  QTY NUMBER(3) NOT NULL CHECK(QTY >= 0),
  DISCOUNT NUMBER(4)
);
```

### RENAME

Used to rename the existing object name.

Syntax:

```sql
RENAME old_tbl_name TO NEW_table;
```

### TRUNCATE

Used to delete/remove all the records of the table permanently.

Syntax:

```sql
TRUNCATE TABLE table_name;
```

### DROP

Used to remove an object from the database.

Syntax:

```sql
DROP TABLE table_name;
```

To recover a dropped table:

```sql
FLASHBACK TABLE table_name TO BEFORE DROP;
```

To permanently delete a table from the recycle bin:

```sql
PURGE TABLE table_name;
```

### ALTER

Used to modify the existing object. Only works if the table is empty.

1. To add a column:

   ```sql
   ALTER TABLE Table_Name ADD COLUMN_NAME DATATYPE CONSTRAINT_Type;
   ```

   Example:

   ```sql
   ALTER TABLE DEPT ADD AGE NUMBER(3) NOT NULL CHECK(AGE > 0);
   ```

2. To drop a column:

   ```sql
   ALTER TABLE Table_Name DROP COLUMN Column_Name;
   ```

   Example:

   ```sql
   ALTER TABLE DEPT DROP COLUMN AGE;
   ```

3. To rename a column:

   ```sql
   ALTER TABLE Table_Name RENAME COLUMN Column_Name TO New_Column_Name;
   ```

   Example:

   ```sql
   ALTER TABLE DEPT RENAME COLUMN LOC TO LOCATION;
   ```

4. To modify the datatype:

   ```sql
   ALTER TABLE Table_Name MODIFY Column_Name New_Datatype;
   ```

   Example:

   ```sql
   ALTER TABLE CELEBRITY MODIFY ANAME NUMBER(5);
   ```

5. To modify NOT NULL constraints:
   ```sql
   ALTER TABLE Table_Name MODIFY Column_Name EXISTING_Datatype [NULL]/ NOT NULL;
   ```
   Example:
   ```sql
   ALTER TABLE CELEBRITY MODIFY EMAIL_ID VARCHAR(20) NOT NULL;
   ```

## DML (Data Manipulation Language)

DML is used to manipulate the object by performing insertion, update, and delete operations. DML statements are not auto-commit statements.

DML statements:

1. INSERT
2. UPDATE
3. DELETE

### INSERT

Used to insert records into the table.

To insert a single record:

```sql
INSERT INTO Table_Name VALUES(V1, V2, V3,...,Vn);
```

Example:

```sql
INSERT INTO MOVIES VALUES(1112, 'KGF', 'HOMBALE', '21-FEB-18', 750000);
```

To insert multiple records:

```sql
INSERT INTO Table_Name VALUES(&COLUMN_NAME1, &COLUMN_NAME2, &COLUMN_NAME3,...,&COLUMN_NAMEN);
```

Example:

```sql
INSERT INTO PRODUCT VALUES(&PID, &PNAME, &PRICE, &DISCOUNT, &CID);
```

### UPDATE

Used to update existing records.

Syntax:

```sql
UPDATE Table_Name
SET COLUMN_NAME1 = VALUE, COLUMN_NAME2 = VALUE,..., COLUMN_NAMEN = VALUE
WHERE FILTER CONDITIONS;
```

Example:

```sql
UPDATE MOVIES SET B_COLLECTION = B_COLLECTION + 25000 WHERE MID = 1113;
```

### DELETE

Used to delete particular records.

Syntax:

```sql
DELETE FROM Table_Name WHERE <filter condition>;
```

Example:

```sql
DELETE FROM MOVIES WHERE MID = 1111;
```

## TCL (Transaction Control Language)

TCL statements:

1. COMMIT
2. SAVEPOINT
3. ROLLBACK

### COMMIT

Used to save the transaction.

```sql
COMMIT;
```

### SAVEPOINT

Used to mark the transaction.

```sql
SAVEPOINT Savepoint_Name;
```

### ROLLBACK

Used to get back to the latest saved transaction.

```sql
ROLLBACK TO Savepoint_Name;
```

Or to revert back to last commit:

```sql
ROLLBACK;
```

## DCL (Data Control Language)

Used to control the flow of data.

DCL statements:

1. GRANT
2. REVOKE

### GRANT

Used to give permission to a user.

```sql
GRANT sql_statement ON Table_Name TO User_Name;
```

Example:

```sql
GRANT SELECT ON EMP TO HR;
```

### REVOKE

Used to take back the given permission from a user.

```sql
REVOKE sql_statement ON Table_Name FROM User_Name;
```

Example:

```sql
REVOKE SELECT ON EMP FROM HR;
```

To connect to other user / To jump from one user to another:

```
CONNECT / CONN
USERNAME: SCOTT/ HR
PASSWORD: tiger
```

## ATTRIBUTE TYPES

1. Key Attribute / Candidate Key
2. Non Key Attribute
3. Prime Key Attribute
4. Non Prime Key Attribute
5. Composite Key Attribute
6. Super Key Attribute
7. Foreign Key Attribute

### Key Attribute

An ATTRIBUTE used to identify a record uniquely from the table.
Example: EID, MOB_NO, ADHAR_NO, EMAIL_ID

### Non-Key Attribute

All ATTRIBUTES except KEY ATTRIBUTES.
Example: NAME, GENDER, AGE, SAL, COMM, HIREDATE

### Prime-Key Attribute

Among the KEY ATTRIBUTES, the one chosen to be the MAIN ATTRIBUTE to identify the RECORD UNIQUELY from the table.
Example: EID

### Non-Prime Key Attribute

All KEY ATTRIBUTES EXCEPT PRIME KEY ATTRIBUTE.
Example: MOB_NO, ADHAR_NO, EMAIL_ID

### Composite Key Attribute

A COMBINATION OF TWO OR MORE NON-KEY ATTRIBUTES used to identify the record UNIQUELY from the table.
Example: ENAME, SAL, COMM, JOB

### Super Key Attribute

The set of ALL KEY ATTRIBUTES.
Example: EID, MOB_NO, ADHAR_NO, EMAIL_ID

### Foreign Key Attribute

Behaves as an ATTRIBUTE of ANOTHER ENTITY to represent RELATION.
Example: DEPTNO

# Functional Dependency

- Let us consider the RELATION 'R' with two ATTRIBUTES 'X' and 'Y' respectively. In which ATTRIBUTE 'X' determines ATTRIBUTE 'Y'.
  OR
- In other words, 'Y' is DEPENDENT on 'X'. There exists FUNCTIONAL DEPENDENCY.

```
R ---> {X, Y}
X----> Y
Y is DEPENDENT on X.
```

- There are 3 types of FUNCTIONAL DEPENDENCY:
  1. TOTAL FUNCTIONAL DEPENDENCY
  2. PARTIAL FUNCTIONAL DEPENDENCY
  3. TRANSITIVE FUNCTIONAL DEPENDENCY

## 1. Total Functional Dependency

- If ALL THE ATTRIBUTES in a RELATION are determined by a SINGLE ATTRIBUTE which is a KEY ATTRIBUTE, then there exists TOTAL FUNCTIONAL DEPENDENCY.
- In TOTAL FUNCTIONAL DEPENDENCY there are NO ANOMALY and REDUNDANCY.
- ANOMALY - THESE are the SIDE EFFECTS which are caused during DML OPERATIONS.
- REDUNDANCY - THESE are the REPEATED or DUPLICATED.

```
R ---> {a, b, c, d}

a ---> b
a ---> c
a ---> d

a is a KEY ATTRIBUTE.

There exists TOTAL FUNCTIONAL DEPENDENCY.
```

## 2. Partial Functional Dependency

- For a PARTIAL FUNCTIONAL DEPENDENCY to exist there must be a COMPOSITE KEY ATTRIBUTE.
- One of the ATTRIBUTE in COMPOSITE KEY RELATION determines another ATTRIBUTE separately, and this is known as PARTIAL FUNCTIONAL DEPENDENCY.
- In PARTIAL FUNCTIONAL DEPENDENCY we have REDUNDANCY and ANOMALY.

```
R ---> {a, b, c, d}

('a' & 'b') is a COMPOSITE KEY ATTRIBUTE.

(a & b) ---> (c & d)
     b  ---> c

THERE EXISTS PARTIAL FUNCTIONAL DEPENDENCY.
```

## 3. Transitive Functional Dependency

- If an ATTRIBUTE is determined by a NON-KEY ATTRIBUTE which in turn is determined by a KEY ATTRIBUTE, then THERE EXIST TRANSITIVE FUNCTIONAL DEPENDENCY.
- In TRANSITIVE FUNCTIONAL DEPENDENCY we have REDUNDANCY and ANOMALY.

```
R ---> {a, b, c, d}

a ---> b
a ---> c
a ---> d
d ---> c

a is a KEY ATTRIBUTE
EXISTS TRANSITIVE FUNCTIONAL DEPENDENCY.
```

# Normalization

- It is a process of reducing the larger table into smaller table in order to remove redundancy and anomaly by identifying their FUNCTIONAL DEPENDENCY.
  OR
- It is a process of decomposing a large table into smaller table to remove redundancy and anomaly.
  OR
- It is a process of reducing the table to its NORMAL FORM.

- NORMAL FORM: A table without redundancy and anomaly is set to be in NORMAL FORM.

**LEVELS OF NORMAL FORM**

1. FIRST NORMAL FORM (1NF)
2. SECOND NORMAL FORM (2NF)
3. THIRD NORMAL FORM (3NF)
4. BOYCE-CODD NORMAL FORM (BCNF)

NOTE: A table is said to be NORMALIZED if we reduce the table in 3NF.

## 1. First Normal Form (1NF)

A table is said to be in 1st NORMAL FORM if it satisfies the following condition:

1. A table should not consist of MULTI-VALUED DATA.
2. A table should not have DUPLICATED of REPEATED VALUES.

Example:

Before 1NF:

| SID | Sname | COURSE   |
| --- | ----- | -------- |
| 1   | A     | SQL      |
| 2   | B     | JAVA, MT |
| 3   | C     | SQL,JAVA |
| 1   | A     | JAVA     |

After 1NF:

| SID | Sname | COURSE_1 | COURSE_2 | COURSE_3 |
| --- | ----- | -------- | -------- | -------- |
| 1   | A     | SQL      |          |          |
| 2   | B     |          | JAVA     | MT       |
| 3   | C     | SQL      | JAVA     |          |
| 1   | A     |          | JAVA     |          |

## 2. Second Normal Form (2NF)

A table is said to be in 2nd NORMAL FORM if it satisfies the following condition:

1. The table should be in 1st NORMAL FORM.
2. The table should not have PARTIAL FUNCTIONAL DEPENDENCY.

Example:

Before 2NF:

| EID | ENAME | SAL  | COMM | DNO | DNAME | LOC |
| --- | ----- | ---- | ---- | --- | ----- | --- |
| 1   | A     | 1250 | NULL | 10  | D1    | L1  |
| 2   | B     | 5000 | 150  | 20  | D2    | L2  |
| 3   | C     | 3000 | NULL | 10  | D1    | L1  |
| 4   | D     | 1290 | 200  | 10  | D1    | L1  |

After 2NF:

EMP Table:

| EID | ENAME | SAL  | COMM | DNO |
| --- | ----- | ---- | ---- | --- |
| 1   | A     | 1250 | NULL | 10  |
| 2   | B     | 5000 | 150  | 20  |
| 3   | C     | 3000 | NULL | 10  |
| 4   | D     | 1290 | 200  | 10  |

DEPT Table:

| DNO | DNAME | LOC |
| --- | ----- | --- |
| 10  | D1    | L1  |
| 20  | D2    | L2  |

NOTE: If the table consists of PARTIAL FUNCTIONAL DEPENDENCY then the attribute responsible are removed from the table.

## 3. Third Normal Form (3NF)

A table is said to be in 3rd NORMAL FORM if it satisfies the following condition:

1. The table should be in 2nd NORMAL FORM.
2. A table should not have TRANSITIVE FUNCTIONAL DEPENDENCY.

NOTE: If the table consists of TRANSITIVE FUNCTIONAL DEPENDENCY then the attribute responsible are removed from the table.

Example:

Before 3NF:

| EID | ENAME | SAL  | COMM | CITY | STATE | PINCODE | COUNTRY |
| --- | ----- | ---- | ---- | ---- | ----- | ------- | ------- |
| 1   | A     | 1250 | NULL | 10   | D1    |         |         |
| 2   | B     | 5000 | 150  | 20   | D2    |         |         |
| 3   | C     | 3000 | NULL | 10   | D1    | L1      |         |
| 4   | D     | 1290 | 200  | 10   | D1    | L1      |         |

EID ----> ENAME, SAL, COMM
PINCODE ---> CITY, STATE, COUNTRY

# Joins

It is used to retrieve the data from multiple Tables simultaneously.

There are 5 types of JOINS in SQL:

1. CARTESIAN JOIN / CROSS JOIN
2. INNER JOIN / EQUI JOIN
3. OUTER JOIN
   - LEFT OUTER JOIN
   - RIGHT OUTER JOIN
   - FULL OUTER JOIN
4. NATURAL JOIN
5. SELF JOIN

## Cartesian Join

- The records of table_1 will merge with all the records of table_2.

Syntax (ANSI):

```sql
SELECT Column_Name FROM Table_Name_1 CROSS JOIN Table_Name_2;
```

Syntax (ORACLE):

```sql
SELECT Column_Name FROM Table_Name_1, Table_Name_2;
```

Example:

```sql
SELECT * FROM EMP, DEPT;
```

EMP Table:

| EID | ENAME | DNO |
| --- | ----- | --- |
| 1   | A     | 30  |
| 2   | B     | 10  |
| 3   | C     | 20  |

DEPT Table:

| DNO | DNAME | LOC |
| --- | ----- | --- |
| 10  | D1    | L1  |
| 20  | D2    | L2  |
| 30  | D3    | L3  |

Result:

| EID | ENAME | DNO | DNO | DNAME | LOC |
| --- | ----- | --- | --- | ----- | --- |
| 1   | A     | 30  | 10  | D1    | L1  |
| 1   | A     | 30  | 20  | D2    | L2  |
| 1   | A     | 30  | 30  | D3    | L3  |
| 2   | B     | 10  | 10  | D1    | L1  |
| 2   | B     | 10  | 20  | D2    | L2  |
| 2   | B     | 10  | 30  | D3    | L3  |
| 3   | C     | 20  | 10  | D1    | L1  |
| 3   | C     | 20  | 20  | D2    | L2  |
| 3   | C     | 20  | 30  | D4    | L3  |

NOTE:

- The Columns are present in the table will be equal to the summation of the columns present in both the tables.
- The Records are present in the table will be equal to the Products of the records present in both the tables.

## Inner Join

- It is used to obtain the matching records.

Syntax (ANSI):

```sql
SELECT COLUMN_NAME FROM Table_Name_1 INNER JOIN Table_Name_2 ON <JOIN_CONDITION>;
```

Syntax (ORACLE):

```sql
SELECT COLUMN_NAME FROM Table_Name_1, Table_Name_2 WHERE <JOIN_CONDITION>;
```

JOIN:

- It is used to merge two tables.
- Syntax: JOIN_CONDITION => Table_Name_1.COLUMN_NAME = Table_Name_2.COLUMN_NAME

Example: Write a query to display ENAME and DNAME

```sql
SELECT ENAME, DNAME FROM EMP, DEPT WHERE EMP.DNO = DEPT.NO;
```

EMP Table:

| EID | ENAME | DNO |
| --- | ----- | --- |
| 1   | A     | 30  |
| 2   | B     | 10  |
| 3   | C     | 20  |

DEPT Table:

| DNO | DNAME | LOC |
| --- | ----- | --- |
| 10  | D1    | L1  |
| 20  | D2    | L2  |
| 30  | D3    | L3  |

RESULT Table:

| ENAME | DNAME |
| ----- | ----- |
| A     | D3    |
| B     | D1    |
| C     | D2    |

## Example Queries

1. Write a query employee details and Department details.

```sql
SELECT * FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO;
```

2. Write a query to display employee name and salary along with their location if they are earning more than 2000.

```sql
SELECT ENAME, SAL, LOCATION FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND SAL > 2000;
```

3. Write a query to display employee name and his deptno along with DEPT Name and LOCATION if the employee is working as MANAGER.

```sql
SELECT ENAME, EMP.DEPTNO, DNAME, LOCATION FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND JOB = 'MANAGER';
```

4. Write a query to display details of the employee along with dept name if the employee is earning more than 100 and working in deptno 20.

```sql
SELECT EMP.*, DNAME FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND SAL > 1000 AND DEPT.DEPTNO = 20;
```

5. Write a query to display employee name and deptname of the employee who is working as manager in LOC DALLAS.

```sql
SELECT ENAME, DNAME FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND JOB = 'MANAGER' AND LOCATION = 'DALLAS';
```

## Assignment

1. Write a query to display name of the employee and the location of all the employees.

```sql
SELECT ENAME, LOCATION FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO;
```

2. Write a query to display DNAME and SALARY for all the employee working in accounting.

```sql
SELECT DNAME, SAL FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND DNAME = 'ACCOUNTING';
```

3. Write a query to display DNAME and ANNUAL_SALARY for all the employees who's salary is more than 2340.

```sql
SELECT DNAME, (12*SAL) AS ANNUAL_SALARY FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND SAL > 2340;
```

4. Write a query to display ENAME and DNAME for all the employees having character 'A' in their DNAME.

```sql
SELECT ENAME, DNAME FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND DNAME LIKE '%A%';
```

5. Write a query to display ENAME and DNAME for all the employees working as a salesman.

```sql
SELECT ENAME, DNAME FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND JOB = 'SALESMAN';
```

6. Write a query to display DNAME and JOB for all the employees who's JOB and DNAME starts with character 'S'.

```sql
SELECT DNAME, JOB FROM DEPT, EMP WHERE DEPT.DEPTNO = EMP.DEPTNO AND JOB LIKE 'S%' AND DNAME LIKE 'S%';
```

7. Write a query to display DNAME and MGR NO for employees reporting to 7839.

```sql
SELECT DNAME, MGR FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND MGR = 7839;
```

8. Write a query to display DNAME and HIREDATE for employees hired after 83 into ACCOUNTING or RESEARCH Department.

```sql
SELECT DNAME, HIREDATE FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND HIREDATE > '31-12-83' AND DNAME IN ('ACCOUNTING', 'RESEARCH');
```

9. Write a query to display ENAME and DNAME of the employees who are getting COMM from dept 10 or 30.

```sql
SELECT ENAME, DNAME FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND COMM IS NOT NULL AND EMP.DEPTNO IN (10, 30);
```

10. Write a query to display DNAME and EMPNO for all the employees who's EMPNO are (7839, 7902) and are working in LOC NEW YORK.

```sql
    -> SELECT DNAME, EMPNO FROM EMP, DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO AND EMPNO IN (7839, 7903) AND LOCATION = 'NEW YORK';
```

**NATURAL JOIN**

- It has two behaviors:

  1. It behaves as INNER JOIN when there is RELATION between the two tables.
  2. It behaves as CARTESIAN JOIN when there is NO RELATION between the two tables.

- Syntax: ANSI(AMERICAN NATIONAL STANDARD INSTITUTE)
  SELECT Column_Name FROM Table_Name_1 NATURAL JOIN Table_Name_2;

NOTE:

1. IN NATURAL JOIN we need not need t write any JOIN CONDITON.
2. There is no Confusion in identifying the common column.

**OUTER JOIN**

- It is used to obtain unmatched records.
- There are 3 types of OUTER JOIN:

  1. LEFT OUTER JOIN
  2. RIGHT OUTER JOIN
  3. FULL OUTER JOIN

  **LEFT OUTER JOIN**

  - It is used to obtain unmatched records of the left table along with matching records.

  - Syntax: ANSI (AMERICAN NATIONAL STANDARD INSTITUTE)
    SELECT Column_Name FROM Table_Name_1 LEFT [OUTER] JOIN Table_Name_2 ON <JOIN_CONDITION>;
  - Syntax: ORACLE
    SELECT COLUMN_NAME FROM Table_Name_1, Table_Name_2 where Table_Name_1.Column_Name = Table_Name_2.Column_Name(+);

  - In ORACLE Syntax (+) carries NULL which will placed in the table for unmatched records.

  - Example:

  EMP
  | ENAME | DNO |
  |-------|------|
  | A | 30 |
  | B | NULL |
  | C | 20 |

  DEPT
  | DNO | DNAME |
  |-----|-------|
  | 10 | D1 |
  | 20 | D2 |
  | 30 | D3 |

  RESULT TABLE:
  | ENAME | DNO | DNO | DNAME |
  |-------|-----|-----|-------|
  | A | 30 | 30 | D1 |
  | B | NULL| NULL| |
  | C | 20 | 20 | D2 |

  **RIGHT OUTER JOIN**

  - It is used to obtain unmatched records of the right table along with matching records.

  - Syntax: ANSI (AMERICAN NATIONAL STANDARD INSTITUTE)
    SELECT Column_Name FROM Table_Name_1 RIGHT [OUTER] JOIN Table_Name_2 ON <JOIN_CONDITION>;
  - Syntax: ORACLE
    SELECT COLUMN_NAME FROM Table_Name_1, Table_Name_2 where Table_Name_1.Column_Name(+)= Table_Name_2.Column_Name;

  - Example:
    EMP
    | ENAME | DNO |
    |-------|------|
    | A | 20 |
    | B | NULL |
    | C | 10 |
    | D | NULL |

    DEPT
    | DNO | DNAME |
    |-----|-------|
    | 10 | D1 |
    | 20 | D2 |
    | 30 | D3 |
    | 40 | D4 |

    RESULT TABLE:
    | ENAME | DNO | DNO | DNAME |
    |-------|------|-----|-------|
    | A | 20 | 20 | D2 |
    | C | 10 | 10 | D1 |
    | NULL | NULL | 30 | D3 |
    | NULL | NULL | 40 | D4 |

  **FULL OUTER JOIN**

  - It is used to obtain unmatched records of both the table along with matching records.

  - Syntax: ANSI (AMERICAN NATIONAL STANDARD INSTITUTE)
    SELECT Column_Name FROM Table_Name_1 FULL [OUTER] JOIN Table_Name_2 ON <JOIN_CONDITION>;

  - Example:
    EMP
    | ENAME | DNO |
    |-------|------|
    | A | 20 |
    | B | NULL |
    | C | 10 |
    | D | NULL |

    DEPT
    | DNO | DNAME |
    |-----|-------|
    | 10 | D1 |
    | 20 | D2 |
    | 30 | D3 |
    | 40 | D4 |

    RESULT TABLE:
    | ENAME | DNO | DNO | DNAME |
    |-------|------|------|-------|
    | A | 20 | 20 | D2 |
    | C | 10 | 10 | D1 |
    | B | NULL | NULL | NULL |
    | D | NULL | NULL | NULL |
    | NULL | NULL | 30 | D3 |
    | NULL | NULL | 40 | D4 |

**SELF JOIN**

- It is used to join a table itself or joining same two table is known as SELF JOIN.

- When and where do we use SELF JOIN?
  -> Whenever the data to selected is present in the same table but in different records we use the concept of self join.

- Syntax: ANSI(AMERICAN NATIONAL STANDARD INSTITUTE)
  SELECT Column_Name FROM Table_Name_1 JOIN Table_Name_2 ON <JOIN_CONDITION>;
  OR
- Syntax: ORACLE
  SELECT Column_Name FROM Table_Name_1, Table_Name_2 WHERE <JOIN_CONDITION>;

- Example: Q> Write a query to display ENAME and MGR NAME.
  -> SELECT E1.ENAME, E2.ENAME as MGR_NAME FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EID;

  EMP as E1
  | EID | ENAME | MGR |
  |-----|--------|------|
  | 1 | DINGI | 2 |
  | 2 | DINGA | 3 |
  | 3 | CHINGI | NULL |
  | 4 | CHINGA | 3 |
  | 5 | TINGU | 2 |
  | 6 | TINGI | 1 |

  EMP as E2
  | EID | ENAME | MGR |
  |-----|--------|------|
  | 1 | DINGI | 2 |
  | 2 | DINGA | 3 |
  | 3 | CHINGI | NULL |
  | 4 | CHINGA | 3 |
  | 5 | TINGU | 2 |
  | 6 | TINGI | 1 |

  RESULT OF WHERE CLAUSE:

  3 = 1 (F) | 2 = 1 (F)
  3 = 2 (F) | 2 = 2 (T)
  3 = 3 (T) | 2 = 3 (F)
  3 = 4 (F) | 2 = 4 (F)
  3 = 5 (F) | 2 = 5 (F)
  3 = 6 (F) | 2 = 6 (F)

  ***

  2 = 1 (F) | 3 = 1 (F)
  2 = 2 (T) | 3 = 2 (F)
  2 = 3 (F) | 3 = 3 (T)
  2 = 4 (F) | 3 = 4 (F)
  2 = 5 (F) | 3 = 5 (F)
  2 = 6 (F) | 3 = 6 (F)

  ***

  1 = 1 (T) | NULL = 1 (NULL)
  1 = 2 (F) | NULL = 2 (NULL)
  1 = 3 (F) | NULL = 3 (NULL)
  1 = 4 (F) | NULL = 4 (NULL)
  1 = 5 (F) | NULL = 5 (NULL)
  1 = 6 (F) | NULL = 6 (NULL)

  RESULT TABLE:
  | ENAME | MGR_NAME |
  |-------|----------|
  | DINGI | DINGA |
  | DINGA | CHINGI |
  | CHINGA| CHINGI |
  | TINGU | DINGA |
  | TINGI | DINGI |

Assignment:

Q1> Write a query to display name of the employee and his manager's name if employee is working as CLERK.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.JOB = 'CLERK';
```

Q2> Write a query to display name of the employee and manager's designation if manager works in dept 10 or 20.

```sql
-> SELECT E1.ENAME, E2.JOB as MGR_Desig, E2.DEPTNO FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E2.DEPTNO IN (10, 20);
```

Q3> Write a query to display name of the employee and manager's salary if employee and manager both earn more than 2300.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME ,E2.SAL as MGR_SAL FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.SAL >2300 AND E2.SAL > 2300;
```

Q4> Write a query to display EMP NAME and MANAGER's HIREDATE if employee was hired before 1982.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME ,E2.HIREDATE as MGR_HIREDATE FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.HIREDATE < '01-01-82';
```

Q5> Write a query to display EMP NAME and MANAGER's COMM if employee works as SALESMAN and MANAGER works in DEPT 30.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME ,E2.COMM as MGR_COMM FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.JOB = 'SALESMAN' AND E2.DEPTNO = 30;
```

Q6> Write a query to display EMP NAME and MANAGER NAME and their salaries if employee earns more than their MANAGER.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME , E1.SAL as EMP_SAL, E2.SAL as MGR_SAL FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.SAL > E2.SAL;
```

Q7> Write a query to display EMP NAME, HIREDATE and MANAGER NAME, HIREDATE if MANAGER was hired before employee.

```sql
-> SELECT E1.ENAME, E1.HIREDATE as EMP_HIREDATE, E2.ENAME as MGR_NAME , E2.HIREDATE as MGR_HIREDATE FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E2.HIREDATE < E1.HIREDATE;
```

Q8> Write a query to display EMP NAME and MANAGER NAME if both are working the same job.

```sql
-> SELECT E1.ENAME, E2.ENAME as MGR_NAME, E1.JOB as EMP_JOB, E2.JOB as MGR_JOB FROM EMP E1, EMP E2 WHERE E1.MGR = E2.EMPNO AND E1.JOB = E2.JOB;
```

**To JOIN MULTIPLE TABLES**

- To join multiple tables we need to pass (n-1) join condition.

- We can join 256 tables by using INNER JOINS.

- See ToJoinMultipleTables image for further discussion.

Q1> Write a query to display ENAME, MANAGER's NAME, EMP DEPT and MANAGER's DEPT.

```sql
-> SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, D1.DNAME as EMP_DEPT, D2.DNAME as MGR_DEPT FROM EMP E1, EMP E2, DEPT D1, DEPT D2 WHERE E1.MGR = E2.EMPNO AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO;
```

Q2> Write a query to display ENAME, MANAGER's NAME, EMP DEPT and MANAGER's DEPT if EMP earns more than 2000 and manager working in dept 20.

```sql
-> SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, D1.DNAME as EMP_DEPT, D2.DNAME as MGR_DEPT FROM EMP E1, EMP E2, DEPT D1, DEPT D2 WHERE E1.MGR = E2.EMPNO AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO AND E1.SAL > 2000 AND E2.DEPTNO = 20;
```

Assignment:

Q3> Write a query to display ENAME, manager_name and their DNAME if EMP earning more than SMITH and MANAGER earning more than ALLEN.

```sql
-> SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, D1.DNAME as EMP_DEPT, D2.DNAME as MGR_DEPT
   FROM EMP E1, EMP E2, DEPT D1, DEPT D2
   WHERE E1.MGR = E2.EMPNO AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO
   AND E1.SAL > (SELECT SAL FROM EMP WHERE ENAME = 'SMITH')
   AND E2.SAL > (SELECT SAL FROM EMP WHERE ENAME = 'ALLEN');
```

Q4> Write a query to display ENAME , Manager's NAME and their LOC if EMP working in the DEPT 10 or 30 and Manager earning more than FORD and EMP working in the LOC NEW YORK or CHICAGO.

```sql
-> SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, D1.LOCATION as EMP_LOCATION, D2.LOCATION as MGR_LOCATION
   FROM EMP E1, EMP E2, DEPT D1, DEPT D2
   WHERE E1.MGR = E2.EMPNO AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO
   AND E1.DEPTNO in (10, 30)
   AND E2.SAL > (SELECT SAL FROM EMP WHERE ENAME = 'FORD')
   AND D1.LOCATION IN ('NEW YORK', 'CHICAGO');
```

# SQL Notes: Functions, GROUP BY, and HAVING

## Sample Queries

### Q5: Display ENAME, Manager's Name, and Manager's Manager Name

```sql
SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, E3.ENAME as MGR_MGR_NAME
FROM EMP E1, EMP E2, EMP E3
WHERE E1.MGR = E2.EMPNO AND E2.MGR = E3.EMPNO;
```

### Q6: Display Names and Departments with Specific Conditions

```sql
SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, E3.ENAME as MGR_MGR_NAME,
       D1.DNAME as EMP_DEPT, D2.DNAME as MGR_DEPT, D3.DNAME as MGR_MGR_DEPT
FROM EMP E1, EMP E2, EMP E3, DEPT D1, DEPT D2, DEPT D3
WHERE E1.MGR = E2.EMPNO AND E2.MGR = E3.EMPNO
  AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO AND E3.DEPTNO = D3.DEPTNO
  AND E1.SAL > 1000
  AND E2.SAL > (SELECT SAL FROM EMP WHERE ENAME = 'ALLEN')
  AND D3.LOCATION IN ('NEW YORK', 'CHICAGO');
```

### Q7: Display Names and Locations with Specific Conditions

```sql
SELECT E1.ENAME as EMP_NAME, E2.ENAME as MGR_NAME, E3.ENAME as MGR_MGR_NAME,
       D1.LOCATION as EMP_LOC, D2.LOCATION as MGR_LOC, D3.LOCATION as MGR_MGR_LOC
FROM EMP E1, EMP E2, E3, DEPT D1, DEPT D2, DEPT D3
WHERE E1.MGR = E2.EMPNO AND E2.MGR = E3.EMPNO
  AND E1.DEPTNO = D1.DEPTNO AND E2.DEPTNO = D2.DEPTNO AND E3.DEPTNO = D3.DEPTNO
  AND E1.HIREDATE < (SELECT HIREDATE FROM EMP WHERE ENAME = 'MARTIN')
  AND D2.DNAME IN ('ACCOUNTING', 'SALES')
  AND E3.SAL > (SELECT SAL FROM EMP WHERE ENAME = 'SMITH');
```

## Functions in SQL

A function is a block of code or a list of instructions to perform a specific task.

### Types of Functions:

1. In-Built functions
2. User-defined functions

#### In-Built Functions:

1. Single row function
2. Multi row function

##### Single Row Function (SRF)

- Executes row by row
- Takes one input, generates one output, and moves to the next input
- N inputs result in N outputs

##### Multi Row Function (MRF)

- Also referred to as GROUP FUNCTION or AGGREGATE FUNCTION
- Executes GROUP BY GROUP
- Takes all inputs at once, aggregates, and generates one output
- N inputs result in one output

Types of MRF:

1. MAX()
2. MIN()
3. AVG()
4. SUM()
5. COUNT()

Characteristics of Multi Row Function:

1. Only one argument can be passed
2. Cannot pass other column names or expressions in the SELECT clause
3. Ignores NULL values
4. Cannot be used in WHERE clause
5. COUNT() is the only MRF that accepts \* as an argument
6. SUM() and AVG() accept numbers as arguments

### Examples of Multi Row Functions

```sql
-- Q1: Display number of employees in EMP table
SELECT COUNT(*) FROM EMP;

-- Q2: Display total salary of employees in EMP table
SELECT SUM(SAL) FROM EMP;

-- Q3: Display average salary of employees in EMP table
SELECT AVG(SAL) FROM EMP;

-- Q4: Display number of employees working in each department
SELECT COUNT(*), DNO FROM EMP GROUP BY DEPTNO;
```

## GROUP BY Clause

- Used to group records
- Executes ROW by ROW
- Can be used with or without WHERE clause
- Results in groups after execution
- Clauses after GROUP BY execute GROUP BY GROUP
- Column names or expressions in GROUP BY can be in SELECT clause
- Multiple arguments can be passed to GROUP BY

Syntax:

```sql
SELECT GROUP_BY_FUNCTION / GROUP_BY_EXPRESSION
FROM TABLE_NAME
WHERE <filter_condition>
GROUP BY COLUMN_NAME / EXP;
```

Order of Execution:

1. FROM
2. WHERE (if needed) -> Row By Row
3. GROUP BY -> Row By Row
4. SELECT -> GROUP BY GROUP

Example:

```sql
-- Display number of employees working in each department
SELECT COUNT(*), DNO FROM EMP GROUP BY DEPTNO;
```

Output:
| COUNT(\*) | DEPTNO |
|----------|--------|
| 3 | 20 |
| 2 | 10 |
| 1 | 30 |

### Assignment Questions

```sql
-- Q1: Display number of employees with 'A' in their names for each job
SELECT COUNT(ENAME), JOB FROM EMP WHERE ENAME LIKE '%A%' GROUP BY JOB;

-- Q2: Display employee count and average salary for those earning > 2000 in each dept
SELECT COUNT(*), AVG(SAL), DEPTNO FROM EMP WHERE SAL > 2000 GROUP BY DEPTNO;

-- Q3: Display total salary and number of salesmen in each dept
SELECT SUM(SAL), COUNT(ENAME), DEPTNO FROM EMP WHERE JOB = 'SALESMAN' GROUP BY DEPTNO;

-- Q4: Display employee count and maximum salary in each dept
SELECT COUNT(ENAME), MAX(SAL) FROM EMP GROUP BY DEPTNO;

-- Q5: Display maximum salary given to employees in each dept
SELECT MAX(SAL), DEPTNO FROM EMP GROUP BY DEPTNO;
```

## HAVING Clause

- Used to filter groups
- Executes GROUP BY GROUP
- Executes after GROUP BY clause
- Contains group filter conditions
- Requires GROUP BY clause
- Can have multiple conditions using logical operators

Syntax:

```sql
SELECT GROUP_BY_FUNCTION/GROUP_BY_EXPRESSION
FROM TABLE_NAME
WHERE <filter_condition>
GROUP BY COLUMN_NAME/ EXP
HAVING <Group_filter_condition>
```

Order of Execution:

1. FROM
2. WHERE -> ROW BY ROW (If needed)
3. GROUP BY -> ROW BY ROW
4. HAVING -> GROUP BY GROUP
5. SELECT -> GROUP BY GROUP

Example:

```sql
-- Display number of employees in each dept with at least 2 employees
SELECT COUNT(*), DEPTNO FROM EMP GROUP BY DEPTNO HAVING COUNT(*) >= 2;
```

Output:
| COUNT(\*) | DEPTNO |
|----------|--------|
| 3 | 20 |
| 2 | 10 |

### More HAVING Examples

```sql
-- Q2: Display jobs with at least 2 employees
SELECT JOB FROM EMP GROUP BY JOB HAVING COUNT(EMPNO) >= 2;

-- Q3: Display names repeated exactly twice
SELECT ENAME FROM EMP GROUP BY ENAME HAVING COUNT(ENAME) = 2;

-- Q4: Display salaries that are repeated
SELECT SAL FROM EMP GROUP BY SAL HAVING COUNT(SAL) >= 2;

-- Q5: Display departments with at least 2 employees having 'A' or 'S' in their names
SELECT COUNT(ENAME), DEPTNO
FROM EMP
WHERE ENAME LIKE '%A%' OR ENAME LIKE '%S%'
GROUP BY DEPTNO
HAVING COUNT(*) >= 2;
```

# DIFFERENCE BETWEEN WHERE CLAUSE AND HAVING CLAUSE

| WHERE CLAUSE                           | HAVING CLAUSE                         |
| -------------------------------------- | ------------------------------------- |
| Used to filter the records             | Used to filter the GROUPS             |
| Executes ROW BY ROW                    | Executes GROUP BY GROUP               |
| Must be written before GROUP BY CLAUSE | Must be written after GROUP BY CLAUSE |
| Cannot pass MULTI ROW FUNCTIONS        | Can pass MULTI ROW FUNCTIONS          |
| GROUP BY CLAUSE is optional            | GROUP BY CLAUSE is MANDATORY          |

## Assignment:

Q6> Write a query to display total salary of each job if total salary of each job is greater than 3450.

```sql
SELECT SUM(SAL) as TOTAL_SAL, JOB FROM EMP GROUP BY JOB HAVING SUM(SAL) > 3450;
```

Q7> Write a query to display number of employees in each job and total salary of the employees if they are earning more than 1500.

```sql
SELECT COUNT(EMPNO), SUM(SAL), JOB FROM EMP GROUP BY JOB HAVING SUM(SAL) > 1500;
```

Q8> Write a query to display deptno and number of clerks working in each dept if there are atleast 2 clerks in each dept.

```sql
SELECT COUNT(EMPNO), DEPTNO FROM EMP WHERE DEPTNO IN (SELECT DEPTNO FROM EMP WHERE JOB = 'CLERK' GROUP BY DEPTNO HAVING COUNT(EMPNO)>=2) GROUP BY DEPTNO;
```

Q9> Write a query to display deptno and total salary needed to pay all the employees in each dept if there are atleast 4 employees in each dept.

```sql
SELECT DEPTNO, SUM(SAL) FROM EMP GROUP BY DEPTNO HAVING COUNT(EMPNO)>=4;
```

Q10> Write a query to display number of employees earning salary more than 1200 in each job and total salary needed to pay employees of each job must exceed 3800

```sql
SELECT COUNT(EMPNO), JOB FROM EMP WHERE EMPNO IN (SELECT EMPNO FROM EMP WHERE SAL >1200) GROUP BY JOB HAVING SUM(SAL)>3800;
```

Q11> Write a query to display deptno and number of manager working only if there are 2 employees working in each dept as manager.

```sql
SELECT DEPTNO, COUNT(EMPNO) FROM EMP WHERE DEPTNO IN (SELECT DEPTNO FROM EMP WHERE JOB = 'MANAGER' GROUP BY DEPTNO HAVING COUNT(EMPNO)>=2) GROUP BY DEPTNO;
```

1> Write a query to display number of employees working in each dept if there are atleast 2 Analyst in each dept.

```sql
SELECT DEPTNO, COUNT(EMPNO) AS num_employees FROM EMP WHERE DEPTNO IN (SELECT DEPTNO FROM EMP WHERE JOB = 'ANALYST' GROUP BY DEPTNO HAVING COUNT(EMPNO) >= 2) GROUP BY DEPTNO;
```

2> Write a query to display deptno and total salary of each dept if there are atleast 4 employees working in each dept.

```sql
SELECT DEPTNO, SUM(SAL) FROM EMP GROUP BY DEPTNO HAVING COUNT(EMPNO) >= 4;
```

3> Write a query to display number of employees working in each job if there are atleast 2 employees.

```sql
SELECT COUNT(*), JOB FROM EMP GROUP BY JOB HAVING COUNT(EMPNO) >= 2;
```

4> Write a query to display job wise maximum salaries of each job is more than 1500.

```sql
SELECT MAX(SAL), JOB FROM EMP GROUP BY JOB HAVING MAX(SAL) > 1500;
```

5> Write a query to display deptno and average salaries given to each dept if the average salary is less than 3000.

```sql
SELECT DEPTNO, AVG(SAL) FROM EMP GROUP BY DEPTNO HAVING AVG(SAL) < 3000;
```

6> Write a query to display number of employees working in each dept if there are atleast one manager in each dept.

```sql
SELECT COUNT(*), DEPTNO FROM EMP WHERE DEPTNO IN (SELECT DEPTNO FROM EMP WHERE JOB = 'MANAGER' GROUP BY DEPTNO HAVING COUNT(EMPNO)>= 1) GROUP BY DEPTNO;
```

7> Write a query to display the names which are present more than once or repeated or duplicate.

```sql
SELECT ENAME FROM EMP GROUP BY ENAME HAVING COUNT(ENAME) >= 2;
```

8> Write a query to display minimum salary to each dept excluding president the minimum salary has to be more than 1000 Rs.

```sql
SELECT MIN(SAL), DEPTNO FROM EMP WHERE EMPNO IN (SELECT EMPNO FROM EMP WHERE JOB NOT IN 'PRESIDENT') GROUP BY DEPTNO HAVING MIN(SAL)>1000;
```

9> Write a query to display average salary given to each job by excluding the employees whose name ends with 'S'and the average salary must be less than 1500.

```sql
SELECT AVG(SAL), JOB FROM EMP WHERE ENAME NOT IN (SELECT ENAME FROM EMP WHERE ENAME LIKE '%S') GROUP BY JOB HAVING AVG(SAL) < 1500;
```

10> Write a query to display details of the employees who were hired on same day.

```sql
SELECT * FROM EMP WHERE HIREDATE IN (SELECT HIREDATE FROM EMP GROUP BY HIREDATE HAVING COUNT(HIREDATE) > 1);
```

11> Write a query to display details of the employees if the employees earns same salary but less than KING.

```sql
SELECT * FROM EMP WHERE SAL IN (SELECT SAL FROM EMP GROUP BY SAL HAVING COUNT(SAL) > 1) AND SAL < (SELECT SAL FROM EMP WHERE ENAME = 'KING');
```

# SINGLE ROW FUNCTION SRF()

1. LENGTH()
2. CONCAT()
3. UPPER()
4. LOWER()
5. INITCAP()
6. REVERSE()
7. SUBSTR()
8. INSTR()
9. REPLACE()
10. MOD()
11. NVL()
12. ROUND()
13. TRUNC()
14. TO_CHAR()

## LENGTH()

- This function is used to count the number of characters present in the given string.
- Syntax: `LENGTH(STRING)`
- Example:
  ```sql
  SELECT LENGTH('TUSHAR') FROM DUAL
  -- OUTPUT: 5
  ```
- DUAL: It is a dummy table which has exactly one row and one column which is used to get the result.

Q> WAQTD name of employee where name have have more than 4 character without using LIKE operator.

```sql
SELECT ENAME FROM EMP WHERE LENGTH(ENAME) > 4;
```

## CONCAT()

- This function is used to join the given two strings.
- Syntax: `CONCAT('STRING_1', 'STRING_2')`
- Example:
  ```sql
  SELECT CONCAT('Mr', 'JAINIL') FROM DUAL;
  -- OUTPUT: MR JAINIL
  ```

## UPPER()

- This function is used to convert the given string into UPPERCASE.
- Syntax: `UPPER(STRING)`
- Example1:
  ```sql
  SELECT UPPER('salman') FROM DUAL;
  -- OUTPUT: SALMAN
  ```
- Example2:
  ```sql
  SELECT UPPER(ENAME) FROM EMP;
  ```

## LOWER()

- This function is used to convert the given string into LOWERCASE.
- Syntax: `LOWER(STRING)`
- Example:
  ```sql
  SELECT LOWER('ARJUN') FROM DUAL;
  -- OUTPUT: arjun
  ```
- Example:
  ```sql
  SELECT LOWER(ENAME) FROM EMP;
  ```

## INITCAP()

- This function is used to convert the given string's initial alphabet into uppercase and rest of the alphabet into lowercase.
- Syntax: `INITCAP(STRING)`
- Example:
  ```sql
  SELECT INITCAP('ARJUN') FROM DUAL;
  -- OUTPUT: Arjun
  ```

## REVERSE()

- This function is used to reverse the given string.
- Syntax: `REVERSE(STRING)`
- Example:
  ```sql
  SELECT REVERSE('BANANA') FROM DUAL;
  -- OUTPUT: ANANAB
  ```

## REPLACE()

- This function is used to replace the given string with new string.
- Syntax: `REPLACE('ORIGINAL_STRING', 'OLD_STRING', ['NEW_STRING'])`
  ```sql
  REPLACE ('BANANA', 'N', 'T') -- => BATATA
  REPLACE ('BANANA', 'N') -- => BAAA
  ```

Q> WAQTD number of 'A' present in particular names

```sql
SELECT (LENGTH(ENAME) - LENGTH(REPLACE(ENAME, 'A'))), ENAME FROM EMP;
```

Q> WAQTD names whose name have character 'A' repeated exactly twice.

```sql
SELECT ENAME, (LENGTH(ENAME) - LENGTH(REPLACE(ENAME, 'A'))) as Number_of_A_in_EName FROM EMP WHERE (LENGTH(ENAME) - LENGTH(REPLACE(ENAME, 'A'))) = 2 ;
```

Q> WAQTD details of the employee if the employee earning odd number of SAL.

```sql
SELECT * FROM EMP WHERE MOD(SAL, 2) != 0;
```

## ROUND()

- It is used to round of the given value to it's nearest value.
- Syntax: `ROUND(NUMBER)`
- Example:
  ```sql
  SELECT ROUND(7.2) FROM DUAL;
  -- OUTPUT: 7
  SELECT ROUND(7.8) FROM DUAL;
  -- OUTPUT: 8
  SELECT ROUND(7.5) FROM DUAL;
  -- OUTPUT: 8
  ```

## TRUNC()

- It is used to round of the given value to it's least value.
- Syntax: `TRUNC(NUMBER)`
- Example:
  ```sql
  SELECT TRUNC(7.9) FROM DUAL;
  -- OUTPUT: 7
  ```

## NVL()

- It stands for NULL VALUE LOGIC(NVL).
- Syntax: `NVL(argument_1, argument_2);`
- This function is used to eliminate the SIDE-EFFECTS of NULL in Arithmetic operations
- Example:
  ```sql
  SELECT SAL+NVL(COMM,0) FROM EMP;
  ```

EMP Table:

| SAL  | COMM |
| ---- | ---- |
| 1000 | NULL |
| 2000 | 250  |
| 3000 | NULL |
| 1500 | 0    |

Result:

- 1000 + 0 = 1000
- 2000 + 250 = 2250
- 3000 + 0 = 3000
- 1500 + 0 = 1500

## TO_CHAR()

- It is used to convert the given date into string format by using format model.
- Syntax: `TO_CHAR(DATE, FORMAT_MODEL)`
- Different FORMAT MODEL:
  1. YEAR
  2. YYYY
  3. YY
  4. MONTH
  5. MM
  6. DAY
  7. DD
  8. HH24
  9. HH12 - Hour in 12-hrs format
  10. D - Day in the Week
  11. MI - Minutes
  12. SS - Seconds

Q> WAQTD of the employees if the employee is hired in the year 81 by using to_char.

```sql
SELECT * FROM EMP WHERE TO_CHAR(HIREDATE, 'YY') = '81';
```

Q> WAQTD details of the employees if the employee is hired in the december by using to_char.

```sql
SELECT * FROM EMP WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';
```

Q> WAQTD details of the employees if the employee is hired on wednesday by using to_char.

```sql
SELECT * FROM EMP WHERE TO_CHAR(HIREDATE, 'DAY') = 'WEDNESDAY';
```

NOTE:
1> DIFFERENCE BETWEEN DELETE, DROP, and TRUNCATE.

NOTE:
1> DIFFERENCE BETWEEN DELETE, DROP, and TRUNCATE.

The main difference between the DROP, DELETE, and TRUNCATE commands in SQL is what they do to a table or database:

## DROP

- Removes the entire table or database, including its structure and associated data and objects.
- DROP is permanent and cannot be recovered without a backup.

## DELETE

- Removes specific rows from a table, while keeping the table structure intact.
- DELETE is slower than TRUNCATE, especially when dealing with many records, because it logs each deletion.

## TRUNCATE

- Removes all rows from a table, but preserves its structure.
- TRUNCATE is generally faster than DELETE because it bypasses individual row deletion and doesn't log each row change.
- TRUNCATE is a Data Definition Language (DDL) statement, while DELETE is a Data Manipulation Language (DML) statement.
