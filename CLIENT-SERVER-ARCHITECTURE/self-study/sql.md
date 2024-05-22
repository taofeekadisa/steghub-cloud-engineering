## **Structured Query Language (SQL)**

### **Introduction**
Structured query language (SQL) is a programming language for storing and processing information in a relational database. A relational database stores information in tabular form, with rows and columns representing different data attributes and the various relationships between the data values. You can use SQL statements to store, update, remove, search, and retrieve information from the database. You can also use SQL to maintain and optimize database performance.

### **File ownership in Linux**

Structured query language (SQL) commands are specific keywords or SQL statements that developers use to manipulate the data stored in a relational database. You can categorize SQL commands as follows.

Data definition language 
Data definition language (DDL) refers to SQL commands that design the database structure. Database engineers use DDL to create and modify database objects based on the business requirements. For example, the database engineer uses the CREATE command to create database objects such as tables, views, and indexes.

### 1. Data query language

Data query language (DQL) consists of instructions for retrieving data stored in relational databases. Software applications use the SELECT command to filter and return specific results from a SQL table. 

### 2. Data manipulation language
Data manipulation language (DML) statements write new information or modify existing records in a relational database. For example, an application uses the INSERT command to store a new record in the database.

### 3. Data control language
Database administrators use data control language (DCL) to manage or authorize database access for other users. For example, they can use the GRANT command to permit certain applications to manipulate one or more tables. 

### 4. Transaction control language
The relational engine uses transaction control language (TCL) to automatically make database changes. For example, the database uses the ROLLBACK command to undo an erroneous transaction.

### **Common SQL**

### 1. SELECT

SELECT is probably the most commonly-used SQL statement. You'll use it pretty much every time you query data with SQL. It allows you to define what data you want your query to return.

For example, in the code below, we’re selecting a column called name from a table called customers.

```sql
SELECT name
FROM customers;
```
### 2. FROM

FROM specifies the table we're pulling our data from:

```sql
SELECT name
FROM customers;
```

### 3. WHERE

WHERE filters your query to only return results that match a set condition. We can use this together with conditional operators like =, >, <, >=, <=, etc.

```sql
SELECT name
FROM customers
WHERE name = ‘Bob’;
```
### 4. GROUP BY

The GROUP BY statement groups rows with the same values into summary rows. The statement is often used with aggregate functions. For example, the code below will display the average age for each name that appears in our customers table.

```sql
SELECT name, AVG(age)
FROM customers
GROUP BY name;
```

### 5. ORDER BY

ORDER BY sets the order of the returned results. The order will be ascending by default.

```sql
SELECT name
FROM customers
ORDER BY age;
```

###### Reference 1:https://aws.amazon.com/what-is/sql/#:~:text=Structured%20query%20language%20(SQL)%20is,relationships%20between%20the%20data%20values.

###### Reference 2: https://www.dataquest.io/blog/sql-commands/
