---
layout: post
title: "Project generator - building exported project"
date: 2014-09-18
comments: true
categories:
 - python
---


The build feature has been implemented in the last 2 days aka ProjectBuilder. This allows to build exported projects, which is useful for automated testing.


The building is currently supported for all tools there (IAR, uVision, Makefile), but IAR still has one bug, does not generate any output eventhough builds without errors. Want to share with you, that I am currently adding CoIDE (only export, as it does not support building via command line). Should be completed this week. Anyone out there using the project generator? What tool would you like to see there ? Eclipse? LPCExpresso? Kinetis Design Studio?


The real example is here [github.com/0xc0170/project_generator_mbed_examples](https://github.com/0xc0170/project_generator_mbed_examples), using mbed SDK. I replaced mbed library by mbed SDK submodule, to stay up to date. The example repository shows how are records written and how to use it with your own files (blinky demo).
