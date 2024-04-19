---
title: Framework
sidebar: technical_sidebar
permalink: /system_design_framework
---

## Framework
- 4-step process for effective system design interview

## Step 1 - Requirements clarifications
- Clarify functional, non functional, and other requirements.
- What scale is expected from the system
- How much storage will we need? 
- What network bandwidth usage are we expecting? This will be crucial in deciding how we will
manage traffic and balance load between servers.

## Step 2 - Propose high-level design and get buy-in
- Aim to develop a high-level design and reach an agreement with the interviewer on the design
- At this step, you and your interviewer should have achieved the following objectives:
  - Agreed on the overall goals and feature scope
  - Sketched out a high-level blueprint for the overall design
  - Obtained feedback from your interviewer on the high-level design
  - Had some initial ideas about areas to focus on in deep dive based on her feedback

## Step 3 - Design deep dive
- You shall work with the interviewer to identify and prioritize components in the architecture.
- Discuss API interface definition.
- Define data model.
- Deep dive into individual aspects.

## Step 4 - Wrap up
- In this final step, the interviewer might ask you a few follow-up questions or give you the
freedom to discuss other additional points.
- The interviewer might want you to identify the system bottlenecks and discuss potential
improvements. Never say your design is perfect and nothing can be improved. There is
always something to improve upon. This is a great opportunity to show your critical
thinking and leave a good final impression.
- It could be useful to give the interviewer a recap of your design. This is particularly
important if you suggested a few solutions. Refreshing your interviewer’s memory can be
helpful after a long session.
- Error cases (server failure, network loss, etc.) are interesting to talk about.
- Operation issues are worth mentioning. How do you monitor metrics and error logs?
How to roll out the system?
- How to handle the next scale curve is also an interesting topic. For example, if your
current design supports 1 million users, what changes do you need to make to support 10
million users?
- Propose other refinements you need if you had more time.

## Time allocation on each step
- System design interview questions are usually very broad, and 45 minutes or an hour is not
enough to cover the entire design. Time management is essential. How much time should you
spend on each step? The following is a very rough guide on distributing your time in a 45-
minute interview session. Please remember this is a rough estimate, and the actual time
distribution depends on the scope of the problem and the requirements from the interviewer.
- Step 1 Understand the problem and establish design scope: 3 - 10 minutes
- Step 2 Propose high-level design and get buy-in: 10 - 15 minutes
- Step 3 Design deep dive: 10 - 25 minutes
- Step 4 Wrap: 3 - 5 minutes

---

## Steps
- Requirements expectations and clarifications  
  - Use cases
  - Scenarios that will not be covered
  - Who are our users
  - How many users are we expecting
  - How will they use it.
  - Write those down in functional, non functional requirements and extra requirements

- Back of the envelope estimation. 
  - Throughput (amount of data that is successfully transmitted through a system in a certain amount of time)
  - Bandwidth (amount of data that can be transmitted and received during a specific period of time)
  - Read/Write Latency. (Amount of time in ms it takes for a message to be sent or received)
  - Read/Write ratio
  - Traffic estimation for read write
  - Storage estimate
  - Memory estimate

- High level design
  - System Interface definition. State APIs required from the system to ensure understanding on requirements.
  - Draw the major components without going too deep.
  - Defining database schema.
  - Walk through end to end flow for read/ & write.
  
- Deep dive
  - Scaling algorithm
  - Scaling individual components (Availability, consistency, scale) 
  - Consider following components how it can help
    - DNS
    - CDN
    - Load balancer
    - Reverse proxy
    - Application layer scaling (Microservices)
    - Database
    - Caches
    - Asynchroism (Messages/tasks queues)
    - Communication (TCP, UDP, REST, RPC)
  - Justify design, evaluate pros and cons, bottlenecks and tradeoffs