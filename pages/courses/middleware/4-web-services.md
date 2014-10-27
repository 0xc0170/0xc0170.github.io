---
layout: page
title: "Web services"
description: "Middleware course review - part 4"
---
{% include JB/setup %}

#### Definition
A platform and implementation dependant software component that can be:
* **Described** using a service description language
* **Published** to a registry of services
* **Discovered** through standard mecanism
* **Invoked** through a declared API, usually over a network, and composed with other service.

<br/>

#### SOAP Structure

* **SOAP envelope**: express what is in a message, who should deal with it and whether it is optional or mandatory.
* **SOAP encoding rule**: defines serialization mechanism for exchanging instances of application definded data types.
* **SOAP RPC representation**: defines convention for representing remote procedure calls and responses.
* **SOAP binding**: defines convention for exchanging SOAP envelopes between peers using underlying transport protocol.

<br/>

#### WSDL (Web Service Definition Language)

* **Interface**: Element describes what fonctionality the web service provides. 
* **Binding**: Element describes how to access the web service.
* **Service**: Element describes where to access the web service.
* **Operation**: associates message exchange pattern with one or more messages, input, output => on interface, binding and service.
* **Endpoint**: **ABC** Address, Binding, Contract

<br/>

#### REST (Representational State Transfer)

**Methods**: Options, Get, Head, Post, Put, Delete, Trace, Connect  
**RESTful** web services works out the data model and split it into resources:

* name the resource with URI
* expose a subset of the uniform interface
* design the representation accepted from the client
* design the representation served to the client
* integrate into existing resources, using hypermdedia links and forms