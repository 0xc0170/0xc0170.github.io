---
layout: page
title: "Project Approaches and methodologies"
description: "Software Project Management course review - part 2"
---
{% include JB/setup %}

### Software development

<br/>

#### Why to develop software systems?
* **Automation**: To reduce costs and improve both quality and service (bank account management, library loan administration, stock control…)
* **Information**: Improve decision making by generating useful information (sales analysis, inventory management, insurance policies…)
* **Transformation**: New technologies create new opportunities for organisations. Internet applications changed the significance of time and geography (e-commerce, e-learning, social network, online news…)  

<br/>

#### How to develop software system?
* **Unstructured** (or **partially**) development
	- Developers can start coding quickly before analysis and design has been done
	- Problem: frequent re-working, lack of clearly defined stages
* **Structured** development:
	- Break the project into clearly defined **stages**, stages may take place in sequence or in parallel
	- Stages are composed by a set of predefined **tasks**, tasks produces one or more deliverables

<br/>

#### Define each stage in terms of:
* **Input and output**
* **Quality**: Working to Standards, applying techniques, reviews, inspections, testing
* **Techniques used**: Structured techniques (dataflow diagram, logical data model) or OO techniques (UML diagrams like class or sequence diagrams)

<br/>

#### Resources required: 
* Hardware, Software, Staff (+DB designer & dev, web designer...)

<br/>

***

<br/>

### Software development methodologies 

<br/>

#### Software lifecycle phases: 
* **Planning**
* **Analysis** (Business or requirement analysis)
* **Design**
* **Implementation**
* **Testing**
* **Operation and maintenance**

<br/>

#### Waterfall model
* Analysts and users proceed in sequence from **one phase to another**
* When to use: low risk applications, experienced staff familiar with the environment, requirements unlikely to change, clear existing and known requirements.

<br/>

#### Rapid application development (RAD - Prototyping)
* Develop some parts of systems quickly and give them to users for **feedback**
* **Throwaway prototyping**: One or more prototypes are developed to test some ideas of the proposed system, prototypes are discarded when the true dev is commenced.
* **Evolutionary prototyping**: A prototype is developed and modified until it is finally in a state where it can be operational system
* **Pros**: end-user involvement, clarify user requirements, usability of the system. 
* **Cons**: hard to control budgets/resource use, danger of “requirements drift”

<br/>

#### Spiral model
* Another way of looking at the waterfall model (see also **V cycle**)
* Modeled as a **loop** where the proposed system is considered in more details in each loop, series of prototype, cost determined by the width of the spiral
* **Four phases**: determine goals, alternatives, constraints, evaluate alternatives & risks, develop & test, evaluation and plan for next phases

<br/>

#### Agile
* Focus on:
	- **Working software** than comprehensive documentation
	- **Customer collaboration**/participation than contract negotiation
	- **Responding to change** than following a plan
	- **Team work and self-organisation** than having a coordinator or a manager
* Methodologies: XP, Scrum, ASD (Adaptive Software Development), FDD (Feature Driven Development)

<br/>

#### Extreme Programming (XP)
* Best practices: customer team member, user story, test driven design and dev, pair programming, collective ownership, continuous integration
* 4 principles: Communication, simplicity, feedback, courage

<br/>

#### Scrum
* **Scrum master**: implements scrum, a coach, removes any impediment 
* **Product owner**: represents the customer, maintain product backlog, prioritise 
* **Team**: between 5 and 9, self-organisation, cross functional, specific expertise but no specific role
* **Product backlog**: contains prioritized list of tasks or users stories, constantly updated
* **Sprint**: 2 to 4 weeks, no changes during sprint, working deliverable at the end
* **Sprint backlog**: users stories with states (to do, working on, done, bug)
* **Daily scrum**: 5 minutes, stand-up, what I have done, what I will do, impediment

<br/>

#### Online Evolution Model
* Developed for web apps, combination of existing software methods and activities
* Two cycles: **Build and test cycle** and **Evolution cycle** corresponds to the two phases **Offline development** and **Online evolution**

<br/>

#### Choosing a methodology:
* **Type of the system**: real-time, single or multi users, single or multi-platform
* **Time to market**
* **Changing requirements**
* **Users involvement**
* **Technologies**
