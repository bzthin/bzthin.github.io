---
title: Bloom Filters
sidebar: technical_sidebar
permalink: /system_design_bloom_filters
---

## Bloom filters
- Bloom filters are space-efficient data structures that use multiple hash functions and a bit array to probabilistically determine whether an element is likely a member of a set, allowing for fast membership tests with a controlled probability of false positives.
- It's particularly useful in scenarios where you need to quickly determine if an element is present in a large dataset, but false positives (indicating that an element is in the set when it's not) are acceptable, while false negatives (indicating that an element is not in the set when it is) are not allowed.

## Usage 
- Caching: To quickly check if an item is in a cache before querying a slower data store.
- Distributed Systems: For routing decisions to quickly eliminate unnecessary requests.
- Big Data Processing: To filter out unnecessary data early in a data processing pipeline.
- Network Protocols: To avoid unnecessary processing or transmission of data packets.