---
layout: page
title: "NoSQL Distilled"
description: "author: Pramod J. Sadalage and Martin Fowler"
---
{% include JB/setup %}


### Preface
* NoSQL databases born out of a need to handle **larger data volumes**
* People consider NoSQL database for application **development productivity** and **large-scale data**
* Multiple data model: **key-value**, **document**, **column-family**, **graph**

***

### Part 1: Understand

#### 1: Why NoSQL?

* **Impedance mismatch**: the difference between the relational model and the in-memory data structures
* **Integration database**: multiple applications store their data in a common database / **Application database**: only directly accessed by a single application
* If data and traffic increase, more computing resources are required: **scale up (a bigger server) or out (cluster of small machines)**
* Relational databases provide **persistence**, **concurrency control** and an **integration mechanism** but are **not designed to be run on clusters**
* 2000s higly influencial papers: BigTable from Google and Dynamo from Amazon
* NoSQL is an accidental neologism. There is no prescriptive definition but common characteristics: **not using the relational model**, **running well on clusters**, **open-source**, **built for the 21st century web estates** and **schemaless**
* The most important result of the rise of NoSQL is **Polyglot Persistence**

<br />

#### 2: Aggregate Data Models

* **Aggregate**: a collection of related objects that we wish to treat as a unit (from Domain-Driven Design). Aggregates form the boundaries for *ACID* operations with the database.
* **ACID**: Atomic, Consistent, Isolated and Durable (the real point is atomicity)
* Key-value, document and column-family databases can all be seen as forms of **aggregate-oriented database**. Key-value data model treats the aggregate as an opaque whole (only key lookup for the whole aggregate), document model makes the aggregate transparent to the database allowing queries and partial retrievals, column family model treat aggregates as units of data within a single row.
* Aggregates make it easier for the database to manage data storage over **clusters**
* Further reading: <a href="http://domaindrivendesign.org">http://domaindrivendesign.org</a>

<br />

#### 3: More Details on Data Models

* Aggregate-oriented databases make **inter-aggregate** relationships more difficult to handle than **intra-aggregate** relationships.
* Graph database organize data into **node and edge graph**; they work best for data that has **complex relationship structures**.
* Schemaless databases allow you to freely add fields to records (it's easy to deal with **nonuniform** data), but there is usually an **implicit schema** expected by users of the data.
* Aggregate-oriented databases often compute (and cache on disk) **materialized views** to provide data organized differently from their primary aggregate. This is often done with **map-reduce computations**.

<br />

#### 4: Distribution Models

* Aggregate orientation fits well with scaling out because the aggregate is a **natural unit to use for distribution** (it's designed to combine data that's commonly accessed together. There are two paths to data distribution: **replication** and **sharding**, they are **orthogonal techniques**: you can use either or both of them.
* **Sharding** or **horizontal scalability** distributes different data across multiple servers, so each server acts as the single source for a subset of data and does its own reads and writes.
* **Replication** copies data across multiple servers, so each bit of data can be found in multiple places. Replication comes in two forms: **master-slave** replication and **peer-to-peer** replication.
* **Master-slave** replication makes one node the authoritative copy that **handles writes** while slaves synchronize with the master and may **handle reads**. This technique reduces the chances of update conflicts. To ensure **read resilience**, you need to ensure that read and write paths into your application are different (putting the reads and writes through separate database connections).
* **Peer-to-peer** replication allows writes to any node; the nodes coordinate to synchronize their copies of the data and to avoid write-write conflict. This technique avoids loading all writes onto a single point of failure.

<br />

#### 5: Consistency

* Write-write conflicts occur when two clients try to write the same data at the same time. Read-write conflicts occur when one client reads inconsistent data in the midle of another client's write.
* Pessimistic approaches lock data records to prevent conflicts. Optimistic approaches detect conflicts and fix them.
* Distributed systems see read-write conflicts due to some nodes havind received updates while other nodes have not. Eventual consistency means that at some point the system will become consistent once at all the writes have propagated to all nodes.
* Clients usually want read-your-writes consistency, which means a client can write and then immediately read the new value. This can be difficult if the read and the write happen on different node.
* To get good consistency, you need to involve many nodes in data operations, but this increase latency. So you often have to trade off consistency versus latency.

<br />

#### 6: Version Stamps

* Version stamps help you detect concurrency conflicts. When you read data, then update it, you can check the version stamp to ensure nobody updated the data between your read and your write.
* Version stamps can be implemented using counters, GUIDs, content hashes, timestamps or a combination of these.
* With distributed systems, a vector of version stamps allows you to detect when different nodes have conflicting updates.

<br />

#### 7: Map-Reduce

* Map-reduce is a pattern to allow computations to be parallelized over a cluster.
* The map task reads data from an aggregate and boils it down to relevant key-value pairs. Maps only read a single record at a time and can thus be parallelized and run on the node that stores the record.
* Reduce tasks take many values for a single key output from map tasks and summarize them into a single output. Each reducer operates on the result of a single key, so it can be parallelized by key.
* Reducers that have the same form for input and output can be combined into pipelines. This improves parallelism and reduces the amount of data to be transfered.
* Map-reduce operations can be composed into pipelines where the output of one reduce is the input to another operation's map.
* If the result of a map-reduce computation is widely used, it can be stored as a materialized view.
* Materialized views can be updated through incremental map-reduce operations that only compute changes to the view instead of recomputing everything from scratch.


***



### Part 2: Implement


#### 8: Key-Value Databases


#### 9: Document Databases


#### 10: Column-Family Stores


#### 11: Graph Databases


#### 12: Schema Migrations


#### 13: Polyglot Persistence


#### 14: Beyond NoSQL


#### 15: Choosing Your Database
