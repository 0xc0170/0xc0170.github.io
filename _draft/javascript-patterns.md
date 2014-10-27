---
layout: page
title: "JavaScript Patterns"
description: "author: "
---
{% include JB/setup %}
                                              
#### 1 - Introduction

* Approach: embrace JS differences and study its specific patterns
* Importance of patterns:
    - help us write better code
    - provide a level of abstraction
    - improve communication
* Five primitive types: number, string, boolean, null and undefined


#### 2 - Essentials

* Always use var, because of the notion of “implied global”
* Implied globals can be undefined using the delete operator
* Access to the global object: var global  = (function () { return this;}());
* Single var pattern: use one var statement and declare multiple variables delimited by commas
* Hoisting: have multiple var statements anywhere in a function and they all acts as if they were declared at the top of the function
* More detail: first stage is parsing and entering the context: variables, functions declarations, and formal parameters are created; second stage is runtime code execution: function expression and unqualified identifiers (undeclared variables) are created
* Pattern for the for loop: cache the length of the array: 
for (var i=0, max=myarray.length; i < max; i++)
* myObj.hasOwnProperty() filter out the prototype properties
* Avoid implied typecasting by using === and !== to check both values and types
* “eval() is evil”
* Naming convention and best practice:
    - Curly braces should always be used
    - Semicolon should always be used (even when they are implied, they help to resolve ambiguities)
    - camelCase for methods and properties
    - all-caps for constant
    - underscore prefix to denote a private method or property
* Writing API docs: JSDoc Toolkit or YUIDoc

#### 3 - Literals and Constructors

* object literal notation var obj = {} is preferred to constructors, is mutable at anytime, inherit from Object.prototype
* Object(arg) delegate the object creation to the built-in type corresponding to arg
* Reusable member, such as methods, should go to the prototype:
Person.prototype.say = function() {return “I am” + this.name}
* If a constructor is called without “new”, “this” refer to the global object, selft-invoking constructor to avoid it:
If (!(this instanceof arguments.callee)){ return new arguments.callee();}
* Check for Array-ness with Array.isArray();
* JSON: a combination of the array and the object literal notation; JSON.parse() and JSON.stringify()
* List of literals: var o = {}; var a = []; var re = /[a-z]/g; var s = “”; var n = 0; var b = false;



#### 4 - Functions

* First-class object and provide scope (blocks don’t create scope)
* Terminology: function expression (aka anonymous function) and the named function expression is a specific case of function expression _ function declarations (like in another language)
* Self-defining function (or lazy function definition) is useful when a function has some initial preparatory work to do and it needs to do it only once
var scareMe – function () { initCode; scareMe = function () { otherCode; }};
* Immediate functions (or self-executing): execute a function as soon as it is defined, usefull because provides a scope sandbox for your init code
(function () { someCode; } ());
* Immediate object initialization (same benefit as immediate function)
({ someCode; init = function () {} }).init();
* Function properties (a memorization pattern): used to cache the results of a function
var myFunc – function (param) { if (! myFunc.cache[param]) { /cache the result/ } return myFunc.cache[param]; };

#### 5 - Object Creation Patterns

#### 6 -Code Reuse Patterns

#### 7 -Design Patterns

#### 8 - DOM and Browser Patterns
                       
                       
                       
