---
title: "mod04 REST, CRUD, and databases"
description: ""
draft: false
---

## Application Programming Interface (API)

An API is the interface layer between two pieces of software that don't necessarily speak the same langauge.
The function of an API is to translate from one platform/piece of software to another.

An API **call** is a process through which requests are made and data is retrieved from an API by a client.
It looks something like this: 

1. A client makes a request for some data.
2. The requested data is retrieved from an external resource. 
3. The data is delivered to the client.

Data can also be manipulated by the API if write actions are permitted.

1. A client requests that new data be added and supplies that data.
2. The request is processed by some sort of middleware that interacts with an external resource.
3. Confirmation of receipt and is returned to the client.

## RESTful services and CRUD operations

REST stands for "REpresentational State Transfer" and the architecture was originally proposed in a [doctoral dissertation](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) at University of California, Irvine by Roy Fielding in 2000. 

The architecture for a RESTful service meets the following constraints:

1. It has a **client-server** architecture: the user interface is separate from data storage. You will see this referred to as "front-end" (client) and "back-end" (server).
2. It is **stateles**: all requests from the client must contain all information necessary for the server to process the request. State information has to remain on the client and cannot be stored on the server.
3. It must have a client-side **cache**: this reduces the number of requests made to the server because the client can reuse information that it already has.
4. It must have a **uniform interface**: this means that the architecture of the client-server interaction is simplified so that the two can be changed independently while still maintaining the same functionality. A uniform interface, as defined, has 4 parts:
	1. Resources: Universal Resource Identifiers (URIs) that identify resources
	2. Representation manipulation: a representation of a resource must contain all of the information necessary to modify the resources itself.
	3. Self-contained messages: messages must include all information necessary to interpret them.
	4. Hypermedia as state: Clients communicate application state through requested URIs, body contents, query-string parameters, and request headers. Servers communicate application state back to clientsas URIs to retrieve objects, body contents, response codes, and response headers.
5. It must be a **layered system**: this restricts knowledge to the immediate layer with which the client is interacting by setting up a hierarchy of intermediaries. This is where middleware and distributed resources come into play.
6. It must be capable of **code-on-demand**: this means that if the API documentation is avaialable, then it should be possible to create or extend a client based on the available endpoints. This constraint is optional, but it does mean that even if documentation is not available, it should be possible to reverse-engineer API calls. 

### 

[REST API Tutorial](https://www.restapitutorial.com/lessons/httpmethods.html)

## SQL databases


