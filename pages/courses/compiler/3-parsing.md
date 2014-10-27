---
layout: page
title: "Parsing"
description: "Language spec and compiler construction - part 3"
---
{% include JB/setup %}


#### Context-Free Grammars (CFG) and Push-Down Automata (PDA)

* Regular grammar cannot handle central recursion (E=x | ”(”E”)”.)
* CFG if all its production have X = α (X:NTS, α:non-empty sequence of TS and NTS)
* PDA recognize CFG, allows transition with TS and NTS, and uses a stack to remember the visited states.
* CFG cannot express context condition: use context-sensitive grammar or check context conditions during semantic analysis

<br/>

#### Recursive Descent Parsing

* Alternative selected using the lookahead token from the input stream and the terminal start symbol of the alternative.
* scan() set most recently recognized token and lookahead token, parse TS check(a), parse X NTS X() 
* Parse: option with if, alternative with if/else, iteration with while(first TS)
* Opti: avoid multiple check, for(;;) and break for iteration and alternatives in an iteration, attention on deletable symbol

<br/>

#### LL1 (Left to right with Left-canonical derivations and 1 lookahead symbol) Property

* Definition: First(αi) ∩ First(αj) = {} (for any i ≠ j)
* Remove LL(1) conflicts: extract common start sequence, sometimes inline NTS before factorisation. Left recursion is a LL(1) conflict, replaced by iteration.
* Hidden conflicts on EBNF options and iterations: 
    - X = {α} β. Or X = [α] β. First(α) ∩ First(β) must be {}
    - X = α {β}. Or X = α [β]. First(β) ∩ Follow(X) must be {}
    - X = α | . First(α) ∩ Follow(X) must be {}

<br/>

#### Error Handling

* Panic Mode
* Dynamically computed recovery sets
* Synchronization points
