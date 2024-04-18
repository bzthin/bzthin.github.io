---
title: SQL vs NoSQL
sidebar: technical_sidebar
permalink: /system_design_sql_vs_nosql
---

## SQL databases
- Represent and store data in tables and rows. 
- Can perform join operations using SQL across different database tables.
- Example: MySQL, Oracle database, PostgreSQL, etc. 

## NoSQL databases
- Also called NoSQL databases. Grouped into four categories: 
  - key-value stores, 
  - graph stores, 
  - column stores, 
  - document stores. 
- Join operations are generally not supported in non-relational databases.
- Example: CouchDB, Neo4j, Cassandra, HBase, Amazon DynamoDB, etc.

## Relational vs non relational 
- SQL databases are relational, NoSQL are non-relational.
- SQL databases use structured query language and have a predefined schema. NoSQL databases have dynamic schemas for unstructured data.
- SQL databases are vertically scalable, NoSQL databases are horizontally scalable.
- SQL databases are table based, while NoSQL databases are document, key-value, graph or wide-column stores.
- SQL databases are better for multi-row transactions, NoSQL are better for unstructured data like documents or JSON.
- SQL databases are ACID compliant. NoSQL solutions sacrifice ACID compliance for performance and scalability.

## ACID
- ACID is a set of properties of relational database transactions.
- Atomicity - Each transaction is all or nothing
- Consistency - Any transaction will bring the database from one valid state to another
- Isolation - Executing transactions concurrently has the same results as if the transactions were executed serially
- Durability - Once a transaction has been committed, it will remain so

## Denormalized vs. Normalized Databases
- Normalization is used to remove redundant data from the database and to store non-redundant and consistent data into it.	
- Denormalization is used to combine multiple table data into one so that it can be queried quickly.

## Sharding
- Sharding is a database architecture pattern related to horizontal partitioning — the practice of separating one table’s rows into multiple different tables, known as partitions. 
- Sharding involves breaking up one’s data into two or more smaller chunks, called logical shards.
- The logical shards are then distributed across separate database nodes, referred to as physical shards, which can hold multiple logical shards. 