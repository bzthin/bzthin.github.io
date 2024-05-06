---
title: Framework
sidebar: technical_sidebar
permalink: /system_design_framework
---

## Framework
- 4-step process for effective system design interview

## Step 1 - Requirements clarifications
- Navigate ambuiguity and understand the problem entirely.
- Get basic requirements
  - Who are our users, and how will they use this.
  - Functional, non functional requirements and extra requirements.
  - Out of scope requirements.
- Estimate system requirements
  - Scale (How many users, how much data is there)
  - Latency (How fast is the APIs supposed to be?)
    - Read/Write Latency. (Amount of time in ms it takes for a message to be sent or received)
    - Read/Write ratio
  - Throughput (What is our QPS? Are there burst queries?)
    - Traffic estimation for read write
  - Storage estimate
  - Memory estimate
- Suggest improvements
  - After gathering data points, if there are certain improvements that can be made to the question or requirement, suggest to the interviewer.

## Step 2 - Propose high-level design and get buy-in
- Develop a high-level design and reach an agreement with the interviewer on the design. You should have
  - Agreed on the overall goals and feature scope
  - Sketched out a high-level architecture for the overall design
  - Obtained feedback from your interviewer on the high-level design
  - Had some initial ideas about areas to focus on in deep dive based on their feedback
- Walk through end to end flow.

## Step 3 - Design deep dive
- Identify and prioritize components in the architecture.
- Discuss API interface definition.
- Define data model.
- Deep dive into individual aspects.
- Justify design, evaluate pros and cons, bottlenecks and tradeoffs

## Step 4 - Wrap up
- Follow-up questions from interviewers
- Identify the system bottlenecks and discuss potential improvements. 
- Recap of your design if you have suggested multiple solutions to refresh interviewer's memory
- Error cases (server failure, network loss, etc.) are interesting to talk about.
- Operation excellence, monitoring metrics and logs. How to fallback and recover on failure.
- How to handle the next scale curve is also an interesting topic. For example, if your current design supports 1 million users, what changes do you need to make to support 10 million users?
- Propose other refinements you need if you had more time.

## Time allocation on each step
- Assuming a 45 mins interview,
- Step 1 Understand the problem and establish design scope: 3 - 10 minutes
- Step 2 Propose high-level design and get buy-in: 10 - 15 minutes
- Step 3 Design deep dive: 10 - 25 minutes
- Step 4 Wrap: 3 - 5 minutes

