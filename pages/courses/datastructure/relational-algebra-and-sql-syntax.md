---
layout: page
title: "Relational algebra and SQL syntax"
description: "Structured data course review"
---
{% include JB/setup %}

#### Relational algebra operators

* **Selection**, \[σ\], selects rows from a table.  
Example: σ Firstname = 'Thibault'(STUDENT)

* **Projection**, \[π\], projects out columns from a table.  
Example: π Firstname(STUDENT)

* **Renaming**, \[ρ\], can be used to rename tables.  
Example: ρ Firstname <- Name(STUDENT)

* **Cartesian product**, \[x\], of two relations (tables) consists of all the tuples of the
first, combined in all possible ways with the tuples of the second.  
Example: A x B = {< a,b >: for all a,b aEA and bEB}

* **Natural Join**, \[∞\], matches up corresponding attributes (attributes with the same names and values) in two tables.
The result is a table in which no two attributes have the same name.  
Example: Employee ∞ Department
 
* **Division**, \[%\], restricts attributes names uniqueness of a table, for which it holds that
all their combinations with another table are present in the first one.  
Example: Employee % Department

* **Union**, \[∪\], of a collection of sets is the set of all distinct elements in the collection.  
Example: A ∪ B = {x: xEA or xEB}
 
* **Intersection**, \[∩\], of two sets A and B is the set that contains all elements of A that also
belong to B but no other elements.  
Example: A ∩ B = {x: xEA and xEB}

* **Set Difference**, \[\\], of U and A (U\A) is the set of all members of U that are not members
of A (also called relative complement)
Example: U\A = {xEU | x!EA} 

* * *

#### SQL Syntax 

<script src="https://gist.github.com/4586266.js"> </script>