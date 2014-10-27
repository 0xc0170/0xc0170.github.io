---
layout: page
title: "Project estimation - part 1"
description: "Software Project Management course review - part 6"
---
{% include JB/setup %}


#### Estimation Overview

* Size of the project
* The project duration/schedule
* The overall cost of the project
* Efforts involved in the project

<br/>

#### The Basis for Software Estimating

* Historical data: past project analysed but differences may exist
* Measure of work: varies according to tools, development environment, experience
* Complexity of software component also varies

<br/>

#### The Estimation Process: continual process used throughout the life cycle of a project

* Estimate the size: requires two main inputs: software requirements specification and historical size data
* Estimate the cost and effort required to complete the software
* Assess the Risk and their impact on the project estimates (size, cost, effort, duration)
* Refine Estimate

<br/>

#### Estimation Methods (selection depends on project’s scope, purpose of estimate and availability of estimating resources)

* Expert judgement method (Delphi technique): use their experience/understanding of the proposed project to produce estimates
* Tod down method assumes that it is possible to estimate overall effort from a relatively small number of parameters (e.g. FPA)
* Bottom up method need considerable effort because of the need for a very comprehensive product and work break down

<br/>

#### Function Point Analysis (FPA): estimate effort and time of a software project

* Function Point as a unit of measure for software (e.g. 230 FPs)
* Estimation independent of Programming language, hardware platform, development method

<br/>

#### FPA takes into account

* Input transactions which add or change data
* Output transactions where data is output to the user or to another system
* Logical Internal Files: data files used by a system
* External enquiries: transactions initiated by the user which provide information
* Complexity factors: 14 to 19 complexity factors ranked from 0 to 5

<br/>

#### Working Mechanism of FPA: (steps)

* 1 Identify all the transactions (functions) of a software system
* 2 Size each transaction (function): Number of input, output and entities
* 3 Sum the counts for all transactions: Sum inputs, outputs, entities
* 4 System size: Function Point Count (FPC) = sum of weighted counts (I * W1 + E * W2 + O * W3) Weighting constants are industry averages
* 5 Determine the system complexity: rate each complexity factor between 0 (low) and 5 (high) then Total Technical Complexity Factor (TCF) = sum of complexity factors
* 6 Calculate the Adjustment Function Point (AFP) Count: AFPC = TCA * FPC
TCA (Technical Complexity Adjustment) = 0.65 + 0.005 * TCF
* 7 Determine Effort (man-days) = AFPC / Productivity (table to select productivity rate)
* 8 Determine Elapsed Time = AFPC / Delivery Rate (Delivery Rate = 0.45 * 〖(AFPC)〗^(1/2))
Delivery Rate is the number of function points delivered per week
* 9 Apportion effort & elapsed time to stages: distribute effort and timescales over the project phases
* 10 Adjust estimates for risks and constraints
