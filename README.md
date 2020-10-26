# XF2 - Explanations in Flora-2

XF2 is a module for use in the Flora-2 (Ergo Lite) logic programming language.
It is designed to create a tree-structured explanation for how a grounded
query is proven in Flora-2.

It uses a meta-programming approach based on a paper
"An explanation shell for expert systems" by Sterling and Lalee.
It is created as part of the Singapore Management University Centre for
Computational Law's research into domain specific programming languages
for legal purposes.

It is written by Jason Morris.

## Usage

You must have Flora-2 installed on your machine and start the Flora-2
interpreter. Then add the xf2 module to your main module using `[+'xf2'].`
at the interpreter (assuming you are in the xf2 directory).

If you want to test xf2 with one of the example rulesets provided, you
can load the example ruleset and xf2 with the command `['module',+'xf2'].`

Then create an object of type xf2Explanation, and set it's goal attribute
to a reified query with no variables.

A reified query is surrounded with `${}`.

For example, if using the `'mortal'` module provided, and the query is
`mortal(Socrates)`, the code would be `e:xf2Explanation[goal->${mortal(Socrates)}].`.

If you are using the `'family'` module provided, and the query is 
`Wednesday[sibling->Pugsley]`, the code would be
`e:xf2Explanation[goal->${Wednesday[sibling->Pugsley}].`.

Then, you can display the explanation by calling `e[display]`.

In these exapmles `e` can be replaced with whatever you want.

## Current Goals

* Generate tree-structured explanations for predicate or frame ground queries
  that use conjunction, disjunction, naf negation, base facts, and boolean truth
  values.