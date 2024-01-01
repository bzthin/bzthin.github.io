---
title: Core Concepts
sidebar: technical_sidebar
permalink: /system_design_core_concepts
---

## Databases
- SQL vs NoSQL
- Database replication can be done by having a master and slaves concept.

## Load balancer
- A load balancer evenly distributes incoming traffic among web servers that are defined in a
load-balanced set

## Scaling
- Vertical scaling, referred to as “scale up”, means the process of adding more power (CPU,
RAM, etc.) to your servers. 
- Horizontal scaling, referred to as “scale-out”, allows you to scale
by adding more servers into your pool of resources.

## Cache
- A cache is a temporary storage area that stores the result of expensive responses or frequently
accessed data in memory so that subsequent requests are served more quickly.
- The benefits of having a separate cache tier include better system performance, ability to reduce database workloads, and the ability to scale the cache tier independently

### Considerations for using cache
- Decide when to use cache.
- Have expiration policy
- Consistency between cache and data store
- Mitigating failures. Cache could become a single point of failure.
- Eviction policy. I.e Least recently used (LRU) cache.

## Content delivery network (CDN)
- A CDN is a network of geographically dispersed servers used to deliver static content. CDN servers cache static content like images, videos, CSS, JavaScript files, etc.
- This enables static content to be cached on dispersed servers so users visiting a website will receive the content from the server closest to him which reduces latency.

### Considerations for using CDN
- Cost
- Appropriate cache expiry
- CDN fallback
- Invalidating files in CDN methods

## Stateful architecture
- A stateful architecture remembers client data (state) from one request to the next. 
- For example, user A information is sent to server 1. All requests of user A now needs to be routed to server 1 as other servers does not have the information

## Stateless architecture
- A stateless architecture uses a shared storage to store data. This allows HTTP requests from users to be sent to any web servers, which fetch state data from the shared data store.
- A stateless system is simpler, more robust, and scalable. It also allows auto scaling to be achieved easily.

## Messaging queue
- A message queue is a durable component, stored in memory, that supports asynchronous communication.
- Input services, called producers/publishers, create messages, and publish them to a message queue. Other services or servers, called consumers/subscribers, connect to the queue, and perform actions defined by the messages

## Logging, metrics, automation
- When working with a small website that runs on a few servers, logging, metrics, and automation support are good practices but not a necessity. However, now that your site has grown to serve a large business, investing in those tools is essential. 

## Database sharding (horizontal scaling)
- Sharding separates large databases into smaller, more easily managed parts called shards. Each shard shares the same schema, though the actual data on each shard is unique to the shard.
- Sharding key (known as a partition key) consists of one or more columns that determine how data is distributed. The key is used to find the particular shard to access for the data.

### Sharding issues
- Resharding data: When shard exhaustion happens. Can be resolved by consistent hashing.
- Celebrity problem: Overloading in one shard. Can be solved by better partitioning.
- Join and de-normalization: Hard to join data across shards. Common wordaround is to denormalize the database to a single table.