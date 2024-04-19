---
title: Messaging
sidebar: technical_sidebar
permalink: /system_design_messaging
---

## Messaging system 
- A messaging system is responsible for transferring data among service applications, processes, or server.
- Such a system helps decouple different parts of a distributed system by providing an asynchronous way of transferring messaging between the sender and the receiver.
- There are two common ways to handle messages: Queuing and Publish-Subscribe.

## Queuing
- In the queuing model, messages are stored sequentially in a queue. Producers push messages to the rear of the queue, and consumers extract the messages from the front of the queue.
- Example, AWS SQS

## Publish-Subscribe
- In the pub-sub (short for publish-subscribe) model, messages are divided into topics. 
- A publisher (or a producer) sends a message to a topic that gets stored in the messaging system under that topic. Subscribers (or the consumer) subscribe to a topic to receive every message published to that topic. 
- Unlike the Queuing model, the pub-sub model allows multiple consumers to get the same message; 
- Example, AWS SNS