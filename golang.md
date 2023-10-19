# Go notes

> All expressions in between <> ought to be replaced with expressionas following as suggested inside it.

> source: mostly, go101.org

## Glossary

***code elements***: named functions, named values (including variables and named constants), defined types and type alias.

***exported identifiers***: an identifier starting with an Unicode uppercase letter. Public identifiers.

***identifiers***: a token which must be composed of Unicode letters, Unicode digits and `_` (underscore), and start with either an Unicode letter or `_`. Names of code elements, package names and package import names must be identifiers.

> Keywords cannot be used as identifiers.

***keywords***: reserved words to prevent them from being used as identifiers.

***non-exported***: identifiers which don't start with an Unicode uppercase letter.Private identifiers. Also called `unexported`.

***unexported identifiers***: identifiers which don't start with an Unicode uppercase letter.Private identifiers. Also called `non-exported`.

<br>

### Identifiers

An identifier is 

### Keywords

***break***: used to break a loop (get out of the loop code block).

***case***: used to specify the code ran if the statement corresponds to the specified case, in a `switch` code block. 

***chan***:

***const***: used to declare constants.

***continue***: used to reinitialize the loop code block.

***default***: used to specify the default code ran by a `switch` code block.

***defer***:

***else***: used to form an else code block. Used only if following an `if` code block.

***fallthrough***:

***for***: used to form a loop code block.

***func***: used to form a `function` code block.

***go***:

***goto***:

***if***: used to form an `if` code block.

***import***: used to specify which packages need to be imported for the code to use them.

***interface***:

***map***:

***package***: used to specify the package name to which the code belongs.

***range***:

***return***: used to return values in functions.

***select***:

***struct***:

***switch***: used to form a `switch` code block.

***type***: used to define custom types of values for the built-in `boolean` and `string` types.

***var***: used to declare variables.

<br>

## Basic types and Basic Value Literals




## Line Break Rules

Coding style cannot be arbitrary.

Go uses a pair of braces (`{` and `}`) to form an explicit code block. One should not put the starting curly brace (`{`) of any explicit code block on a new line. 

> There are some exceptions for this, for example, the bare `for` loop block, which compiles ok.

The formal grammar uses semicolons `;` as terminators in a number of productions. Go programs may omit most of these semicolons using the following two rules:

1. When the input is broken into tokens, a semicolon is automatically inserted into the token stream immediately after a line's final token if that token is
 - an identifier
 - an integer, floating-point, imaginary, rune, or string literal
 - one of the keywords `break`, `continue`, `fallthrough`, or `return`
 - one of the operators and punctuation `++`, `--`, `)`, `]`, or `}`

2. To allow complex statements to occupy a single line, a semicolon may be omitted before a closing `)` or `}`.

Compilers will not automatically insert semicolons for any other scenarios: one must insert the semicolons manually as needed for other scenarios.

One consequence of the semicolon insertion rules is that the self increment and self decrement operations must appear as statements (they can't be used as expressions).

Another consequence of the semicolon insertion rules is one can't break a line before the dot `.`.

In some syntax forms containing multiple alike items, commas are used as separators, such as composite literals, function argument lists, function parameter lists and function result lists. In such a syntax form, the last item can always be followed by a comma. If the following comma is the *last effective character in its respective code line*, then the comma is **required**, otherwise, it is optional. Compilers will not insert commas automatically for any cases. 