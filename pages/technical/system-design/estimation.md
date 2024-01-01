---
title: Estimation
sidebar: technical_sidebar
permalink: /system_design_estimation
---

## Back of the envelope estimation
- Estimate system capacity or performance requirements using a back-of-the-envelope estimation.
- User Traffic Estimations: Estimating how many users a system might have and what kind of load this translates to per day/month/year.
- Storage Calculations: Calculating the amount of data generated, stored, and queried.
- Bandwidth Needs: Estimating bandwidth requirements for serving content to users. Predicting the number of requests or transactions per second/day.
- Scaling Estimates: Determining how a system might need to scale over time based on growth predictions.

## Common units
### Power of two
- A byte is a sequence of 8 bits. An ASCII character uses one byte of memory (8 bits)
- 
|Power|Approximate value|Full name|Short name|
|10|1 thousand|1 kilobyte|1 kb|
|20|1 million|1 megabyte|1 mb|
|30|1 billion|1 gigabyte|1 gb|
|40|1 trillion|1 terabyte|1 tb|
|50|1 quadrillion|1 petabyte|1 pb|


## Tips
- Use rounding and approximation.
- Write down your assumptions.
- Label your units.
- Commonly asked back-of-the-envelope estimations: QPS, peak QPS, storage, cache, number of servers, etc. You can practice these calculations when preparing for an interview.