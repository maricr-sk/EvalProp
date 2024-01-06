# EvalProp
Takes an input in postfix order and rewrites it using discrete math operators and puts it into infix notation. Also creates a RPN calculator to evaluate the logic expression and return true or false.

Directions: 

Part A: Format Prop
One way to represent a compound proposition in Python is to use lists as follows: the first element is a
logical connective, and the remaining elements (up to two) will be the atomic propositions in the compound
proposition.

For example:

 ¬p1 will be represented with the list

 [ " not " , [ " p1 " ]]
 
 p1 =⇒ p2 will be represented with the list
 
 [ " if " , [ " p1 " ] , [ " p2 " ]]
 
 p1 ∧ ¬p2 =⇒ p3 will be represented with the list

 [ " if " , [ " and " , [ " p1 " ] , [ " not " , [ " p2 " ]] ] , [ " p3 " ]

Write a python function format prop that allows to print a proposition in Propositional Logic using the
indicated list representation. Consider the connectives: ∨, ∧, =⇒ , ⇐⇒ , ¬. and ⊕ (XOR). In the code,
they will be written, respectively, as: or, and, if, iff, not, xor.

You may safely assume that we consider only the unary operator as not and binary operations: functions
that take only two inputs.

For example, such list will be a valid input:

 [ " or " , [ " p1 " ] , [ " p2 " ]]

List with more variables is an invalid input:

 [ " or " , [ " p1 " ] , [ " p2 " ] , [ " p3 " ]]
 
Your python function format prop should take one argument prop, which may be a (possibly nested)
list of lists (of strings), as above. It should return a formatted string corresponding to the desired compound
proposition. Assume all inputs are valid.


For example, inputs from our sample example
 
 lst1 = [ " if " , [ " and " , [ " p1 " ] , [ " not " , [ " p2 " ]] ] , [ " p3 " ]]
 
 lst2 = [ " iff " , [ " p1 " ] , [ " or " , [ " p2 " ] , [ " not " , [ " p3 " ]]]]
 
 print ( format_prop ( lst1 ) )

 print ( format_prop ( lst2 ) )

produce the following strings:

((p1 and (not p2)) -> p3)

(p1 <-> (p2 or (not p3)))

You may assume that atomic propositions are in the format of p[1-9], meaning that they have a prefix p
and one digit from 1 to 9, or a string true or false. The list of valid operators is
 [ " or " , " and " , " if " , " iff " , " not " , " xor " ]
You may wrap all strings in parentheses even if they are not required.

Part B: Evaluate Prop
Given a proposition p over atomic propositions p1, p2, · · · , pn, n ≤ 9, and a truth value assigned to each
atomic proposition, evaluate whether p is true or false under this assignment. The proposition will be given
to you in the same form as Part A.

Assume that the values of atomic propositions are given as a Python list of length n where
each element is 0 or 1. For example if we have p1 = 0, p2 = 1, p3 = 0 the corresponding list is:
 values = [0 , 1 , 0]
 
Your python function eval prop should take 2 arguments prop, a proposition in the list representation,
and values, values of atomic propositions. It should return 0 for False and 1 for True (not the Boolean
value itself).
