---
title: TinyURL
sidebar: technical_sidebar
permalink: /system_design_examples_tiny_url
---

## Problem statement
- Design a URL shortening service like TinyURL.

## Step 1 - Requirements clarifications
### Functional
- Generate short url link, will redirect to original link.
- Optionally pick custom short link.
- Has a expiry TTL.

### Non Functional
- Highly available
- Redirection in real time with minimal latency.
- Not guessable

### Extended requirements:
- Analytics; e.g., how many times a redirection happened?
- Our service should also be accessible through REST APIs by other services.

### Estimations
- Traffic estimate
  - Query per second (shortening)
  - Reads per second
- Storage estimate
- Bandwidth estimate
- Memory estimate (cache)
- High level estimates example: Assuming 500 million new URLs per month and 100:1 read:write ratio following is the summary of the high level estimates for our service:
  - Traffic QPS: New URLs 200/s 
  - Traffic RPS: URL redirections 20K/s
  - Bandwidth: Incoming data 100KB/s 
  - Bandwidth: Outgoing data 10MB/s
  - Storage: For 5 years 15TB
  - Memory: For cache 170GB
 
## Step 2 - Propose high-level design and get buy-in
- High level components
- API input and output. Throttling, error handling
- Database design. 
  - Observe we need to store billions of small records and no relations with each other.
  - Two database tables, one for url link, another for user information.
  - Thus use NoSQL.


## Step 3 - Design deep dive
- How is url generated? 2 ways, using a hash function like SHA256 or generate keys offline.
- Just simply using SHA256 is not sufficient because different users with same url can get same generated url. Append an increasing sequence number or user id.
- We can generate keys offline first and stores them in a db. 
- In terms of sharding, consider partitioning by url (range based) or hash based.
- Cache URLs that are frequently accessed with LRU eviction policy

## Step 4 - Wrap up
- Telemetry. (Metrics and logging)
- Security and permissions.