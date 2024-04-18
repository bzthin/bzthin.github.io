---
title: Caching
sidebar: technical_sidebar
permalink: /system_design_caching
---

## Caching
- The cache is a high-speed storage layer that sits between the application and the original source of the data, such as a database, a file system, or a remote web service.

## Types
- Client caching. Caches can be located on the client side (OS or browser), server side, or in a distinct cache layer.
- Content distribution network (CDN). CDNs are a kind of cache that comes into play for sites serving large amounts of static media
- Database caching. Your database usually includes some level of caching in a default configuration, optimized for a generic use case. Tweaking these settings for specific usage patterns can further boost performance.
- Application server cache. Placing a cache directly on a request layer node enables the local storage of response data.

## Cache invalidation
- If the data is modified in the database, it should be invalidated in the cache
- Write-through cache: Data is written both to the cache and the underlying storage (such as a disk or database) simultaneously or immediately after being written to the cache.
- Write-around cache: Data is written directly to the underlying storage without being written to the cache first. 
- Write-back cache: In a write-back cache, data is initially written only to the cache and is later asynchronously written to the underlying storage in the background.
- Differences lies in 
  - Data Consistency
  - Latency
  - Data Loss Risk
  - I/O Load:

## Cache eviction
  - FIFO
  - LIFO
  - LRU
  - MRU
  - LFU
  - RR (Random replacement)


## Cache read strategies
- Cache-Aside (Lazy Loading): In cache-aside (also known as lazy loading), the application first checks the cache for the requested data. If the data is not found in the cache (a cache miss), the application fetches the data from the underlying data source (such as a database) and then stores it in the cache before returning it to the requester.
- Read-Through Cache (Read-Through): In read-through cache, the application does not directly interact with the cache. Instead, it reads data from the cache through a caching layer or cache proxy. When data is requested, the caching layer automatically checks the cache. If the data is not found (a cache miss), the caching layer fetches the data from the underlying data source, caches it, and then returns it to the application.