---
title: Database
sidebar: technical_sidebar
permalink: /system_design_database
---

## Denormalized vs. Normalized Databases
- Normalization is used to remove redundant data from the database and to store non-redundant and consistent data into it.	
- Denormalization is used to combine multiple table data into one so that it can be queried quickly.

## Data Partitioning
- Data partitioning is a technique used in distributed systems and databases to divide a large dataset into smaller, more manageable parts, referred to as partitions.
- Horizontal Partitioning also known as sharding, horizontal data partitioning involves dividing a database table into multiple partitions or shards, with each partition containing a subset of rows. 
- Vertical data partitioning involves splitting a database table into multiple partitions or shards, with each partition containing a subset of columns. This technique can help optimize performance by reducing the amount of data that needs to be scanned, especially when certain columns are accessed more frequently than others.

## Partitioning Criteria
- Key or Hash-based partitioning
- List partitioning
- Round-robin partitioning
- Composite partitioning

## Indexes
- The goal of creating an index on a particular table in a database is to make it faster to search through the table and find the row or rows that we want.
- Indexes can be created using one or more columns of a database table, providing the basis for both rapid random lookups and efficient access of ordered records.