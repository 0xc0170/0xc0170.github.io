---
layout: page
title: "Pervasive Computing Environments"
description: "Pervasive Applications course review - part 1"
---
{% include JB/setup %}

#### Pervasice computing
An environment in which people interact with embedded (and mostly invisible) computers and in which networked devices are aware of their surroundings and peers and are able to provide services from peers effectively. Multiple distributed computers with adequate processing, memory and communications capability. High availability, reliability, adapt to changes in environment.

</br>

***

#### Reminders:
* **HCI**: Human-Computer Interaction
* **Harvard Architecture**:  is a computer architecture with physically separate storage and signal pathways for instructions and data. Difference with the **Von Neumann** architecture.
* **RISC**: (Reduced Instruction Set Computing) “CPU design strategy based on the insight that simplified instructions can provide higher performance if this simplicity enables much faster execution of each instruction”. CISC (Complex Instruction Set Computing) is the opposition.

***

</br>

#### Terminology:
* **Ambient intelligence**: environment that senses and responds
* **The internet of things**: where real world objects have virtual internet representations
* **Haptic computing**: computer interaction using mechanical tactile feel or movement

</br>

#### Evolution: 
* **Distributed computing** (message passing, RPC, fault tolerance...)
* **Mobile computing** (adaptive applications, location awareness, mobile networking...)
* **Pervasive computing** (smart spaces, invisibility, localized scalability...)

</br>

#### Difference between Pervasive and Ubiquitous:
* **Pervasive**: Something that is present or felt throughout a place or thing, computers and operation invisible and transparent to users
*	**Ubiquitous**: Computers or computational devices are everywhere but they are not always obvious as they form part of the users environment

</br>

#### Context awareness: 
* State of the user, of the physical environment, of the computing system, history of user-computer interaction... (Who, what, when, where and possibly why) unpredictable behavior. Key concept of pervasive computing
* **Issues**: data representation, information inference from various sensors, what frequency of update, security, what is minimum level of awareness required, balance between proactive action and user privacy. 

</br>

#### Volatile systems: 
* Failures of devices and communications links
* Changes in communications quality (bandwidth, QoS...)
* Dynamic logical communication links between software components

</br>

#### Smart Objects: 
Real world objects are enriched with information processing capabilities. Embedded processors, communication capability, sensors and actuators, remember pertinent events, responsive/proactive

</br>

#### Sensors and actuators:
* **Sensor**: device generating electronic inputs relating to the environment state
* **Actuator**: electronic and mechanical outputs to control the environment state

</br>

#### Sensor capability:
* **Sensitivity**: ability to detect small changes
* **Accuracy**: absolute correct values
* **Linearity**: output response is directly proportional to input value
* **Hysteresis/latency**: immediacy of response

</br>

#### Agents: 
Software abstraction that can control the system environment using autonomous and reactive behavior. Monitor environment through sensors and responds to control the environment using actuators. Can be made intelligent with proactive behavior and/or can learn from previous behavior.

</br>

#### Intelligent Environments: 
Environment uses technology transparently and intelligently to improve our experience and quality of life, minimize operating costs (ex: carbon footprint), awareness of privacy and security issues. **Ambient Intelligence**.

</br>

#### Sensor Networks: 
Geographically distributed network of sensor nodes configured to monitor environment state (temperature, vibration, pressure, GPS position…) each sensor node has communications + microcontroller processor.

</br>

#### Motes:
* Small low cost and low power computer, autonomous wireless sensors, when clustered together could create flexible networks that interact with the environment
* Example: Zig Bee, Sun Spot, Arduino, Raspberry Pi

</br>

#### Pervasive computing issues: 
take-up (needs to be adopted everywhere to become accepted), interoperability (needs standardization of interface and operation), ambiguity of operation, administration, social issues, security, battery and low power techno, fault tolerance and reliability
