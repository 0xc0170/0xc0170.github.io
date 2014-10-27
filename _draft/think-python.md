---
layout: page
title: "Think Python"
description: "author: Allen B. Downey"
---
{% include JB/setup %}


#### Variables, Expressions, and Statements

* Python performs floor division, for instance when both of the operands are integers, the result is also an integer (5/3 = 1)
-> if either of the operands is a floating-point number, python performs floating point division (5.0/3 = 1.666667)
* String operations: the '+' operator concatenates strings & the '*' operator performs repetition.  


#### Functions

 * Built-in type conversion function: int(), float(), str()
 * Statements inside functions are not executed until the function is called
 * Arguments are evaluated before the function is called


#### Case Study: Interface Design

 * for loop: for i in range(x, y):
 * Docstring: multiline (triple-quoted) string at the begining of a function that explains the interface
 * Preconditions: requirements/conditions on the functions arguments
 * Postconditions: effect of the function and any side effects


#### Conditionals and Recursion

* Logical operators: and, or & not
* elif is an abbreviation of "else if"
* keyboard input: raw_input (python 2) & input (python 3)


#### Fruitful functions

* The return statement can include an expression (return 3*4)
* Check type of a var: isinstance(var, type)


#### Strings

* Methods: len('mystring'), 'mysring'[n:m] (slice), 'mystring'.upper(), 'mystring'.find('charorstring'), .count(), .strip(), .replace()
* In: boolean operator


#### Case study: World play

* Methods on files: file = open('file_path'), line = file.readline(), word = line.strip()


#### Lists

* list = [], elements of a list don't have to be the same type
* lists are mutable (unlike strings): numbers = [17, 123] -> numbers[1] = 5
* traversing a list: for l in list or for i in range(len(list)) (combine the function range and lens give the indice i)
* operators: + concatenate lists, * repeats a list, "in" and "slice" are available
* list methods: "append" adds a new element to the end of a list, "extend" takes a list as an argument and appends all of the element, "sort" sort elements from low to high (sort(reverse=True) to reverse), list methods are all void
* "reduce": traverses a sequence and accumulates the elements into a single result: sum(list) adds list elements
* "map": traverse a sequence and performs an operation on each element: built-in map function
* deleting elements: list.pop(index) returns the element that was removed unlike del list[index] (del can also delete range of elements) / t.remove(element) when the index is unknown (return None)
* lists and Strings: t = list(string) -> convert a string into a list of char / t = string.split() -> break a string into words (split takes an arg acting like a delimiter) / delimiter.join(list) inverse of split
* "is" checks whether two variables refers to the same objects (same string: true, same list: false)
* An object with more than one reference has more than one name: the object is aliased, if the object is mutable, changes made with one alias affect the other.
* Passing a list to function, the function gets a reference to the list (if the function change the list, the caller see the change)
* important: distinguish operation that modify lists and operations that create new lists (most list methods modify the argument and return None, it's the opposite for string methods which return a new string and leave the original alone)
* methods and operators that lists share with other sequence: http://docs.python.org/2/library/stdtypes.html#typesseq
* methods and operators that only apply to mutable sequences: http://docs.python.org/2/library/stdtypes.html#typesseq-mutable


#### Dictionaries

* d = dict() -> creates a new dictionary with no items
* the order of items in a dictionary is unpredictable
* len(d) and 'test' in d works on dictionary
* the in operator uses different algorithms for lists and dictionaries: search algorithm for lists and hash-table for dictionary
* d.get(key, default_value) -> returns the default value if the key is not in the dictionary
* dictionaries have a method called keys that returns the keys of the dictionary, in no particular order, as a list
* lookup: v = d[key] / reverse lookup (much slower): for k in d: if d[k] == v:
* dictionary is implemented using a hashtable: keys have to be hashable (a hash is a function that takes a value and returns an integer, dictionary use this integer to store and look up key-value pairs).
* keys have to be immutable (if the key is updated, it would go to a different location) -> list cannot be used as keys
* global variables has to be declare with "global" to be reassigned in a function (unless the global variable is mutable, it can be modified without declaring it as global)
* Python 3: long id gone, all integers are type int


#### Tuples

* a tuple is a comma-separated list of values
* to create a tuple with a single element, include a final comma: t1 = 'a',
* t = tuple() -> create an empty tuple
* most list operators also works on tuples
* swap values f two tuples: b, a = a, b (called tuple assignment)
* gather: the operation of assembling a variable-length argument tuple (*arg: functios can take a variable number of arguments, ex: print, min, max)
* scatter: the operation of treating a sequence as a lists of arguments (give *tupple to a function that doesn't accept a variable number of argument)
* zip(seq1, seq2): takes two or more sequences and zip them into a list of tuples where each tuple contains one element from each sequence. (if the sequences are not the same length, the result has the length of the shorter one.)
* for index, element in enumerate(seq): traverse the seq with both elements and indices
* dictionaries and tuples: tupple = dico.items() -> returns a list of tuples where each tuple is a key-value pair / other direction: d = dict(tuple_list)
* for key, val in d.items(): to traverse the dico
* it's common to use tuples as key in dictionaries (because you can't use list): directory[last_name, first_name] = number
* relational operators works with tuples and other sequence (python starts by comparing the first element from each sequence). sort works the same way
* DSU: Decorate-Sort-Undecorate a pattern that involves building a list of tuples, sorting, and extracting part of the result
* http://www.greenteapress.com/thinkpython/code/structshape.py summarize shapes od datastructure (list, tuple, dico etc.)


#### Case study: Data structure selection

* The string module provides strings named string.whitespace and string.punctuation (contains white space and punctuation characteres)
* deterministic: giving the same input, the program does the same thing each time it runs
* pseudorandom: sequence of numbers that appear to be random, but are generated by a deterministic program (check the random module)
* random.random() -> between 0.0 (included) and 1.0 (excluded) / random.randint(low, high) -> return an interger between low and high (included) / random.choice(seq) -> choose randomly in the sequence
* def my_func(a, b=10): -> b=10 is default value for optional parameter
* check data structure set: http://docs.python.org/2/library/stdtypes.html#types-set


#### Files

* fout = open('output.txt', 'w') -> open a file in write mode, if the file exists it erase the data, if the file doesn't exist it creates it.
* fout.write("some text") and fout.close()
* % on string is the format oprator: %d for integer, %g for floating-point number and %s for string -> '%d %g %s' % (3, 0.1, 'test')
* os module: os.getcwd() returns the name of the current working directory, os.path.abspath('path_to_file'), os.path.exists('path_to_file'), os.path.isdir('path') or isfile('path'), os.listdir('dir'), os.path.join..
* try: / except:
* pickle module translates almost any type of object into a string (pickle.dumps and pickle.loads
* subprocess module can launch unix cmd in python


#### Classes and object


#### Classes and functions


#### Classes and method


#### Inheritance


#### Case study: Tkinter

