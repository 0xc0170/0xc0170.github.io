---
layout: page
title: "Pervasive Data Access"
description: "Pervasive Applications course review - part 4"
---
{% include JB/setup %}

#### Data dissemination in Pervasive environment

* Transfer data from producers to interested consumer, two categories: **pull** and **push**
* Characteristics & Challenges:
	- **Limited client capability**: battery life, screen size, CPU, memory…
	- **Limited bandwidth & Weak connectivity**: clients don’t stay connected continuously, frequent disconnections impact how transaction management is implemented and how data consistency is guaranteed.
	- **Asymmetry in the communication**: downstream much greater than upstream.
	- **User Mobility**: different cells and servers at different times.

<br/>

#### Pervasive data broadcast

* Performance criteria
	- **Access efficiency**: how fast a client request is answered
	- **Energy conservation**: how much battery power a mobile client consumes
* **Broadcast scheduling**: arranges the order of data items and the frequency of these data items in a broadcast channel, to improve the client access efficiency. Broadcast schedules:
	- Push-based broadcast
	- Pull-based (on-demand) broadcast
	- Hybrid broadcast
* **Push based broadcast**
	- **Flat broadcast**: All data broadcasted in one cycle, same access time. Inefficient. 
	- **Probabilistic-Based Broadcast**: Long access time for a data item may be resulted + inferior performance to other broadcast algorithms.
	- **Broadcast Disk**: Data items of same range of access probability are grouped into **logical disks**. Each disk is assigned a broadband frequency. A broadcast is decomposed into several minor cycles. One minor cycle = one data item from each disk.
	- **Optimal Push Scheduling** (complicated)
* Disadvantages of push based scheduling: not tailored to individual client need + tend to limit the broadcast data items to a pool and react slowly to changing client access patterns.
* **On-demand based (pull-based)**: client sends requests to the server through an uplink channel, requests are queued at the server, the server choose requested items, delivers them over the broadcast channel and clear the request in the queue. Clients manage the broadcast channel.
* **Fixed-Size Item** On-demand broadcast: Average access time performance used as the main optimization objective
	- FCFS: **First-Come-First-Serve** (simple but poor access performance)
	- MRF: **Most Requests First**
	- MRFL: **MRF Low** by breaking the pie in favor of the item with low requested probability
	- LWF: **Longest Wait First**: sum of the waiting time of all outstanding requests for the item 
* **Variable-Size Item** On-Demand broadcast
	- A new performance metric called **stretch** is used (ratio access time/service time). Reasonable metric for variable-size item: takes the size into consideration (service time)
	- PLWF: **Pre-Emptive Longest Wait First**
	- SRTF: **Shortest Remaining Time First**
	- LTSF: **Long Total Stretch First** (current stretch of a request: ratio = time the request has been queued in the system thus far / service time)
	- **MAX algorithm**: assigns a deadline to each request when it arrives at the server. deadline = arrivaltime + servicetime * SMAX (SMAX = max stretch value of the request)
* **Energy-Efficient** On-Demand broadcast takes energy saving into consideration. Broadcast data items in batches using an indexing technique (index items in the current broadcast cycle). Client tunes into a small portion of the broadcast channel instead of monitoring the broadcast channel (energy saving). Data scheduling based on a priority formula.
* **Hybrid broadcast**: requires 2 queues (request queue + broadcast cycle), a timer and algorithm
* **Aix indexing** for energy conservation, indicates the arrival time of data items (instead of scanning a broadcast channel for requested data items)
* Aix indexing steps:
	- **Initial probe**: tuning the broadcast channel to determine when an index is broadcast.
	- **Index lookup**: accessing the index to determine the time when a required data item is on air.
	- **Download**: retrieving required data item at its indicated broadcast time.
* Indexing  techniques
	- **Hashing & flexible indexing**: data items inside frames, hash function hashes a key attribute (ex: delivery time) of the frame holding the desired data, shift function guide a search to the frame containing the desired data.
	- **Index tree**: stores the key attribute values and the arrival time of the data frames in each node, very efficient for clustered broadcast cycle.
	- **Signatures** (for non-cluster based) widely used for information retrieval, signature and query signature generated

<br/>

#### Mobile Data Caching

* Caching frequently used data items in the mobile client’s local storage improve access latency and data availability
* Cache management technique include **cache replacement** (what data items to keep to maximize the space efficiency), **cache coherence** (between source values and cached values) and **cache prefetching** (loads data in advance on the server, if the request is predictable).

<br/>

#### Data Access based on user requirements

* **Time-critical** applications demand data to be made available by a specified “deadline”.
* **Location-based** applications request data based on the current location of the users.
* **Semantic-based** data access: to understand the data access requirement in a semantic way (make required data earlier and more efficient).
* **Reliable** data access: introduce controlled redundancy in the broadcast schedule to deal with unreliable wireless communication (data corrupted or lost because of signal interference for ex)
