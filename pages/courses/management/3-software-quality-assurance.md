---
layout: page
title: "Software Quality Assurance"
description: "Software Project Management course review - part 3"
---
{% include JB/setup %}

#### History
* 1970’s: customer orient development -> software lifecycle crisis
* 1980’s: customer satisfaction consideration -> shared responsibility
* 1990’s: scope of quality expanded -> non-functional issues (safety, ethics…)

<br/>

#### What is quality?
* **Relative**: it’s about a product being used in a particular context
* **Multidimensional**: price, reliability, maintainability, ease of use …
* Quality dimensions are **dependent**: ex: price and reliability are not independent
 
 **AQL**: Acceptable Quality Level

**ISO/IEC 8402**: “The totality of features and characteristics of a product or service that bear upon its ability to satisfy specified or implied needs”

<br/>

#### **Levels** of quality:
* **Absolute** (quantify)
* **Relative** (comparative)

**Quality Process -> Quality Product** (concept from manufacturing and engineering)

**Garvin (1998)**, Quality: transcendent, user, process, product and value based

Cost versus Quality optimisation: an **optimum** needs to be established

Software **quality characteristics**: efficiency, cost, effectiveness, reliability, maintainability, safety, security, usability

<br/>

#### Quality as part of **software documentation**
* **Functional specification**: what the system will do
* **Quality plan**: quality attributes applicable, how it is assured
* **Project management plan**: timing, dependencies and resource requirements

<br/>

#### **McCall’s Model**
* **Product Operation**: the smooth running of existing software – Correctness, reliability, efficiency, integrity, usability
* **Product Revision**: the ease of changing software and bug fixing – Maintainability, testability, flexibility
* **Product Transition** - Portability, reusability, interoperability

<br/>

#### **Quality Factor** – Relationship (between pairs of quality factors):
* **Indifferent**: zero correlation
* **Complementary**: positive correlation
* **Conflicting**: negative correlation

<br/>

#### **CMMI**: Capability Maturity Model Integration
* Process improvement approach to software development
* **Levels**: chaotic (initial), repeatable (managed), defined, quantitatively managed, optimised

<br/>

#### **Measures** for Software Quality:
* The **test** measure a given quality factor
* A **metric** is a quantifiable measurement relating to a quality criteria
* A **scale** defines the **range** and **unit** of measurement
* A measurement type may be **binary** or **relative**
* A **range** which includes a worst, a best, a planned and a “now” value

<br/>

#### McCall: 
* **quality factor value: Fq = c1m1 + c2m2 + … + cnmn**
* Ci: criteria relevance or weighting (internal measure)
* Mi: criteria metric value or score (internal measure), 0 to 10
* N: number of criteria

Software metrics: count **Lines of code** (**LOC**) or KLOCs (30lines/day developer average)

<br/>

#### Code complexity metrics:

<br/>

* **Halstead**: count operators and operands
	- n1: number of distinct **operators** in a program
	- n2: number of distinct **operands** in a program
	- N1: total number of operator occurrences
	- N2: total number of operand occurrences
	- **Vocabulary**: n = n1 + n2, Implementation length: N = N1 + N2
	- **Program length** N = n1log1n1 + n2log2n2
	- **Program volume** V = Nlog2(n1+n2)
	- **Program level** (complexity) L = (2/n1) x (n2/N2)

<br/>

* **McCabe**: determine control structure from **flow graph**
	- Detail design notation with loops and all the paths as unit test prediction
	- Flow graphs to measure **code complexity**
	- **Regions** = number of arcs (edges) – no of nodes + 2
	- 1-10: simple, 11-20:moderate, 21-50:complex, high risk, 51+: untestable

<br/>

#### Problems with Software metrics:
* Relationship between quality criteria and metric values need to be established
* Some criteria are unmeasurable or not have tested metrics
* Some metrics are linked to several criteria and difficult to predict
* Cost of collection


**ISO 9126** defines 6 software quality criteria: functionality, reliability, usability, efficiency, maintainability and portability and sub characteristics.

**Reasons to adopt standards**: avoid errors, create confidence, increase productivity and product quality, reduce development costs, customers expect it, condition of contract

Standards apply at three levels: **Product** (code, documents, methodology), **Project** and **Management**

Hierrachy of standard makers: International (ISO, IEC), National (BSI, ANSI), Sector Specific (Defense, Nuclear), Proprietary (UML), Organizational (W3C, MS), Project, Personal

**ISO 9000**: define what you do, document the system, demonstrate that you do what you say you do, demonstrate it to customers through registration (obtain certification)

<br/>

#### ISO 9001: 
* Models for quality assurance in design, development, production, installation and servicing
* **Certification**: recognise competence or conformance, provide evidence that an organisation is capable of producing quality products or services
* **Accreditation**: ability to award certified, an accreditation body accredits a certification body after satisfying itself that it operates in accordance with appropriate criteria of competence

<br/>

#### Quality Management:
* **Hierarchy**: Quality Management (quality plan), Quality Assurance (define procedures), Quality Control (check procedures)
* **Evolution**: Inspection focus on errors, quality control focus on product, quality assurance focus on process, quality management focus on development culture
* **Quality Control**: operational techniques and activities used to fulfil requirements for quality
* **Quality Assurance**: steps taken to make sure that a company’s product or service are sufficiently high quality, includes software engineering methods, review, testing, documentation, software dev standards & control, measurement, reporting.
* **Total Quality Management**: is the management approach of an organization, centred on quality and based on the participation of all its members, and aiming at long-term success through customer satisfaction and benefits to all members of the organization and the society.

<br/>

**Quality and Safety critical systems**: result in loss or damage to people, assets or equipment. **Control system** & **Protection system**

**Validation**: Concerns the software product, demonstrate that system satisfies user requirements. Assessed using dynamic **testing** (performance, regression, acceptance, usability, stress, security, recovery, alpha and beta testing)

**Verification**: Concerns the dev process, ensure component or system conforms to its specification, the output conforms to its inputs

**Testing adequacy**: complete testing usually impossible. Specify % coverage, testing costs, how to generate test values

**Dynamic testing elements**: program under test, test case, observation, analysis of results

**Generic testing process**: Planning, Specification, Execution, Result recording, evaluation

**Test plan**: for a module, component or system document part of the system being tested, general testing strategy, hardware and software dependencies, date, location, individuals. For each test include what program/module, what level of testing, scenario or test case, how to test (input and output expected), test results (analyse)