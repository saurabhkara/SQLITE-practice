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
