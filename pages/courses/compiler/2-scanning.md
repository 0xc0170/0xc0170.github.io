---
layout: page
title: "Scanning"
description: "Language spec and compiler construction - part 2"
---
{% include JB/setup %}


#### Task of a scanner

* Delivers tokens (token stream, must end with eof)
* Skips meaningless characters such as blanks, comments, end-of-line characters (CR, LF), tabulator characters

<br/>

#### Regular grammars:

* Can be described by production of the form X=a. X=bY. -> a single non-recursive EBNF production
* limitation: cannot deal with nested structures (because they cannot handle central recursion)

<br/>

#### DFA (Deterministic Finite Automaton) 
* It can be used to analyse regular languages (The scanner can be viewed as a big DFA)
* It is a 5 tuple:
    - S: set of states
    - I: set of input symbols
    - Δ: S x I -> S state transition function
    - s0: start state
    - F: set of final states

<br/>

#### Scanner Implementation

* Initialize the scanner
* Read the token stream (next() method, Token class, tokens code integers or enum, nextCh() methods + readName(Token t), readNumber(Token t), readCharCon(Token t))
