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

