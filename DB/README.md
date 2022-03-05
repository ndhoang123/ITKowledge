# Database
- Content:
    + [Key](#key)
    + [Trigger](#trigger)
    + [Stored Procedure and Function](#stored-procedure-and-function)
    + [DML and DDL](#dml-ddl)
    + [Index](#index)

## Key
### **Primary key**
- Primary key is an attribute or set of attributes used to indetify uniquely each row.
- A table can have **only one** primary key. And, the primary key must contain the **unique** value and **not null** value.
### **Foreign key**
- A **foreign key** is a column or combination of two columns that are used to establish the connection between two tables.

## Trigger
- A trigger is a special type of stored procedure that automatically runs when an event occurs in the database server.

## Stored Procedure and Function
### **Stored procedure**
- **Stored procedure** are used as script. They run a series of command for you and you can schedule them to run a several times. Usually, runs multiples DML statements like **INSERT**, **SELECT**, **DELETE**.
- Stored procedure does not or returns value.
- Stored procedure can have input/output parameters. And, it has one or more parameter.
- Use `exec` to execute the stored procedure.
- We can use the function in SP.
### **Function**
- **Function** are used as method. You pass it sth and it returns a result. Should be small and fast - does it on the fly. Usually used in a SELECT statement.
- It has only one input parameter, it can be a table or basically a scalar value.
- We cannot call the SP in function.

## DML, DDL
### DML (Data manipulation language)
- DML events are INSERT, UPDATE, DELETE on table or view.
### DDL (Data definition language)
- DDL events are ALTER, DROP, CREATE.

## Index
- An **index** on an attribute A of a relation is a data structure that makes it efficient to find those tuples that have a fixed value for attribute A.
### **Selections of indexes**
- Two important factors to consider:
    + The existence of an index on an attribute may speed up greatly the execution of those queries in which a value, or range of values, is specified for that attribute, and may speed up joins involving that attribute as well.
    + On the other hand, every index built for one or more attributes of some relation makes insertions, deletions, and updates to that relation more complex and time-consuming.