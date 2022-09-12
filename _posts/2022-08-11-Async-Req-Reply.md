---
toc: true
layout: post
description: Backend needs to be async, where as front-end needs to be sync
categories: [architecture]
title: Asynchronours Request-Reply Pattern
comments: false
---

# Problem     
Typically frontend expects response to be immediate (less than few seconds), but sometimes backend might take more time than expected. In these cases, requests would be timed out (AWS API Gateway has 30 seconds timeout).

# Solution    
One way to handle this to make backend asynchrous and do HTTP long polling from the front end. 

1) Make the server async to accept any number of jobs.    
2) Offload the time consuming part to a worker.     
3) Periodically check from client if worker has finished the request.      

![](https://user-images.githubusercontent.com/3127498/189568631-93f2e2fc-c61a-4755-b6c0-1058088423bb.png)

# More Options
* Instead of long polling we can also use **[websocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)** to create a bidirectional connection and send the result from the server, when it is available. We do have a overhead of maintaing the websocket connection from server.

* We can also use **[Server-sent Events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)**. This is **not a bidirectional** connection. We can send events only from the server. Typical use of this technology is in **stock tickers**


# References
* [Http Polling Issues](https://datatracker.ietf.org/doc/html/rfc6202#section-2.1)          
* [Azure Architecure Patterns](https://docs.microsoft.com/en-us/azure/architecture/patterns/async-request-reply)
