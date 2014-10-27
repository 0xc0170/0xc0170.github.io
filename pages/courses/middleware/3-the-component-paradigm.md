---
layout: page
title: "The component paradigm"
description: "Middleware course review - part 3"
---
{% include JB/setup %}

#### Component-based middleware

* **Component**: A run-time entity that complient applications and other components can use.
* Two general types: **standalone** and **distributed**
* Example: Javabeans, CORBA component model

<br/>

#### Key concepts:

* **Interface**: Point of service.
* **Receptacle**: describes service requirements.
* **Connection**: binds interface and receptacle of the same type.

<br/>

#### Reflective middleware

* A **reflective system** provides a representation of its own behaviour  which is causally connected to underlying behaviour ( **CCSR**: Causally Coonected Self Representation).
* **Reflective middleware** is a middleware system that provides inspection and adaptation of behaviour through an appropriate CCSR.
* CCSR in Java like language can be class loader, garbage collection and method dispatcher.

<br/>

#### Open Overlays

* Next generation of grid application.
* Many interaction paradigms (publish-subscribe, multicast, RPC, message passing etc.).
* Operate with and accros many heterogeneous network types.
* Wide range of device types from supercomputers to sensor nodes.