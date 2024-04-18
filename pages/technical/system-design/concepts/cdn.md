---
title: Content delivery network
sidebar: technical_sidebar
permalink: /system_design_cdn
---

## CDN
- A content delivery network (CDN) is a globally distributed network of proxy servers, serving content from locations closer to the user. Generally, static files such as HTML/CSS/JS, photos, and videos are served from CDN, although some CDNs such as Amazon's CloudFront support dynamic content.

## Push CDNs
- Content Pre-Population: In a push CDN, content is uploaded or "pushed" to edge servers in advance, typically by the content provider or publisher.

## Pull CDNs
- On-Demand Content Retrieval: In a pull CDN, content is requested by end-users, and edge servers retrieve or "pull" the content from the origin server when it's requested for the first time.
- AWS Cloudfront uses pull CDN. 