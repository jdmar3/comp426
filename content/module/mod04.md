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

### HTTP methods and status codes

You will want to familiarize yourself with REST API terminology and structure.
Pay special attention to HTTP methods and status codes. 

The [REST API Tutorial](https://www.restapitutorial.com/lessons/httpmethods.html)

## SQL databases

SQL is a language for interacting with data held in databases.
SQL uses "statements" to structure queries.
Statements are effectively commands and are (sort of) human readable. 

Some examples of SQL statements relevant to this class:

```sql
CREATE TABLE table1 ( id INTEGER PRIMARY KEY, var1 TEXT, var2 TEXT )
INSERT INTO table1 (var1, var2) VALUES (somedata, someotherdata)
SELECT * FROM table1
SELECT * FROM table1 WHERE id = 5
UPDATE table1 SET var1 = COALESCE(somenewdata,var1), var2 = COALESCE(othernewdata,var2) WHERE id = 5
DELETE * FROM table1 WHERE id = 5
```

Familiarize yourself with how SQL statements work. 
There are many, many resources available online. 
1. [w3c SQL Tutorial](https://www.w3schools.com/sql/)
2. [SQL Tutorial for Beginners](https://www.sqltutorial.org/)

We are using [SQLite3](https://www.sqlite.org/index.html) for this course, which implements SQL in locally stored database files that do not require a server. 
The syntax is [basically the same](https://www.sqlite.org/lang.html), with a few differences.

We will be using a JS implementation of SQLite3 called [better-sqlite](https://www.npmjs.com/package/better-sqlite3).
Full documentation of that implemntation is available [here](https://github.com/JoshuaWise/better-sqlite3/blob/master/docs/api.md#class-statement).

## Express.js

[Express.js](https://expressjs.com/) is a "minimalist" web framework that can be used to create both front- and backend applications in JavaScript.
We will be using it to develop an API and consider its frontend components as well.

*Express* will be the main point of translation for connecting API endpoints to a database in our assignments. 

## Translation table

The following is a table of "verbs" related to different components of our API ecosystem.
This is provided to demonstrate how they relate to one another across languages and frameworks in both conceptual and practical terms. 

| CRUD | SQL | HTTP | Express | What does it do? |
| ---------- | ---------- | ---------- | ---------- | ---------- |
| Create | INSERT | POST | `app.post()` | Makes a new record. |
| Read | SELECT | GET | `app.get()` | Retrieves an existing record. |
| Update (replace) | REPLACE | PUT | `app.put()` | Searches for a record and overwrites it. If it doesn't exist, the record is createed. |
| Update (modify) | UPDATE | PATCH | `app.patch()` | Modifies the information in an existing record. |
| Delete | DELETE | DELETE | `app.delete()` | Removes an existing record. |
