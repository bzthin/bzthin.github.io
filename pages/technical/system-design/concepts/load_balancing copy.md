---
title: Load Balancing
sidebar: technical_sidebar
permalink: /system_design_load_balancing
---

## Load balancer
- A load balancer evenly distributes incoming traffic among web servers that are defined in a load-balanced set
- We can add LBs at 
  - Between the user and the web server
  - Between web servers and an internal platform layer, like application servers or cache servers
  - Between internal platform layer and database.

### Uses
- Improving website performance
- Ensuring high availability and reliability
- Scalability
- Redundancy
- Network optimization
- Geographic distribution
- Application performance
- Security
- Cost savings
- Content caching

### Algorithms
- Round Robin
- Least Connections
- Weighted Round Robin
- Weighted Least Connections
- IP Hash
- Least Response Time
- Random
- Least Bandwidth
- Custom Load

### Types
- Hardware Load Balancing
- Software Load Balancing
- Cloud-based Load Balancing 
- DNS Load Balancing
- Global Server Load Balancing (GSLB)
- Hybrid Load Balancing (Hardware + software + cloud)
- Layer 4 Load Balancing (transport layer)
- Layer 7 Load Balancing (application layer)