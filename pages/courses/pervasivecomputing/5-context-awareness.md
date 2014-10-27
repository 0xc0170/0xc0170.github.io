---
layout: page
title: "Context Awareness"
description: "Pervasive Applications course review - part 5"
---
{% include JB/setup %}

#### Wireless Communication: Wireless cellular network (GSM) - architecture
* **Coverage area** or **cells**: form regions of a geographical area
* **Base station**: controls communication in each cells
* **Mobile Switching Centre (MSC)**:  controls base stations
* **Public Switching Telephone Network (PSTN)**: connects MSC together

<br/>

#### Wireless Communication: Wireless cellular network (GSM) – important notions
* **Uplinks**: channels that handle transmissions from mobile users to base stations
* **Downlink**: channels that handle transmission from base stations to mobile users
* **Handoff**: process wherein a user moves from one base station (host) to another (destination). User’s session/connection info are transmitted to the destination.
* **HLR** (Home Location Register) and **VHR** (Visiting Location Register) are databases storing user’s information.

<br/>

#### Context – Definition
* “A context represents the **state** or **situation** in the environment of a system that affects that **system’s behaviour** (application specific)” (UbiCom Book)
* “Any information that can be used to describe the situation of **people, resources and services** in a service-oriented environment. It may include all other info that can be considered relevant to the interaction between a user and a service.” (Dey & Schilit)

<br/>

#### Context-aware
* Pervasive and mobile applications operate in **highly dynamic environments**
* **Aim**: automatically perform tasks without demanding much of the user intervention
* **Objective**: provide such facilities – automatically adapt to the changes in location, time and user or device situation
* Different **applications types** like network, device, time, location, mobility context-aware

<br/>

#### 3 main sources of context information
* **Physical devices**: context info include location, time, temperature
* **Users** (Human): context include personalisation, user input, other HCI info
* **Software applications**: info related to device display, content adaptation, etc.

<br/>

#### Context adaptation
* **Passive context adaptation system**: context is presented to the user and let it decide on how to change application behaviour
* **Active context adaptation system**: system automatically changes application behaviour according to the context information
* **Personalisation of context**: “system let users specify the settings for how the application should behave in a given situation” (Barkhuus and Dey) 

<br/>

#### Context-awareness: issues and challenges
* **Uncertainty of context info**: user contexts out of date, incomplete, incorrect or imprecise
* Factors contributing to the uncertainty of context info: technical or environment problems or users related issues
* **Context representation**: it can have alternative representations
* **Context processing**: it can generate huge volumes of data, need low resource infrastructure
* **Privacy issues**: it can reduces the privacy and distract users

<br/>

#### Location-awareness context
* Steps: 1 trigger location-aware services, 2 determine current location, 3 determine the location context, 4 service adaptation
* E.g. location determination in call routing for mobile users (see GSM architecture)

<br/>

#### Content adaptation, 2 types:
* **Device or terminal context**: can be done on the server by determining device type and choosing the appropriate content (server side adaptation) or on the client  by formatting the content at retrieval time (client side adaptation) or as the content passes through network nodes (in-network adaptation)
* **Network context**: a service that is aware of the characteristics of the physical network

<br/>

#### Context Management System
* **Context toolkit**
	- **Sensor layer**: works as an information (or data) collector and provider, contains a network of sensor
	- **Semantic layer**: defines the context model of a context-aware app and “supplies the control layer with an accurate image of the current interaction situation”
* **Entity layer**: defines relationship between entities and their context
* **Entity relationship layer**: models dependencies between different entities in order to define relationships
* **Process layer**: analysis of the context data, observes the evolution of the context
	- **Control layer**: gets info from the semantic layer and takes appropriate action: it generates sequences of commands for the control of the behaviour of the domain
	- **Indicator/actuator layer**: handles the connection back to the domain, maps the decisions taken by the control layer to real world action
* **The design tool**: panels for sensors, (context) attributes (add, remove etc.), modelling, control, queries, etc.
* **The mobile collector**: tool for the production of contextualized content by content provider
* **Content management**: provides repositories (metadata of content + actual content) to store all the info about context, users and devices

<br/>

#### CRUMPET: 
* **Creation of User-friendly Mobile services Personalised for Tourism**, EU FP5, maps, routes and sight recommendations can be adapted according to the current location of the tourist, personal context of a service uses, network context, and terminal context.


