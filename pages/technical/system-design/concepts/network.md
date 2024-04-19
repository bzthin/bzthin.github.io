---
title: Network
sidebar: technical_sidebar
permalink: /system_design_network
---

## HTTP and HTTPS
- HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are both protocols used for transmitting data over the internet, primarily used for loading webpages.
- Differs in security aspect.

## TCP and UDP
- TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two of the main protocols used for transmitting data over the internet.
- TCP is reliable but heavyweight.
- UCP is not reliable but lightweight.

## RPC
- RPC is a protocol that allows a program to execute code or call functions on another system as if they were local procedures or functions. It enables distributed applications to communicate by invoking procedures or methods on remote systems.

## URL, URI, URN
- A URI is a string of characters used to identify a resource, typically on the internet. It provides a standard way to locate and access resources, regardless of the protocol used.
- A URL is a specific type of URI that provides the means to locate a resource by specifying its location and how to access it. 
- A URN is a type of URI that is used to uniquely identify a resource without specifying its location or how to access it. URNs are intended to be persistent and globally unique identifiers for resources.

## OSI model
- The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven distinct layers. 
- Application Layer (Layer 7)
- Presentation Layer (Layer 6)
- Session Layer (Layer 5)
- Transport Layer (Layer 4)
- Network Layer (Layer 3)
- Data Link Layer (Layer 2)
- Physical Layer (Layer 1)


## Long polling vs web sockets vs server sent events 
- Long-polling is a request-response mechanism with delayed responses, 
- WebSockets provide full-duplex communication over a persistent connection, 
- SSE allows servers to push updates to clients over a unidirectional channel.

## Heartbeat
- Aheartbeat is a periodic signal or message sent by a component or node to indicate its operational status and availability. 
- Heartbeats are used in distributed systems, networks, and monitoring tools to detect failures, maintain connectivity, and ensure system reliability. By regularly sending and receiving heartbeats, nodes can monitor the health of each other and quickly identify any failures or network issues, enabling timely response and recovery actions.

## Checksum
- A checksum is a value calculated from a data set using a specific algorithm, typically for the purpose of detecting errors during data transmission or storage.
-  It's a form of redundancy check that helps ensure data integrity by verifying that the transmitted or stored data hasn't been corrupted or tampered with. 
- Checksums are commonly used in networking protocols, file transfer protocols, storage systems, and cryptographic operations.