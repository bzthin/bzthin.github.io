---
title: Databases
sidebar: technical_sidebar
permalink: /misc_databases
---

## SQL vs NoSQL
- SQL databases are relational, NoSQL are non-relational.
- SQL databases use structured query language and have a predefined schema. NoSQL databases have dynamic schemas for unstructured data.
- SQL databases are vertically scalable, NoSQL databases are horizontally scalable.
- SQL databases are table based, while NoSQL databases are document, key-value, graph or wide-column stores.
- SQL databases are better for multi-row transactions, NoSQL are better for unstructured data like documents or JSON.

## Denormalized vs. Normalized Databases
- Normalization is used to remove redundant data from the database and to store non-redundant and consistent data into it.	
- Denormalization is used to combine multiple table data into one so that it can be queried quickly.

## Sharding
- Sharding is a database architecture pattern related to horizontal partitioning — the practice of separating one table’s rows into multiple different tables, known as partitions. 
- Sharding involves breaking up one’s data into two or more smaller chunks, called logical shards.
- The logical shards are then distributed across separate database nodes, referred to as physical shards, which can hold multiple logical shards. 