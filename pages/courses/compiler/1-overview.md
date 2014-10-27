---
layout: page
title: "Overview"
description: "Language spec and compiler construction - part 1"
---
{% include JB/setup %}


#### Introduction

* Compiler translates source code to machine code
* Interpreter executes source code “directly” (ex: statements in a loop are scanned and parsed again and again).
* Variant: interpretation of intermediate code of a VM

<br/>

#### Dynamic structure of a compiler :

* 1 Lexical analysis (scanning) -> token stream, token has numbers + values (when needed)
* 2 Parsing -> syntax tree (structure of the program)
* 3 Semantic analysis (type checking, symbol table…)
* 4 Optimization
* 5 Code generation (machine or bytecode)

<br/>

#### Static structure of a compiler:

* Scanner: provides tokens from the source code
* Parser and sem. Analysis: “main program” directs the whole compilation
* Symbol table: maintains info about declared names and types
* Code generation: generates machine code

<br/>

#### Grammars: four components
* Terminal symbols: are atomic (“if”, ident, number…)
* Nonterminal symbols: are decomposed into smaller units (Statement, Condition, Type…)
* Productions: rules how to decompose nonterminals (Statement = Designator “=” Expr”;” … )
* Start symbol: topmost nonterminal

<br/>

#### EBNF (Extended Backus-Naur form) for writing grammar
* Productions
    - Statement = “write” ident “,” Expression “;”.
    - Terminal symbols start with lower-case letters
    - Nonterminal symbols start with upper-case letters
* Metasymbols
    - | separates alternatives -> a|b|c = a or b or c
    - (…) groups alternatives -> a(b|c) = ab | ac
    - […] optional part -> [a]b = ab | b
    - {…} iterative part -> {a}b = b | ab | aab | aaab …
* John Backus developed the first fortran compiler, Peter Naur edited the Algol60 report

<br/>

#### Start symbols:

* terminal symbols with witch a nonterminal can start -> First(Factor)=ident, number, “(”

<br/>

#### Successors:

terminal symbols can follow a nonterminal in the grammar -> Follow(Expr)=”)”, eof (eof: end of file)

<br/>

#### Strings

* A finite sequence of symbols from an alphabet
* Alphabet: all terminal and nonterminal symbols of a grammar
* Strings denoted by greek letter α, β … , emty string ε

<br/>

#### Derivation

* Direct: α => β -> Term = Factor * Factor => Term = ident * Factor
* Indirect: α => y1 => y2 => … => yn =>s β

<br/>

#### Recursion: can be used to represent repetitions and nested structures

* Direct: X => ω1 X ω2
    - Left recursion X = b | Xa.
    - Right recursion X = b | aX.
    - Central recursion X = b| “(” X “)”.
* Indirect: X => * ω1 X ω2

<br/>

#### Chomsky’s classification of grammar

* Class 0: Unrestricted grammars recognized by Turing machines (α and β arbitrary)
* Class 1: Context-sensitive grammars recognized by linear bounded automata ( |α| ≤ |β|)
* Class 2: Context-free grammars recognized by push-down automata (α = NT, β ≠ ε)
* Class 3: Regular grammars recognized by finite automata (α = NT, β = T or T NT)
