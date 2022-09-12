---
toc: true
layout: post
description: Backend needs to be async, where as front-end needs to be sync
categories: [indiehacker]
title: Asynchronours Request-Reply Pattern
comments: true
---

# Problem:     
Typically frontend expects response to be immediate (less than few seconds), but sometimes backend might take more time than expected. In these cases, requests would be timed out (AWS API Gateway has 30 seconds timeout).

# Solution:    
One way to handle this to make backend asynchrous and do long polling from the front end. 

