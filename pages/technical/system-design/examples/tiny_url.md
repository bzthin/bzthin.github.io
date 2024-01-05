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
- Page 7


## Step 3 - Design deep dive

## Step 4 - Wrap up