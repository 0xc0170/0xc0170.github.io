---
layout: page
title: "Risk Management"
description: "Software Project Management course review - part 5"
---
{% include JB/setup %}

#### Introduction on Risk Management
* Address project specific risks
* Look at possible problems and their contingencies
* Consider what could happen, and look for ways to minimise damage
* Plan to manage potential causes of failure
* What to do about risks
	- **Reactive**: deal with the risk when it occurs
	- **Proactive**: plan ahead to anticipate hazards

<br/>

#### Reasons for needing risk management (Boehm)
* Avoid project disasters: budget, schedule, maintenance or operation failure
* Avoid rework caused by missing or incorrect requirements, design or code
* Avoid overkill in areas of minimal or low risk
* Aim for win-win solution: customer happy with product, vendor makes business profit

<br/>

#### Classification of risks:
* **Project risks**: affect schedule or resources (coordination problems, supplier relationships, internal politics…)
* **Product and process risks**: affect the functionality, quality or performance of the 
software being developed (undocumented process, poor design…)
* **Business risks**: affect both organisation developing the software and the customer using the software (lack of expertise, complex design…)

<br/>

#### Risk Management:
* **Risk Assessment**: 1 Identification, 2 Analysis, 3 Prioritisation
* **Risk Control**: 1 Management Planning, 2 Resolution, 3 Monitoring

<br/>

#### WBS Project Risks
* **Technical**: requirements, technology, complexity, interfaces, performances, reliability
* **External**: suppliers, subcontractors, regulatory, market, customer, weather
* **Organisation**: dependencies, resources, funding, prioritisation
* **Management**: estimation, planning, controlling, communication

<br/>

#### Activities of risk analysis
* **Grouping**: eliminate redundancy, link dependent risks, combine related risks
* **Determining risk drivers**: increases understanding of how risk can be mitigated, underlying factors that affect severity of consequence
* **Ranking**: order of likelihood, consequence, exposure, time frame
* **Determining root causes**: sources of risk

<br/>

#### Anatomy of a risk:
* **Likelihood**: probability of occurrence, as a fraction (0.0-1.0), as a scale value (1-10), 
as a category: very low, low, moderate, high or very high
* **Consequence** or **impact**: size or cost of loss, rated insignificant, tolerable, serious, 
catastrophic

<br/>

#### Risk Exposure 
* Risk Exposure = **Risk Likelihood x Risk Impact** (on a 1-10 scale for both) quantify the 
importance of risks
* **Man-day method** with likelihood in fraction 0.0 to 1.0 and cost in days -> risk exposure in days

<br/>

#### Risk Control
* **Avoidance**: identify or implement alternative procedure or activities to eliminate risk
* **Contingency**: have a prearranged plan of action that will come when the risk occurs
* **Prevention**: put in place measures to stop a problem from occurring
* **Reduction**: take action to minimise likelihood or impact of the risk
* **Transference**: transfer the risk to a third party
* **Acceptance**: when it would be too expensive or likelihood and impact are minor

<br/>

#### Risk Analysis – Report: 
* Risk description, risk category, likelihood, impact, priority, risk action plan:  who, when, what

<br/>

#### Risk Response Matrix: 
* Risk event, mitigation plan, contingency plan, trigger, responsibility

<br/>

#### Evaluating risks to the schedule
* Best estimate task times Tb or μ = (optimistic + 4 x most_likely + pessimistic) / 6
* Standard deviation σ = (pessimistic – optimistic) / 6
* PERT: 
	- Tb = sum of each tb
	- σ ² =  sum of each σ² -> σ = √(σ(_^2)1+ σ(_^2)2 )… 

<br/>

#### Cumulative Normal Probability Tables (Z-values) = (T-t)/s

<br/>

#### The risk management process (CCL): 
* Learn about risks (risk knowledge base), identify risks, analyse risks, plan for risks, track risks, resolve risks