---
title: Script injections
tags: Templates, Talk, injections
description: View the slide with "Slide Mode".
---

# Script injections / safety issues

---

## What is a script injection?

---

XSS refers to an injection flaw whereby user input to a web script or something along such lines is placed into the output HTML, without being checked for HTML code or scripting.

SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.

---

## how do these happen?

**Injection attack:** SQL Injection (SQLi)

**Description:** The attacker injects SQL statements that can read or modify database data. The attacker can use SQL commands to write arbitrary files to the server and even execute OS commands. This may lead to full system compromise.

---

## Impact Potential:

* Authentication bypass
* Information disclosure
* Data loss
* Sensitive data theft
* Loss of data integrity
* Denial of service
* Full system compromise.

---

![](https://i.imgur.com/m8iAEiq.png)

###### The SQL UNION operator is used to combine the result sets of 2 or more SELECT statements. 

---

## How would you prevent script injections?

---

Most instances of SQL injection can be prevented by using parameterized queries (also known as prepared statements) instead of string concatenation within the query.

---

The following code is vulnerable to SQL injection because the user input is concatenated directly into the query:

```sql
String query = "SELECT * FROM products WHERE category = '"+ input + "'";

Statement statement = connection.createStatement();
ResultSet resultSet = statement.executeQuery(query);
```

---

![](https://i.imgur.com/AFLIoFW.png)

---

This code can be easily rewritten in a way that prevents the user input from interfering with the query structure:

```sql
PreparedStatement statement = connection.prepareStatement

("SELECT * FROM products WHERE category = ?");

statement.setString(1, input);
ResultSet resultSet = statement.executeQuery();
```


---

Parameterized queries can be used for any situation where untrusted input appears as data within the query, including the WHERE clause and values in an INSERT or UPDATE statement.

For a parameterized query to be effective in preventing SQL injection, the string that is used in the query must always be a hard-coded constant, and must never contain any variable data from any origin. Do not be tempted to decide case-by-case whether an item of data is trusted

---

### Thank you! :sheep: 

