# Schemas and relationships

Schema is basically the design of your database. The number of tables in a database, the relation between the tables, and the tables altogether constitute a schema in database. It can be thought of as the structure of your database

---

## Why would we need a schema? 

A database Schema give you as a developer a high level view of the structure and relationship of the tables in your database. Database Schema is valuable in documenting your database in such a way that others can understand your design.


A database schema is a way to logically group objects such as tables, views, stored procedures.

---


## What are primary keys and why do we need them?

The main purpose of a primary key is to implement a relationship between two tables in a relational database. More specifically, the primary key is the "target" which a foreign key can reference. You cannot declare a foreign key in table B to relate to table A unless the primary key in table A has been defined.


---

<img src="https://i.imgur.com/5d4CySg.png">

---

## How to create relationships:

1. Download Tinder.
2. You're welcome.

> FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE