---
layout: page
title: "Professional Node.js"
description: "author: Pedro Teixeira"
---
{% include JB/setup %}

#### Introducing Node

Event-driven programming: the flow is determined by the flow of event. Programmers register callbacks to be used as event handlers for events they are interested in, and the system invokes these handlers when those events occurs. 
Advantages: no need to use multiple processes or threads to scale. 
JS suits well: first class function and closures

***

### Node core API basics

#### Loading modules

JS bad feature: the sharing of a global namespace among scripts -> Node use the CommonJS modules standard: each module has it's own context, separated from the other modules.
To load a module: var module = require('my_module');
The require function return a JS object representing the API exposed by the module. That object can be any JS value (object, function, array..). 
'my_module' can be:
	- a module name, to load a nodejs core module
	- a module name, to load a module from the node_modules folder. (1: if nodejs fails to find the module in node_modules folder of the current directory, it will try the parent folder and keep descending until it reaches the root) (2: the node_modules folder os the default folder where npm installs modules)
	- a module path, to load a custom module. The path can ba absolute or relative to the current file
	- a folder path. Node will presume the folder is a package and will try to find a package definition file (package.json, with the main entry point of the package defined in it). I there is no package.json file in the folder, nodejs will assume that the main entry point is a file named index.js and will look for it.
The '.js' extension can be omitted when loading a module: nodejs will automatically add the '.js' extension when looking for the module
Modules are cached the first time they are loaded, if a module is required two times, the module initialization runs only once.



#### Using buffers to manipulate, encode and decode binary data

#### Using the event emitter pattern to simplify event binding

#### Scheduling the execution of function using timers