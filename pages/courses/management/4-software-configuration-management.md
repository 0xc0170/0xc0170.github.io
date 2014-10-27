---
layout: page
title: "Software Configuration Management"
description: "Software Project Management course review - part 4"
---
{% include JB/setup %}

#### Introduction
* **Overview**: managing all system software and doc components, in particular version and configuration control. Integral part of SQA and concerned by quality
* **Symptoms of poor SCM**: previous releases cannot be rebuilt or cannot be found, Files get lost, are “mysteriously” or concurrently changed, bugs reappear…
* **Reasons for SCM**: disaster recovery, ensure, keep track and report changes, control the evolution of the product, allow team work…

<br/>

#### Configuration Management Plan: 
defines the types of doc to be managed, who takes responsibilities for CM activities, tools and db to be used for CM, policies for changes 

<br/>

#### Configuration items
* Unit that needs to be separately recorded, managed and versioned within the project. Forms the metadata for a project (so item naming rules and secure storage)
* Example: software items (source code, librairies, db schemas, build procedure, test data) and document items (project contract, plan, spec, test plan, bug report…)

<br/>

#### Version control tools
* Need to identify, keep track, store, archive, regenerate each version (version: customer view of a system evolution) or versions of files
* **Version** can reflect bug fixes, features, improvments… major and minor numbers + letters -> identifies release, beta …
* **Variants** of a version customise a system for a specific implementation, identical functionality but different non-functional requirements
* **Release** is distributed to users outside the dev team, incorporated bug fixes and enhancement requests from customers
* **Tools**:
	- RCS: very old but still in use
	- **CVS** (Concurrent Version Control): based on RCS, allows concurrent working without locking
	- Perforce: Repository server, keep track of each developer’s activities
	- ClearCase: Multiple servers, process modelling, policy check mechanisms
	- **Subversion**: Open source, based on CVS, integrated to Apache webserver. Version controlled moving, renaming, copying, metadata of files and directories. Checkout, add, delete, commit, diff

<br/>

#### Build management
* Process of converting source code files into executable code, for complex programs source and object files must be compile in the correct order
* **Tools**:
	- **Apache ANT** (Another Neat Tool), java environment, uses XML to describe the build process and file dependancies, good portability
	- SCons: open source written in Python, multiplatform, support C, C++, fortran, .NET, config files are python scripts, built-in support to use RCS or CVS
	- **Make**: most widely used build tool, particularly for C/C++ on Unix, is a specification language to define build instruction, file dependency in a makefile

<br/>

#### Release procedures
* **Purpose**: clarify purpose of release, verify integrity and quality of delivered software product, assign unique version number
* **Software release**: executable code, config files, data files, instal procedures, documentation
* **Software testing**: static tests (code complexity metrics, source code meets agreed standards) and dynamic tests (verification and validation testing)

<br/>

#### Change control
* Prevents ad hoc, informal or unintended software modifications 
* **Change request form**: record the proposed change (requester, reason, urgency) and the change evolution (impact analysis, cost and recommendation)
* **Impact analysis**: config items affected, impact on cost, schedule, deliverables and resources, risk associated with implementing the change, risk with non implementing
* **Change control board**: group responsible for reviewing proposed changes, inde of the dev project team, decide on strategic, organisational and technical view points

<br/>

#### Traceability
* **Key concept**: ability to record development decisions and changes to allow rationale for development approach to be related to earlier work. Provides project progress visibility and provides sense of accountability.
* **Traceability Matrix**: correlate different project documents or config items
* **Configuration audit**: Ensure that agreed changes are implemented correctly

<br/>

#### SCM standards
* SCM should be based on standards (ex: IEEE) defining how items are identified, how changes are controlled and how new versions are managed
* **IEEE Std 828**: Intro, SCM Management (Who?), SCM Activities (What?), SCM Schedules (When?), SCM Resources (How?), SCM Plan Maintenance
* **Disaster recovery**: policies and procedure in place for the recovery of IT infrastructure within an organisation

<br/>

#### Software Documentation
* **Outline design**: explain rationale for design approach
	- Aimed at management
	- Used for project proposals, to justify funding

* **Technical**
	- Requirements, design, implementation
	- Document the design process
	- QA requirements

* **User**: installation, operation, tutorial and support
* **Marketing**
	- Advertise products
	- Inform potential users/customers
	- To place product in the marketplace
