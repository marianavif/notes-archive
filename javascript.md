# Javascript notes

> All expressions in between <> ought to be replaced with expressions following as suggested inside it.

## Glossary

## Basic types

### Built-in basic types

## Operators

- Basic binary arithmetic operators

  - Assignment operator:

	`x = y`

  - Addition: 

	`x + y`

  - Subtraction:

	`x - y`

  - Multiplication:

	`x * y`

  - Division:

	`x / y`

  - Remainder:

	`x % y`

> For a binary arithmetic operator `op`, `x = x op y` can be shortened to `x op= y`.

- Unary arithmetic operators

  - Positive:

	`+ x`

  - Negative:

	`- x`

  - Increment:

	`x++`

  - Decrement:

	`x--`

- String concatenation operator:

	`x + y`

> The `op=` form also applies for this operator.

- Boolean operators:

  - Boolean And (aka conditional And):

	`x && y`

  - Boolean Or (aka conditional Or):

	`x || y`

  - Boolean Not:

	`!x`

- Comparison operators:

  - Equal to: 
  
	`x == y`

  - Not equal to:

	`x != y`

  - Strictly equal to (same type and same value):

	`x === y`

  - Less than:

	`x < y`

  - Less than or equal to:

	`x <= y`

  - Larger than:

	`x > y`

  - Larger than or equal to:

	`x >= y`

- Ternary operator:

	  <boolean-expression> ? <if-true-do-this> : <if-false-do-this>
	
## Comments

### Line comment

To comment a line, start with a `//` and the rest of it is ignored by the compiler.

### Block comment

Block comments can span multiple lines. They start with a `/*` and end with a `*/`, enveloping everything inside.

## Types of command

- **Code block**: list of instructions delimited by `{}`

	  { <commands> }

- **Control flow statements**: conditional and laces commands to determine the execution flow.

  - Condition commands:

    - **if-else**

		Syntax:

			if (<boolean-condition>) <code-block> else if (<boolean-condition2>) <code-block> else <code-blockN>

	- **switch-case-default**
  
		Syntax:

			switch (<variable>) {
				case <variable-value1>:
					<commands-list>
					break
				case <variable-valueN>:
					<commands-list>
					break
				default:
					<commands-list>
			}

  - Repetition commands:

	- **for**

		Syntax:

			for (<inital-expression>;<boolean-expression>;<incremental-expression>) <code-block>
		> The initial expression may initialize a local variable and if so, the reserved word `let` is needed in order to do it.
		
	- **while**

		Syntax:

			while(<boolean-expression>) <code-block>

	- **do-while**

		Syntax:

- **variable**:
  
  - Declare a variable:

		var <variable-name>

  - Declare a variable:
  
		let <variable-name>

  - Declare a variable and assign it a value:

		<variable-name> = <variable-value>

  - Declare a variable and assign it a value:

		let <variable-name> = <variable-value>

- **constant**: a value of a constant cannot change.

  - Declare a constant:

		const <constant-name> = <constant-value>

- **arrays**:

  - Declare an array and assign it to a variable:

		let <variable-name> = new Array(<value1>,<value2>,<valueN>)
	
	> `const` and `var` could be used instead.

  - Access a value from an array:

		<array-name>[<value-index>]

  - Add a value to an existing array:

		<array-name>.push(<value>)

  - Remove values from an existing array:

		<array-name>.splice(<value-index1>,<value-indexN>,<number-of-values-to-be-removed>)

- **function**:

  - Declare a function:
 

## Javascript commands

### Built-in commands

Print a value in terminal:

	console.log(<value>)

> It can be a variable, a constant, the returned value of a function, or a raw value.

> Separating variables with a comma will add a space in between its values.

> To format a text in `console.log()`, one can write a text in between ` `` ` and add variable values inside the brackets in `${}`, e.g.
> 
> 	  console.log(`<text> ${<variable-name>} <text>`)

Convert a value to integer type:

	parseInt(<value-to-be-converted>)

Convert a value to float type:

	parseFloat(<value-to-be-converted>)