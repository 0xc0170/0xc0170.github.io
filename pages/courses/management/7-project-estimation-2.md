---
layout: page
title: "Project estimation - part 2"
description: "Software Project Management course review - part 7"
---
{% include JB/setup %}

#### Estimation Process
* Continual process used throughout the life cycle of a project
* Stages: Establish the reason for the estimate -> Obtain all the existing information -> Determine the requirements -> calculate the size, effort, timescale -> Assess risk -> Discuss and refine the estimate -> Agree and document the estimate

<br/>

#### COCOMO (COnstructive COst MOdel) model

* By Dr Barry W Boehm, algorithmic model build around equation
* Effort = A * (Size) ^ P * EAF ( Size in KSLOC: Thousand Source Lines of Code ; A & P depends on development mode; Effort in person month)
* Three models:
    - Basic model: single-valued model, estimates effort as a function of program size taking into account the estimated source code. (EAF=1)
    - Intermediate model: Basic model + a set of cost drivers (including product, hardware, personnel, and projet attributes) rated on 6-point scale (very low, low, nominal …) and with assigned weighting factors (EAF = factors multiplication)
    - Advanced or detailed model: Intermediate model + the assessment of cost driver’s impact on each phase such as analysis, design, implementation, etc.
* Three development modes:
    - Organic: simple project, small team work together, no commu overhead
    - Semi-detached: medium sized project, moderate level of experience
    - Embedded: tight set of constraints, large team, big project

<br/>

<div class="row">
    <img class="span7 offset2" src="{{ ASSET_PATH }}img/page/courses/estimation.png" />
</div>

<br/>


#### COCOMO II

* Take into account different requirements of software such as distributed software, web-based software etc.
* Used to estimate efforts for different stages in the system life cycle (see sub-models)
* Uses various effort multipliers (cost drivers) and exponent drivers. Exponent drivers replace modes in COCOMO.
* Three different sub-models:
    - Application Composition: projects where extensive reuse of software parts
    - Early Design: when requirements are available but design not yet started
    - Post-Architecture: when system architecture is designed and more info about the system is available
* Differences with COCOMO:
    - Size: KSLOC + object points or functions points
    - EAF = 7 (early design) or 17 (post-architecture) cost drivers instead of 15 for intermediate COCOMO model
    - Modes are replaced by 5 Scale Factor (SF, or exponent drivers)
* Effort = A (SIZE) ^ SF * EM
* Five exponent drivers:
    - Precedentedness: novelty of the project, experience with similar project
    - Development flexibility (needs requirements)
    - Architecture/risk resolution: degree of uncertainty in the requirements
    - Team cohesion: large dispersed or well integrated team
    - Process maturity: structure and organisation
