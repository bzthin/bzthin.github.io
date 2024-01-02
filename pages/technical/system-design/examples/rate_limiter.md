---
title: Rate Limiter
sidebar: technical_sidebar
permalink: /system_design_examples_rate_limiter
---

## Requirements
- Client side or server side?
- Throttle based on what?
- Scale of system?
- Distributed environment?
- Do we need to inform user if they are throttled?

## Solutions
- Rate limiter in API gateway, but depends on the company tech stack.
- Types of throttling:
  - Hard Throttling
  - Soft Throttling
  - Elastic or Dynamic Throttling
- Algorithms for rate limiting:
  - Token bucket (AWS APIGateway uses this)
  - Leaking bucket
  - Fixed window counter
  - Sliding window log
  - Sliding window counter
- Use in-memory cache because it is fast and supports time-based expiration strategy. (Like Redis or AWS ElastiCache)
- Return extra info when error in header. (Remaining, limit, retry after x time).
- Add monitoring to ensure rate limiting works.

## Issues
- Race conditions in distributed environment. (When reading from cache)
  - Solution: Two strategies are commonly used to solve the problem: Lua script and sorted sets data structure in Redis.
- Synchronization issue when multiple rate limiting servers are used.
  - Solution: Use a centralized datastore.