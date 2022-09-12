---
toc: true
layout: post
description: Decompose complex tasks into series of simple tasks, that can be reused.
categories: [architecture]
title: Pipes Pattern
comments: false
---

# Pros:
* Reusability of code (or module)
* Performance (large CPU bound tasks can be alloted Large CPU bound machines - vertical scaling)
* Scalability (if a certain task takes more time to process, we can horizondally scale to meet the needs)

# Cons:
* Difficult to Debug

# Reference:
[Azure Architecture](https://docs.microsoft.com/en-us/azure/architecture/patterns/pipes-and-filters)