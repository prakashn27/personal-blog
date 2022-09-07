---
toc: true
layout: post
description: DynamoDB Quick Reference.
categories: [db, aws]
title: DynamoDB Quick Reference
---
# DynamoDB

## Scalar Data Types
|Type|Symbol|Description|JSON Example|
|-|-|-|-|
| String | S  |  typical string | "S": "this is a string"  | 
| Number | N | Any int or float  |  "N": "98", "N":"3.141592" | 
| Binary | B | Base64 encoded binary data  | "B": "nwaafrafs" |
| Boolean | BOOL | true or false  | "BOOL": false |
| Null | NULL | use for missing values  | "NULL": true | 


## Set and Document Data Types

|Type|Symbol|Description|JSON Example|
|-|-|-|-|
| String Set | SS  | Set of string | "SS": ["Prakash", "Natarajan"] | 
| Number Set | NS | Set of numbers  |  "NS": ["1", "2"] | 
| Binary Set | BS | Set of Binary  | "BS": ["wsfawefa==="] |
| List | L | List that can consist of any scalar type  | "L" : [{"S":"prakash"},{"N":"1"}]|
| Map | M | key-value store with string as keys and any scalar as value  | "M":{"key":{"S":"value"}}| 