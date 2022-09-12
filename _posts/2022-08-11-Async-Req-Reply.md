---
toc: true
layout: post
description: Backend needs to be async, where as front-end needs to be sync
categories: [indiehacker]
title: Asynchronours Request-Reply Pattern
comments: false
---

# Problem:     
Typically frontend expects response to be immediate (less than few seconds), but sometimes backend might take more time than expected. In these cases, requests would be timed out (AWS API Gateway has 30 seconds timeout).

# Solution:    
One way to handle this to make backend asynchrous and do HTTP long polling from the front end. 

1) Make the server async to accept any number of jobs.
2) Offload the time consuming part to a worker
3) Periodically check from client if worker has finished the request

![](https://user-images.githubusercontent.com/3127498/189568631-93f2e2fc-c61a-4755-b6c0-1058088423bb.png)


# References:
[Http Polling Issues](https://datatracker.ietf.org/doc/html/rfc6202#section-2.1)
[Azure Architecure Patterns](https://docs.microsoft.com/en-us/azure/architecture/patterns/async-request-reply)
