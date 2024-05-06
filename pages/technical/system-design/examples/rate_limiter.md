---
title: Rate Limiter
sidebar: technical_sidebar
permalink: /system_design_examples_rate_limiter
---

## Problem
- Design a rate limiter.

## Step 1 - Requirements clarifications
- Functional
  - Accurately limit excessive requests
  - Server side rate limiter
  - Flexible to support different throttle rules whether if its by IP, user ID or other properties.
  - Users throttled need to be informed via proper exceptions.
- Non functional
  - Support large number of requests in distributed environment and high availbility.
  - Low latency and little memory as possible

## Step 2 - Propose high-level design and get buy-in
- Put rate limiter as a middleware like API gateway.
- Rate limiter to return error 429 when throttled.
- 5 types of rate limiting algorithms
  - Token bucket
  - Leaking bucket
  - Fixed window counter
  - Sliding window log
  - Sliding window counter
- High level architecture
![](/images/rate_limiter_1.png)
  - We use rate limiter as middleware and a in memory cache as database is slow
  due to disk access.
  - The client sends a request to rate limiting middleware.
  - Rate limiting middleware fetches the counter from the corresponding bucket in elastic cache and checks if the limit is reached or not.
  - If the limit is reached, the request is rejected.
  - If the limit is not reached, the request is sent to API servers. Meanwhile, the system increments the counter and saves it back to elastic cache.

## Step 3 - Design deep dive
- How are rate limiting rules created? Where are they stored?
  - Rules are written as configurations and stored on disk.
- How to handle requests that are rate limited?
  - API will return HTTP response 429.
- We need to add monitoring to ensure rate limiting algorithms and rules are effective

## Step 4 - Wrap up
- Hard vs soft rate limiting
- Rate limiting at different OSI levels.


## Notes
### Token bucket algorithm
- A token bucket is a container that has pre-defined capacity. Tokens are put in the bucket at preset rates periodically. Once the bucket is full, no more tokens are added.
- Pros: 
  - Easy to implement
  - Memory efficient
  - Allows burst traffic
- Cons:
  - Two parameters bucket size and refill rate are hard to tune properly.

### Leaking bucket algorithm
- The leaking bucket algorithm is similar to the token bucket except that requests are processed at a fixed rate like a queue and when queue is full, new requests are dropped.
- Pros:
  - Efficient memory size
  - Stable outflow rate
- Cons:
  - Burst of traffic fills up queu
  - Two parameters bucket size and outflow rate are hard to tune properly.

### Fixed window counter
- The fixed window counter algorithm divides time into fixed-sized windows and assigns a counter to each window. Each request increments the counter by one. When the counter reaches a predefined threshold, further requests are dropped until a new time window starts.
- Pros:
  - Easy and efficient memory
  - Resetting quota at a window size might fix some use cases.
- Cons:
  - Spike in traffic in edges of window could exceed rate limit quota

## Sliding window log
- The sliding window log algorithm regulates request acceptance by maintaining a timestamp log, removing outdated entries, and allowing requests only if the log size is within the permitted count.
- Pros:
  - Rate limiting implemented by this algorithm is very accurate. In any rolling window,requests will not exceed the rate limit
- Cons:
  - The algorithm consumes a lot of memory because even if a request is rejected, its timestamp might still be stored in memory.

## Sliding window counter
- The sliding window counter algorithm is a hybrid approach that combines the fixed window counter and sliding window log.
- Formula is: Requests in current window + requests in the previous window * overlap percentage of the rolling window and previous window
- Pros:
  - It smooths out spikes in traffic because the rate is based on the average rate of the previous window.
  - Memory efficient.
- Cons: 
  - It only works for not-so-strict look back window. It is an approximation of the actual rate because it assumes requests in the previous window are evenly distributed.