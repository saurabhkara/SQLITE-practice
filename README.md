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
