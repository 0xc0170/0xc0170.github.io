---
layout: page
title: "Message passing and PVM"
description: "Middleware course review - part 5"
---
{% include JB/setup %}


#### Message Passing Models and requirements

* Computation(MIPS, Flops), Communication(latency + bandwidth), Synchronization(timing constraints, handshaking)
* Pipe, socket, ACID
* Deadlock: Mutual exclusion, hold and wait, non preemption, circular wait – Livelock
* Synchronous/Asynchronous – Blocking/Non-Blocking – Sender/Receiver naming Static/Dynamic – Connection Oriented/Connectionless – Scatter/Gather – Transient/Persistent
* Transmission time = latency + data_length / data_rate
* Advantages/disadvantages

<br/>

#### The Client Server model
* Comparison to P2P Model
* Thin and Thick (or Fat) Clients
* Binding and the Name Server
* Iterative / Concurrent server
* Stateful / Stateless server

<br/>

#### Distributed Memory Computing
* MPI and PVM approaches
* Shared memory – Threads – Message Passing
* Control and Data Parallel
* Parallel computing / Distributed computing / Concurrent
* Amdahl’s law: Speedup(P)= TimeWith1Processor / TimeWithPProcessor = P / 1 + (P-1)f
Efficiency: Ep(P) = Sp(P) / P = 1/1 + (P-1)f
* Multicast Model: T = L+N / D and Tp = PL + N/D + NC/P and Sp = T1 / Tp = NC / (PL+N / D+NC / P)

<br/>

#### PVM
* Pvmd (daemon process, create and manage the VM) & spawning (user lib for starting new processes, task coordination and message passing)

<br/>

<div class="ten centered columns">
    <img class="span3 offset1" src="{{ ASSET_PATH }}img/page/courses/pvm1.png" width="200px"/>
    <img class="span5 offset2" src="{{ ASSET_PATH }}img/page/courses/pvm2.png"/>
</div>
