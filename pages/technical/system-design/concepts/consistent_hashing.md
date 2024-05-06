---
title: Consistent Hashing
sidebar: technical_sidebar
permalink: /system_design_consistent_hashing
---

## How it works
Consistent hashing is a technique used in distributed computing and caching systems to efficiently distribute data across a dynamically changing set of servers or nodes while minimizing the amount of data movement when nodes are added or removed from the system. It aims to evenly distribute the load and maintain a balanced distribution of data, even as the system scales up or down.

Here's how consistent hashing works:

1. **Hash Function**: Consistent hashing relies on a hash function to map both data items and server/node identifiers to a numerical range. The hash function typically produces a large integer value as output.

2. **Ring Structure**: Imagine a ring structure represented by a range of hash values (e.g., from 0 to 2^32 - 1), where each point on the ring corresponds to a hash value.

3. **Node Placement**: Each server or node in the system is assigned a unique identifier, such as its IP address or a randomly generated identifier. These identifiers are hashed using the same hash function used for data items, and the resulting hash values determine the positions of the nodes on the ring.

4. **Data Placement**: Data items are also hashed using the same hash function. The resulting hash values are then mapped onto the ring structure. Each data item is assigned to the closest node in a clockwise direction on the ring. This process is often referred to as "finding the owner" or "mapping the key to a node."

5. **Load Balancing**: Since each node corresponds to a range of hash values on the ring, adding or removing nodes from the system affects only the region of the ring corresponding to those nodes. This means that most of the data items remain mapped to the same nodes, minimizing the amount of data movement required when nodes are added or removed.

6. **Handling Failures**: In case of node failures or removals, consistent hashing allows the system to redistribute the affected data items to the next closest live node on the ring. This ensures that the load remains balanced across the available nodes even in the presence of failures.

Overall, consistent hashing provides a scalable and efficient approach to distributing data in distributed systems, enabling load balancing and fault tolerance while minimizing the overhead associated with node additions, removals, or failures. It is widely used in distributed caching systems, content delivery networks (CDNs), and distributed databases.

## Two issues in the basic approach
- It is impossible to keep the same size of partitions on the ring for all servers considering a server can be added or removed.
- It is possible to have a non-uniform key distribution on the ring.

## Virtual nodes
- A technique called virturl nodes or replicas is used to solve the two problems where each server is represented by multiple virtual nodes on the ring.

## Benefits of consistent hashing
- Minimized keys are redistributed when servers are added or removed.
- It is easy to scale horizontally because data are more evenly distributed.
- Mitigate hotspot key problem. Excessive access to a specific shard could cause server overload. Imagine data for Katy Perry, Justin Bieber, and Lady Gaga all end up on the same shard. Consistent hashing helps to mitigate the problem by distributing the data more evenly.