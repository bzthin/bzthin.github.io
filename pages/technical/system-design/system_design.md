---
title: System Design
sidebar: technical_sidebar
permalink: /system_design
---


# System Design
Usually no right answers and will be more discussion based. You should drive the conversation.

## Key concepts
- Key characteristics of a distributed system include Scalability, Reliability, Availability, Efficiency, and Manageability. 
  - Scalability
    - Horizontal vs vertical scaling
  - Reliability (with redundancy)
  - Availability
  - Efficiency
  - Maintainability
- Load balancing
- Caching 
  - Application server cache
  - Content distribution network (CDN)
  - Cache invalidation
  - Cache eviction
- Data partitioning (or database partitioning)
  - Horizontal partitioning (data sharding)
  - Vertical partitioning
  - Directory Based Partitioning
- Database indexing
- Proxy server
- Redundancy and replication
- SQL vs NoSQL
- CAP 
  - CAP theorem states that it is impossible for a distributed software system to simultaneously provide more than two out of three of the following guarantees (CAP): Consistency, Availability, and Partition tolerance
- Consistent Hashing
- Asynchronous processing & queues
- Networking metrics
  - Bandwidth
  - Throughput
  - Latency


## Considerations
- Failures/Exceptions
- Availability and reliability 
- Read heavy vs write heavy
- Security


## Steps
- Requirements expectations and clarifications  
  - Use cases
  - Scenarios that will not be covered
  - Who are our users
  - How many users are we expecting
  - How will they use it.
  - Write those down in functional, non functional requirements and extra requirements

- Back of the envelope estimation. 
  - Throughput (amount of data that is successfully transmitted through a system in a certain amount of time)
  - Bandwidth (amount of data that can be transmitted and received during a specific period of time)
  - Read/Write Latency. (Amount of time in ms it takes for a message to be sent or received)
  - Read/Write ratio
  - Traffic estimation for read write
  - Storage estimate
  - Memory estimate

- High level design
  - System Interface definition. State APIs required from the system to ensure understanding on requirements.
  - Draw the major components without going too deep.
  - Defining database schema.
  - Walk through end to end flow for read/ & write.
  
- Deep dive
  - Scaling algorithm
  - Scaling individual components (Availability, consistency, scale) 
  - Consider following components how it can help
    - DNS
    - CDN
    - Load balancer
    - Reverse proxy
    - Application layer scaling (Microservices)
    - Database
    - Caches
    - Asynchroism (Messages/tasks queues)
    - Communication (TCP, UDP, REST, RPC)
  - Justify design, evaluate pros and cons, bottlenecks and tradeoffs