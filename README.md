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


For example, inputs from our sample example
 
 lst1 = [ " if " , [ " and " , [ " p1 " ] , [ " not " , [ " p2 " ]] ] , [ " p3 " ]]
 
 lst2 = [ " iff " , [ " p1 " ] , [ " or " , [ " p2 " ] , [ " not " , [ " p3 " ]]]]
 
 print ( format_prop ( lst1 ) )

 print ( format_prop ( lst2 ) )

produce the following strings:

((p1 and (not p2)) -> p3)

(p1 <-> (p2 or (not p3)))

The list of valid operators is
 [ " or " , " and " , " if " , " iff " , " not " , " xor " ]

Part B: Evaluate Prop
Given a proposition p over atomic propositions p1, p2, · · · , pn, n ≤ 9, and a truth value assigned to each
atomic proposition, evaluate whether p is true or false under this assignment. 

Assume that the values of atomic propositions are given as a Python list of length n where
each element is 0 or 1. For example if we have p1 = 0, p2 = 1, p3 = 0 the corresponding list is:

 values = [0 , 1 , 0]
 
Your python function eval prop should take 2 arguments prop, a proposition in the list representation,
and values, values of atomic propositions. It should return 0 for False and 1 for True (not the Boolean
value itself).
