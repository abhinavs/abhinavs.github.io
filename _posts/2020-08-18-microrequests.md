---
layout: post
title: Microrequests
excerpt: "Microrequests is a wrapper over Python's requests module - makes it more efficient to consume microservices in Python"
tags: [microrequests, Microservices, Open Source, Module, Library, Python, pip]
comments: true
canonical_url: 'https://www.abhinav.co/microrequests'
---
Microservices have slowly become the chosen way of building systems in large and small companies - they work because they allow decentralisation and the separation of concern which helps when the number of teams in an organisation starts growing.

<br />

Microservices, however, also present some challenges. Amongst many of them, one of the key challenges is to keep the communication between different microservices simple and easy yet performant. 

<br />

There are a lot of ways in which microservices can talk to each other, one of the most popular ways is to use HTTP APIs (including REST APIs) - HTTP is a sort of stateless protocol, and by default is a bit inefficient to use from the latency point of view if you have to call many microservices to serve one client-facing request. 

<br />

Microrequests makes consuming microservices in Python more efficient. Python’s requests module is fantastic and highly configurable, microrequests builds a wrapper over requests module and enables connection pooling as part of initialisation. This ensures that you use the same connection instead of creating one with every new request, while still working with requests’ clean APIs and mechanisms.

### Installation
The easiest way to install microrequests is using pip
```sh
$ pip install microrequests
```

## Usage
To use, simply do::
```python
import microrequests

mr = microrequests.init()
res = mr.get("http://httpbin.org/get") # mr is requests' session object and you can use it in similar manner
print(res.text) 
```

You can also customize max_retries, pool_connections, and pool_maxsize - they are by default set to 1, 100 and 50 respectively; pool_connections is the number of urllib3 connection pools to cache and poolmaxsize is the maximum number of connections to save in the pool

```python
import microrequests

mr = microrequests.init(max_retries=2, pool_connections=10, pool_size=5)
res = mr.get("http://httpbin.org/get")
print(res.text)
```

### Future Work
In the future, I intend to add more nifty ways to make consuming microservices easy and efficient. I also want to experiment websockets as a communication protocol instead of RPC or HTTP - a lot of backend frameworks in various programming languages now support websockets and interface is mostly clean, however consuming microservices using websockets is still not mainstream and interfaces are still ugly. I intend to work on this.

### Source Code
Source code is present on [Github](https://github.com/abhinavs/microrequests), please check [project homepage](http://www.abhinav.co/microrequests.html) for more and updated details. 


