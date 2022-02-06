Cleveland State University
CIS 524: Comparative Programming Languages
Spring 2022, Due date: 09 February 2022

Consider the following grammar for a simple programming language called TinyPL:


Following the method outlined in class, write an object-oriented top-down parser in Java that translates every TinyPL program into a sequence of byte-codes for the Java Virtual Machine.
Part 1: Assume:
1. that the rules for program, function, pars, funcall, and exprlist are deleted from the grammar;
2. that the rule for stmt does not include the case for return on its RHS and, similarly, the rule for factor does not include funcall on its RHS; and
3. body is the start symbol of the grammar and the rule for body has the keyword end on the RHS at the end of the rule.
   Program Structure
1. There should be one Java class definition for each nonterminal of the grammar. Place the code for the top-down procedure in the class constructor.
2. There should be a top-level driver class called Parser as well as a class called Code, for code generation, and a class SymTab, for the symbol table.
3. The code for the lexical analyzer (classes Lexer, Token, and Buffer) will be given to you in their entirely – do not modify them.
   Assumptions
1. All input test cases will be syntactically correct; syntax error-checking is not necessary.
2. Optimizations are not required: For programs in the TinyPL fragment, the Java compiler would perform two types of optimizations, both of which are not required for this assignment:
   a. Expressions such as 3 + (15 - 2 * 3) will be simplified by the Java compiler to an integer value, namely, 12. This is part of a more general process called "constant folding" and this is typically done in the (machine-independent) optimization phase.
   b. When there is a chain of goto's in the generated byte-codes, each one transferring control to the next, the Java compiler will optimize them by generating "goto x", where x is the location of the final destination.