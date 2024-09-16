# AI2SQL Prompts and Snippets

Welcome to the **AI2SQL Prompts and Snippets** repository! This guide is designed to help you leverage **AI2SQL** to generate SQL queries using natural language, making database interactions more accessible and efficient.

## Table of Contents

- [Introduction to AI2SQL](#introduction-to-ai2sql)
  - [What is AI2SQL?](#what-is-ai2sql)
  - [How Does It Work?](#how-does-it-work)
- [Useful Prompts and Examples](#useful-prompts-and-examples)
  - [1. Basic Query Generation](#1-basic-query-generation)
  - [2. Filtering Data](#2-filtering-data)
  - [3. Joining Tables](#3-joining-tables)
  - [4. Aggregating Data](#4-aggregating-data)
  - [5. Creating Stored Procedures](#5-creating-stored-procedures)
  - [6. Updating Records](#6-updating-records)
  - [7. Deleting Records](#7-deleting-records)
- [Benefits of Using AI2SQL](#benefits-of-using-ai2sql)
- [Tips for Crafting Effective Prompts](#tips-for-crafting-effective-prompts)
- [Conclusion](#conclusion)
- [References](#references)

## Introduction to AI2SQL

### What is AI2SQL?

**AI2SQL** is a tool that simplifies the creation of SQL queries by interpreting natural language prompts. It's especially useful for individuals who need to interact with databases but may not be proficient in SQL syntax.

### How Does It Work?

Users input queries in plain English, and AI2SQL translates these into executable SQL commands. This allows for quick and accurate data retrieval without the need to write complex SQL code manually.

## Useful Prompts and Examples

Here are some practical prompts and their expected SQL outputs to help you get started with AI2SQL.

### 1. Basic Query Generation

**Prompt**:  
*"Retrieve all customers who are based in New York."*

**Expected Output**:

```sql
SELECT * FROM customers WHERE city = 'New York';
```

### 2. Filtering Data

**Prompt**:  
*"Show the total sales figures for the previous month."*

**Expected Output**:

```sql
SELECT SUM(sales) FROM orders WHERE order_date >= DATEADD(month, -1, GETDATE());
```

### 3. Joining Tables

**Prompt**:  
*"List all orders along with the corresponding customer names."*

**Expected Output**:

```sql
SELECT orders.*, customers.name
FROM orders
JOIN customers ON orders.customer_id = customers.id;
```

### 4. Aggregating Data

**Prompt**:  
*"Calculate the average value of all orders."*

**Expected Output**:

```sql
SELECT AVG(total_amount) FROM orders;
```

### 5. Creating Stored Procedures

**Prompt**:  
*"Create a stored procedure to fetch orders using a customer's ID."*

**Expected Output**:

```sql
CREATE PROCEDURE GetOrdersByCustomerID
@CustomerID INT
AS
BEGIN
    SELECT * FROM orders WHERE customer_id = @CustomerID;
END;
```

### 6. Updating Records

**Prompt**:  
*"Mark order number 123 as shipped."*

**Expected Output**:

```sql
UPDATE orders SET status = 'shipped' WHERE id = 123;
```

### 7. Deleting Records

**Prompt**:  
*"Delete all orders that are over a year old."*

**Expected Output**:

```sql
DELETE FROM orders WHERE order_date < DATEADD(year, -1, GETDATE());
```

## Benefits of Using AI2SQL

- **User-Friendly**: Makes database querying accessible to those unfamiliar with SQL.
- **Time-Saving**: Speeds up the process of writing queries.
- **Error Reduction**: Minimizes syntax errors common in manual coding.
- **Educational**: Helps users learn SQL by seeing natural language translated into code.

## Tips for Crafting Effective Prompts

- **Be Specific**: Clearly state what data you need and any conditions.
- **Include Table Names**: Mention specific tables if possible to guide the AI.
- **Use Clear Language**: Avoid ambiguous terms to ensure accurate translation.
- **Iterate as Needed**: Refine your prompts if the initial output isn't what you expected.

## Conclusion

AI2SQL bridges the gap between natural language and SQL, making data retrieval straightforward for users of all skill levels. By utilizing precise prompts, you can efficiently generate the SQL queries you need without extensive knowledge of SQL syntax.

## References

1. [AI2SQL Official Website](https://ai2sql.io)

---

*Disclaimer: This repository is an unofficial guide intended to help users understand and utilize AI2SQL effectively.*
