---
toc: true
layout: post
description: Decompose complex tasks into series of simple tasks, that can be reused.
categories: [architecture]
title: Pipes Pattern
comments: false
---

# Problem

Often there is overlap of the functionalities between different modules. In monolith approach, we split it up in reusuable modules and import it in corresponding module. 
Let take one example about Netflix. In order to support wide variety of encoding, Netflix encodes all the shows in all supported devices. Encoding is CPU intensive task, With monolith approach, we tend to increase the entire capacity of the server, but if you look closely only Encoding service needs to be CPU bound. To support this we can split up the pipeline into small set of tasks which perform dedicated operation on its own.

# Solution

![](https://user-images.githubusercontent.com/3127498/189771485-09a35f2a-55b3-45f2-afd5-7824fd41a601.png

Here a complex process is splitup into small individual process. 
Let assume that Task A is CPU Intesive, so we can put it in a large machine to make it faster. 
and Task B is small task and does not require that much compute, we can use Serverless kind of framework or use horizondal scalability to increase the speed of execution.

![](https://user-images.githubusercontent.com/3127498/189771465-318d0953-1e2f-489d-ac3f-5328b914414c.png)

To make it **event driven **, we can use queues in between all the tasks, thereby acheiving segregation between each modules. 

# Why    
## Pros     
* Reusability of code (or module)
* Performance (large CPU bound tasks can be alloted Large CPU bound machines - vertical scaling)
* Scalability (if a certain task takes more time to process, we can horizondally scale to meet the needs)

## Cons
* Difficult to Debug

# Reference
[Azure Architecture](https://docs.microsoft.com/en-us/azure/architecture/patterns/pipes-and-filters)     