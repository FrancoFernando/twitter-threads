Parsing and evaluating arithmetic expressions is basic functionality of any computer.

This is how the algorithm works: {1/6} ↓

Arithmetic expressions can be represented by 3 different notations:

- infix: (a+(b*c))
- prefix: +a*bc
- postfix: abc*+

Humans usually use the infix notation, avoiding  ambiguities with parentheses.

{2/6}

But prefix and postfix expressions have an advantage.

They don't need parentheses or precedence rules.

The order in which the operations are performed depends only on the position of the operators and operands.

{3/6}

Infix arithmetic expressions are usually evaluated in 2 steps:

- convert the expression to postfix notation
- evaluate the postfix expression

The stack data structure is the more suitable to accomplish both tasks.

{4/6}

1. Infix to postfix conversion

The algorithm iterates through each token t of the expression.

1. if t is an operand, it's added to the output
2. if t is an operator, it's pushed to a stack
3. if t is ')', an operator is popped from the stack and added to the output

{5/6}

2. Postfix evaluation

The algorithm iterates through each token t of the expression.

1) if t is an operand, it's pushed to a stack
2) if t is an operator, 2 operands are popped from the stack, applying the operator to them. The result is pushed to the stack.

{6/6}



