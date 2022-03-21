---
title: SQL Full Course by freeCodeCamp
geekdocCollapseSection: true
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Intro](#Intro)
  - [Primary key](#Intro#Primary key)
    - [Foreign Key](#Intro#Primary key#Foreign Key)
    - [Composite key](#Intro#Primary key#Composite key)
- [SQL Basics](#SQL Basics)
  - [Queries](#SQL Basics#Queries)
  - [Creating table](#SQL Basics#Creating table)
  - [Adding values](#SQL Basics#Adding values)
  - [Constraints](#SQL Basics#Constraints)
  - [Update and delete rows](#SQL Basics#Update and delete rows)
- [Queries](#Queries)

</div>
{{<toc>}}


# Intro

A database is a collection of related information. These can be stored in many
ways, one of the most efficient one being a *Database Management System* or
DBMS, like SQL, which are CRUD systems.

Rational Databases like SQL organize data into one or more tables, where each
table has columns and rows, and a unique key which identifies each row.

Relational Database Management Systems or RDBMS help users create an maintain a
relational database. Some examples are MySQL, Oracle, MariaDB or PostgreSQL.
Here, **SQL** is a Structured Query Language, which is:
- Standardized language for interacting with RDBMS.
- Used to perform CRUD operations as well as other administrative tasks.
- Used to define tables and structures.
- SQL code used on one RDBMS is not always portable to another without
  modification.

Queries are requests made to the DBMS for specific information. As the
database's structure becomes more complex, it's also more difficult to get
specific pieces of information we want.

## Primary key

Tables contain a number of columns that we can use to store data. For example,
we could visualize it like this:

| Student_Id       | Name            | Major           |
| ---------------- | --------------- | --------------- |
| 1                | Kate            | Sociology       |
| 2                | Jake            | Biology         |
| 3                | Claire          | English         |

We can see clearly how it works with columns and rows. In this case, we got the
first row that's a *primary key* which allow us to uniquely identify each item.

### Foreign Key

These kind of keys allow us to store the primary key from the same item but in
another table. For example, we could have a *Employee Table*, where we got a 
Foreign Key for each employee to another table, particularly a *Branch Table*.

### Composite key

This is a key that's composed of two values to uniquely define each item. For
example, we could have two branches that have the same supplier, but they buy
different things from it. So you we were to make the following table:

| branch_id        | supplier_name   | supplier_type   |
| ---------------- | --------------- | --------------- |
| 1                | Hammer Mill     | Paper           |
| 2                | Hammer Mill     | Pencils         |

We see that the only way to identify the supplier_type we need two columns as a
primary key. These can be both Foreign Keys or natural keys.

# SQL Basics

It has four types of languages in one:

- **Data Query Language:** used to query the database for information and get
  what's already stored.
- **Data Definition Language:** used for defining database schemas.
- **Data Control Language:** used for controlling access to the data in the
  database.
- **Data Manipulation Language:** used for inserting, updating or deleting data
  from the database.

## Queries

A query is a set of instructions given to a RDBMS that tells what information
you want it to retrieve for you. This allows us to get just what we need fast.

The main data types of data we can store are:
- *INT*: whole numbers.
- *DECIMAL(M,N)*: decimal numbers.
- *VARCHAR(N)*: string of text of length N.
- *DATE:* "YYYY-MM-DD".
- *TIMESTAMP:* "YYYY-MM-DD HH:MM:SS".
- *BLOB:* binary large object which stores data.

## Creating table

We can create a table with some columns like: `CREATE TABLE name ();`. 

```SQL
CREATE TABLE students(
  student_id INT PRIMARY KEY,
  name VARCHAR(32),
  major VARCHAR(32),
);
```

To see if it's created correctly, you can use the command `DESCRIBE name;`.

## Adding values

To add a value or ROW, we could use the following:

```SQL
INSERT INTO students VALUES(1, "Jack", "Biology") 
```

Where the values need to be given in the specific order of how the table was
created. But we also could create a `NULL` value by doing the following:

```SQL
INSERT INTO students(student_id, name) VALUES(2, "Claire") 
```

## Constraints

In the last case, the table is going to show the `NULL` value for Claire, as we
might not know the major yet. But we could also create a column where this
isn't allowed, like this:

```SQL
CREATE TABLE students(
  student_id INT PRIMARY KEY,
  name VARCHAR(32) NOT NULL,
  major VARCHAR(32) UNIQUE,
);
```

Here, the `NOT NULL` impedes the column to have a null value. On the other
hand, the `UNIQUE` tag in the last column rejects any value that's not unique
in this table.


Another option is a `DEFAULT` which works like this:

```SQL
CREATE TABLE students(
  student_id INT PRIMARY KEY,
  name VARCHAR(32) NOT NULL,
  major VARCHAR(32) DEFAULT "Undecided",
);
```

Now, if someone doesn't provide a major, it'll give the "Undecided" value.
Lastly, we got the `AUTO_INCREMENT` like the following, that it autocreate the
the ID and auto increment its value:

```SQL
CREATE TABLE students(
  student_id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(32) NOT NULL,
  major VARCHAR(32) DEFAULT "Undecided",
);
```

This will start from 1 and keep incrementing.

## Update and delete rows

If we wanted to update a value, we could to the following:

```SQL
UPDATE students
SET major = "Bio"
WHERE major = Biology
```

Other logic operations are:
- Not equals: `<>` 
- Greater/equals than: `>` / `>=` 
- Lesser/equals than: `<` / `<=` 

We can use other operators like:

- `OR` for a $\lor$ operation.
- `AND` for a $\land$ operation.
- `IN (1,2,3)` for a $\lor$ operation with multiple values.

To **delete** rows, we could do something very similar, like:

```SQL
DELETE students
SET major = "Bio"
WHERE major = Biology
```

# Queries

We can get data by using the `SELECT` keyword, the most basic being:

```SQL
SELECT * 
FROM student;
```

This would return all the values from the table. The `*` can be replaced with
the value we want to get.

We also could order the information by using `ORDER BY`, like the following. We
could also add a `DESC` after the `name` to flip the order.

```SQL
SELECT name, major
FROM student
ORDER BY major, student_id;
```

This example first will order by the major, and then it'll look for the
student_id. You can see that we can order by items we didn't ask for, and have
more than just one ordering factor.

Other two useful commands are `LIMIT`, which it's going to limit the response
to the first two results, and lastly the `WHERE` command, which allows us to
cherrypick a value, like this:

```SQL
SELECT name, major
FROM student
WHERE mayor = "Chemistry" OR student_id = 1
```


