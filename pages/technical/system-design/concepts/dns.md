---
title: Domain Name System
sidebar: technical_sidebar
permalink: /system_design_dns
---

## DNS
- DNS, or Domain Name System, is a system used to translate human-readable domain names (e.g., www.designgurus.com) into IP addresses (e.g., 198.47.25.1) that computers can understand. 

## Domain names, TLDs (Top-Level Domains), and subdomains
- A domain name is a human-readable address used to access a website or other resources on the internet. It consists of a series of character strings separated by dots, such as www.example.com. Domain names are easier to remember and use than IP addresses.
- A top-level domain (TLD) is the rightmost part of a domain name, such as ".com" in www.example.com.
- A subdomain is a subdivision of a domain name, allowing the creation of separate sections or areas within a website. Subdomains appear to the left of the main domain name, such as blog.example.com, where "blog" is the subdomain of example.com.

## Root, TLD, and Authoritative Name Servers
- Root servers are the highest level of DNS servers and are responsible for directing queries to the appropriate TLD servers. 
- TLD servers store information about domain names within their specific TLD.
- Authoritative name servers hold the actual DNS records for a domain, including its IP address and other information. 

## DNS resolution process
- Client Request
- Local DNS Cache Lookup
- Recursive DNS Server Lookup
- Root DNS Servers
- TLD DNS Servers
- Authoritative DNS Server Lookup
- Response to Client
