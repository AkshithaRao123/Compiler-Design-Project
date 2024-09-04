# Compiler-Design-Project

### PROBLEM STATEMENT 
In our CD project we are designing a Lexer and SLR Compiler for hypothetical language for the following question.  
int main()
begin 
int n; 
do 
  expr=expr+expr; 
  n=exp; 
while(exp) 
return(n) 
end 

### OBJECTIVES 
The objectives of this project are as follows: 
(i) Building a Lexer which takes input file and performs lexical analysis and generates  tokens from the file. 
(ii) The tokens generated from the Lexer are given as input the SLR Parser which  parses the input.

### IMPLEMENTATION  
An efficient bottom-up syntax analysis technique that can be used to parse large classes of context free grammar is called LR(0) parsing. 
L stands for the left to right scanning
R stands for rightmost  derivation in reverse
0 stands for no. of input symbols of lookahead

SLR is simple LR. It is the smallest class of grammar having few number of states. SLR is very easy to construct and is similar to LR parsing. The only difference between SLR parser and LR(0) parser is that in  LR(0) parsing table, there’s a chance of ‘shift reduce’ conflict because we are entering ‘reduce’ corresponding to all terminal states. We can solve this problem by entering ‘reduce’ corresponding  to the FOLLOW of LHS of production in the terminating state. This is called SLR(1) collection of items.

##### Grammar used:
r1 : "S -> FORMAT",
r2 : "FORMAT -> TYPE MAIN BEGIN CONTENT END",
r3 : "TYPE -> 'int'",
r4 : "TYPE -> 'float'",
r5 : "CONTENT -> TYPE id ';' DO WHILE RETURN",
r6 : "DO WHILE -> 'do' OPERATION 'while' '(' EXP ')'",
r7 : "OPERATION -> id '=' VAR '+' VAR ';' id '=' VAR ';'",
r8 : "EXP -> 'exp'",
r9 : "EXP -> id RELOP id",
r10 : "RETURN -> 'return' '(' VAR ')'",
r11 : "VAR -> id",
r12 : "VAR -> num"

### CONCLUSION 
The lexical analyser takes the file with the code as input and returns the tokens accordingly. We have used the SLR bottom-up parsing approach in which we first construct  the closure states for the given grammar thus producing the required Parsing table.  
The grammar is used to parse the statement. If the string is parsed completely, then the output will be Accept.
