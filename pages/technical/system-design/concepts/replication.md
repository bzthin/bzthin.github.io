---
title: Replication
sidebar: technical_sidebar
permalink: /system_design_replication
---

## Redundancy
- Redundancy refers to the duplication of critical components or functions to increase the reliability, availability, and fault tolerance of a system. 

## Replication
- Replication means sharing information to ensure consistency between
redundant resources, such as software or hardware components, to improve
reliability, fault-tolerance, or accessibility.
- Replication is widely used in many database management systems (DBMS),
usually with a master-slave relationship between the original and the
copies. The master gets all the updates, which then ripple through to the
slaves. Each slave outputs a message stating that it has received the update
successfully, thus allowing the sending of subsequent updates.

## Quorum
- A quorum refers to the minimum number of nodes or components that must agree or acknowledge an operation for it to be considered successful or valid. 
- It ensures that a distributed system remains consistent and available even in the presence of failures or network partitions. 
- In a system with n replicas
  - If a write is acknowledged by w replicas (write quorum)
  - And we subsequently read from r replicas (read quorum)
  - and r+w > n
  - Then the read will see the previously written value (or a value that subsequently overwrote it)
  - Read quorum and write quorum share >=1 replica