---
layout: page
title: "Cloud and Grid computing"
description: "Middleware course review - part 1"
---
{% include JB/setup %}

#### Cloud, Grid and Cluster

* They are all **parallel** or **distributed** system.
* **Cluster**: Collection of interconnected stand-alone computers with single administration.
* **Grid**: Allows sharing and aggregation of geographically distributed autonomous resources, dynamically at runtime. May involve multiple administration domain.
* **Cloud**: Collection of interconnected virtualised computers that are dynamically provisioned as one or more unified computing resource, based on a negociated SLA.

* * *

#### Cloud

<br/>

##### Components

* **Client**: The end used, usually a thin client.
* **Service**: Cloud computing functionality.
* **Application**: Client purchased used of cloud service.
* **Platform**: Cloud middleware launching client application.
* **Storage**: File server and other resources used for client data.
* **Infrastructure**: Cloud control and operation for service provision.

<br/>

##### Key technologies

* **Web 2.0**: Use the web for service participation.
* **Broadband networking**
* **SOA**: Client-server development model based on interoperable software services.
* **Virtualisation**: Hosting of multiple logical operating systems, each sharing the available resources.

<br/>

##### Hosting

* **Remote**: Service is hosted on remote infrastructure.
* **Ubiquitous**: Service is available from many providers.
* **Commodified**: Utility computing model; client pays for what and how much service used.

<br/>

##### Customer choice

* **Advantages**: Buy service, not hardware and software; pay for and used only what is needed; scalable, available, transparent.
* **Disadvantages**: Cost of service; restricted to services that are available; dependency on third party for maintenance; privacy issue.

<br/>

##### Deployment model

* **Internal (private) cloud**: Operated only within an organization.
* **Community cloud**: Jointly owned by several organization as a community.
* **Public cloud**: Owned by an organization selling services to outsiders.
* **Hybrid**: Composition of two or more private, public or community cloud working together to provide a single service.
* **Cloud storage**: Large cloud providers now hire data storage.

<br/>

##### Types

* **IaaS** (*Infrastructure as a Service*): Access to computer hardware over the internet; lease of servers, sofware, databases, hardware etc. as an outsourced service. Example: Dropbox, Amazon Web Services.
* **PaaS** (*Platform as a Service*): Use web based tools to develop application to run remotly. Example: Windows Azure, Google App Engine.
* **SaaS** (*Software as a Service*): Access to application running remotely, can provide communication security, monitoring etc. Example: Salesforce, Hotmail.

* * *

#### Grid

<br/>

##### Key concepts

* **Virtual organization**: People and resources collaborating accros admin and organization boundaries.
* **Grid middleware**: Running on each resources to interface to the grid; providing specific service.
* **Single virtual computer**: User just perceives "shared resources" without concern for location or owning organization; Issues: heterogeneity, scalability, reliability, computing model, access control.

<br/>

##### Features

* **Resources sharing**: Computers, storage, sensors, network; heterogeneity of device, mechanism policy; conditional sharing.
* **Coordinated problem solving**: Integration of distributed resources, compound quality of service requierements.
* **Dynamic, multi-institutional virtual organization**: Dynamic overlays on classic organizational structure.

<br/>

##### Scales

* **Department Grid** (cluster)
* **Enterprise Grid** (example: CERN)
* **Global Grid** (example: NGS)

<br/>

##### Types

* **Computational**: Provides computational services (most common).
* **Data**: Provides computational access to large (possibly distributed) datasets from multiple storage systems.
* **Collaboration**: Designed to facilitate collaborative computation.
* **Network**: Provides fault tolerant high performance communication to facilitate computation.
* **Utility**: Computational resources accessed on demand.
* **Cluster**: Smaller grid, operating localy.

<br/>

##### Components

* **Resources**: Networking, computers, data storage, instruments..
* **Grid middleware**: The operating system of the grid.
* **Operations infrastructure**: Runs enabling services.
* **Virtual organization management**: Procedures for gaining access to resources.

<br/>

##### Middleware

* Distributed services and operating system to allow authorised Grid users access to required access. 
* **Gridware** includes authentication, negociation of resources access, distributed load balancing, accounting with multiple domains etc.

<br/>

##### Architecture

* **Applications**: Climatology, cosmology, high energy physics. 
* **Application toolkits**: Data grid, computational grid, collaborative grid.
* **Grid services**: Protocols, authentication, resource management.
* **Grid fabric**: Disk, network, processor.

* * *

#### Cluster

<br/>

##### Types

* **Non-dedicated** (network of workstation): Usage of spare workstation, frequently serial communication between workstations, individual owners of workstations.
* **Dedicated** (supercomputer): High performance, parallel communication between workstation nodes, parallel computing.
