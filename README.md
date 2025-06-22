"# SQLITE-practice"

### Database

A database is an organized collection of data, typically stored electronically in a computer system, that can be easily accessed, managed, and updated.

### SQLite

SQLite is a lightweight, embedded, relational database management system (RDBMS).

- Lightweight : SQLite does not run as a separate server process like MySQL or PostgreSQL.
- Embedded : It is embedded directly into the application — your app accesses the database directly via a library.
- Self-contained: All data (tables, indexes, metadata, etc.) is stored in a single file on disk.
- Relational Database: It supports SQL (Structured Query Language) for querying and managing data, just like larger RDBMS system. You can create tables, run joins, transactions, indexes, constraints, etc.
- Zero configuration: No setup or installation of server software required. You just need the SQLite library.
- Serverless: There’s no server. The application reads and writes directly to the database file.

### Installation

- Download SQLite from website
- Extract from zip
- set Environment variable in path of SQLite
- Fire the command in CMD to verify sqlite3 is installed

### Create Database

- fire this command in terminal to create database `sqlite3 database_name.db`
- to create in file fire this command in terminal `.database` after above command
- fire this command in terminal `.databases` to see the databases
- `.tables` command to see the table
- `.shell cls` to clear terminal in sqlite

### Table Creation

- `.tables` command to see the table in database
- `CREATE TABLE TABLE_NAME(col1 INT, col2 INT, col3 TEXT, col4 REAL);` command to create table

```
sqlite> CREATE TABLE EMPLOYEE
   ...> (
(x1...> eName TEXT,
(x1...> eId INT,
(x1...> age INT,
(x1...> Salary REAL,
(x1...> )
   ...> ;
```

- `.tables` to see the tables
- `.schema TABLE_NAME` to see table details

### Insert data into table

- `.tables` command to see table in database
- `.schema Table_Name` to see the details of table like number of columns and data type
- `INSERT INTO TABLE_NAME VALUES(value1, value2, value3, value4);` command to insert row

```
INSERT INTO EMPLOYEE VALUES(1,'Saurabh',28,75000);
```

### SELECT(View) all data from table

- `SELECT * FROM TABLE_NAME;` to view all data in table
- `SELECT COLUMN_NAME FROM TABLE_NAME;` to view single colum data in table

### UPDATE(edit) data in table

- `UPDATE EMPLOYEE SET salary=90000 WHERE empId=1;` to update data in table
- `SELECT * FROM EMPLOYEE;` to view all data of table

### DELETE(Remove) data from table

- `DELETE FROM EMPLOYEE WHERE empId=3;` to delete data of employee whose Id=3;
- `SELECT * FROM EMPLOYEE;`
- Must add `WHERE` cluase otherwise it will delete all rows of table

### DROP(Delete) table from database

- `DROP TABLE TABLE_NAME` to drop table from database
- `.tables` to see the tables

```
sqlite> DROP TABLE DEPARTMENT
   ...> ;
sqlite> .tables
```

### DROP DATABASE

- `DROP DATABASE Database_Name;` to delete database

### To Download Table in CSV file

- `.header on` command to add header row in csv file
- `.mode csv` command to download file in csv format
- `.once file_path\file_name.csv` to download once at this location in csv format
- `SELECT * FROM EMPLOYEE;` to add data into csv file

```
sqlite> .header on
sqlite> .mode csv
sqlite> .once C:\Users\skara\Desktop\sqlite3Learning\abc.csv
sqlite> SELECT * FROM EMPLOYEE;
```

### ALTER(Update) table name or colum or Add colum

- `.tables` to see the table name
- `ALTER TABLE Table_Name RENAME TO New_Table_Name;` to rename table name

```
sqlite> .tables
EMPLOYEE
sqlite> ALTER TABLE EMPLOYEE RENAME TO Employee_List;
sqlite> .tables
Employee_List
```

- `.schema` to see the table details
- `ALTER TABLE Table_Name ADD COLUMN column_name DataType;`

```
.schema Employee_List
CREATE TABLE IF NOT EXISTS "Employee_List"(empId INT,empName TEXT,empAge INT, salary REAL);

sqlite> ALTER TABLE Employee_List ADD COLUMN deptId INT;
sqlite> SELECT * FROM Employee_List;
empId,empName,empAge,salary,deptId
1,Saurabh,28,90000.0,
2,ANKIT,26,20000.0,
4,HARI,21,15000.0,

UPDATE Employee_List SET deptId=1001 WHERE empId<=4;

```

### JOIN

A JOIN combines rows from two or more tables based on a related column between them.

Why JOIN

- To retrieve meaningful data spread across multiple tables.
- To avoid data duplication (normalization).
- To enforce relationships between tables.

### INNER JOIN

Returns records where there is a match in both tables.

- `SELECT E.EmpId, E.eName, E.salary, D.dName FROM Employee_List E INNER JOIN Department_List D ON E.departId = D.deptId `

```
sqlite> SELECT E.eName, E.empId, D.dname FROM Employee_List E INNER JOIN Department_List D ON E.departId= D.deptId;


saurabh|1|IT
sneha|2|IT
sneha|3|HR
```

### LEFT JOIN

Returns all rows from the left table, even if there’s no match in the right table.
If no match, columns from the right table will be NULL.

- `SELECT E.empId, E.empName, E.salary, D.dname FROM Employee_List E LEFT JOIN Department_List ON E.departId = D.deptId;`

```
sqlite> SELECT E.eName, E.empId, D.dname FROM Employee_List E LEFT JOIN Department_List D ON E.departId = D.deptId;


saurabh|1|IT
sneha|2|IT
sneha|3|HR
Priti|3|SALES
Ashis|3|
```

### RIGHT JOIN

Returns all rows from the right table, even if there’s no match in the left table.
(SQLite doesn’t support RIGHT JOIN directly, but many DBs do.)

### FULL OUTER JOIN

Returns all rows when there is a match in one of the tables.
Includes rows from both tables that don’t have matches in the other.

### CROSS JOIN

Returns a cartesian product: every row of the first table combined with every row of the second table

- `SELECT E.eName, D.dname FROM Employee_List E  CROSS JOIN Department_List D;`

```
sqlite> SELECT E.eName, D.dname FROM Employee_List E  CROSS JOIN Department_List D;


saurabh|IT
saurabh|HR
saurabh|SALES
saurabh|SALES
sneha|IT
sneha|HR
sneha|SALES
sneha|SALES
sneha|IT
sneha|HR
sneha|SALES
sneha|SALES
Priti|IT
Priti|HR
Priti|SALES
Priti|SALES
Ashis|IT
Ashis|HR
Ashis|SALES
Ashis|SALES

```
