---
layout: page
title: "Peer to Peer"
description: "Middleware course review - part 2"
---
{% include JB/setup %}

#### Definition

* **High degree of decentralization**: Peers implement both client and server functionality, most of system state dynamically allocated among peers.
* **Self-organization**: Once a node is distributed, a little or no manual configuration required.
* **Low barrier to deployment**: Low upfront investment.
* **Organic growth**: Resources contributed by participating nodes.
* **Resilience to faults and attacks**: Few, if any, node's critical to system operation.
* **Abundance and diversity of resources**: Few organization can afford: divers hardware, software, network access, power supply ..

<br/>

#### Application

* **SETI@HOME**: volounteer computing, users donate spare CPU cycles.
* **BBC**: Iplayer, streaming media, exploit bandwith of clients to avoid bandwith cost of server based solutions.
* **BitTorrent**: Sharing and distributing files.

<br/>

#### How it works?

* **Overlay network**: Computer network built on top of another network. Nodes connected by virtual links, each is a path, possibly through many nodes in the underlying network.
* **Key challenge**: To build an overlay network with routing capability that works well in presence of high membership turnover.
* **Characteristic**: Degree of centralization, overlay maintenance, distributed state, distributed coordination.

<br/>

#### Degree of centralization

* Presence or absence of centralized components in system design
* Partially centralized system have a dedicated node controller maintaining set of participating nodes
* Decentralized system has no dedicated nodes critical to operation of the system but some has supernodes (highly available) which store state, keep indices of available content, act like a rendez-vous point.

* * *

#### Unstructured overlays

* No constraints on links between different nodes and hence no particular structure to the overlay.
* New node performs random walkthrough overlay to find place to join
* Minimum chosen to maintain connectivity in case of failure.
* Maximum set to bound overhead of maintaining links.

<br/>

#### Structured overlays

* Each node has a unique ID chosen so they are uniformly distributed in that spaces. Overlay graph has a specific structure. The ID determines the position in the structure and contains its sets of links.
* Use of key to assign responsabilities: one key is mapped to one node. **KBR**, *key based routing*, with a starting node and a key. KBR gives the path to the node responsible for the key.

<br/>

#### Content in unstructured overlays

* Object stored at node that inserted the object, as well as at node that subsequently download the object.
* Controller node maintains list of what is where.
* Queries are directed to controller which responds with lists of nodes where object may be found.

<br/>

#### Content in structured overlays

* Object stored at node that inserted the object, as well as at node that subsequently download the object.
* Querying node floods request message through the overlay specifying object by key, keywords, metadata..
* Node that has matching object (or pointer) responds.
* Scope of floods often limited, to trade recall for overhead.

* * *

#### Chord

* Efficient by locating a node that stores a particular object.
* Distributed lookup protocol with one operation: maps keys to node + a finger table
* With n nodes, each nodes maintains only informations about log(n) nodes and resolves lookup via log(n) messages to other nodes, join or leave requires log2(n) messages. 

<br/>

#### Pastry

* Each node is assigned a node ID (128 bits) chosen randomly, assumed to be uniformly distributed.
* Identifies node's position in a circular spaces 0 to 2^128 - 1
* Message and node ID share prefix (messages are routed to node ID closer message key).
* Each nodes maintain a routing table, neighbourhood set and leaf set.

<br/>

#### Scribe

* Based on Pastry, publish-subscribe.
* Subscribers register interest in a topic or pattern of events.
* Asynchronously receive events matching their interests.

* * *

#### DHT (Distributed Hash Table) threat in security

* Incorrect lookup routing.
* Incorrect routing update.
* Partitionning