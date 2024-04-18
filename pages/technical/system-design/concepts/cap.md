---
title: CAP
sidebar: technical_sidebar
permalink: /system_design_cap
---

## CAP
- Consistency: A system is considered consistent if all nodes see the same data at the same time. This means that any read operation should return the most recent write operation's result, ensuring that the system maintains a single, up-to-date version of the data.
- Availability: A system is considered highly available if it continues to operate and respond to requests despite failures, ensuring that every request receives a response, either a success or an error.
- Partition Tolerance: A system is considered partition-tolerant if it can continue to operate and maintain its guarantees despite network partitions, which are situations where communication between nodes in the system is interrupted or lost.

## CAP theorem
- The CAP theorem states that it is impossible for a distributed system to simultaneously provide all three properties: consistency, availability, and partition tolerance and at max guarantees two.

