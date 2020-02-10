##### <h1>Database setup and maintenance</h1>


---


##   **What is a build script ?**
- A build script is a script used to setup a new Database , from scratch.
- It's a prewritten set of commands that creates your Database,for example the build_db.sql we used.



---


## Why do you need one?


- The main purpose is to prove that what you are working on can succesfully create a working Database.
- It automates the process of setting up a *Working* database.
- The build will be constant, no need to doubt if we had errors creating the DB.
- A database is likely to be built many times during development and testing.


---

-   **What is database migration?**
Database migration means moving our data from one platform to another.
<u>Benefits of database migration:</u>
1)**Costs**: Saving money;
Often companies will move from an on-premise database to a cloud database. This saves on infrastructure as well as the manpower and expertise needed to support it.
2)**Modernized software**:
Moving from an outdated system or legacy systems to a system that is designed for modern data needs.
3)**One source of truth**: Moving all the data into one place that is accessible by all divisions of the company.
For example, the IT department might use one database while the Marketing group uses another database and these systems cannot "talk" to each other.

---


Database migration is a multiphase process that involves some or all the following steps:

1)**Assessment**:
Gather business requirements, assess the costs and benefits, and perform data profiling. Data profiling is a process by which we get to know our existing data and database schema.
2)**Database schema conversion**:
Convert the schemas so that the structure of the data works with the new database.
3)**Data migration**:After completing all the preliminary requirements, we’ll need to actually.
4)**Testing and tuning**. Once we’ve moved the data, we need to verify that the data: was moved correctly, is complete, isn’t missing values, doesn’t contain null values, and is valid.









___

# A simple buildscript example
```
BEGIN;

DROP TABLE IF EXISTS webahead;

CREATE TABLE webahead (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    role VARCHAR(100) NOT NULL
);

INSERT INTO
    webahead (name, role)
VALUES
    ('Mario', 'Mentor'),
    ('Aysam', 'Mentee'),
    ('Ivan', 'The Joker');

COMMIT;
```

---

## Running the script in the terminal : 
  Using pgcli : 
        enter the command \i path_to_file
        
  

___


**References:**
* [https://www.alooma.com/blog/what-is-database-migration](https://www.alooma.com/blog/what-is-database-migration)

* https://www.red-gate.com/simple-talk/sql/database-delivery/better-ways-to-build-a-database/