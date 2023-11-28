# Go notes

> All expressions in between <> ought to be replaced with expressionas following as suggested inside it.

> source: mostly, go101.org

## Glossary

***code elements***: named functions, named values (including variables and named constants), defined types and type alias.

***function closure***: function value that references variables from outside its body. The function may access and assign to the referenced variables; in this sense the function is "bound" to the variables. 

***exported identifiers***: an identifier starting with an Unicode uppercase letter. Public identifiers.

***identifiers***: a token which must be composed of Unicode letters, Unicode digits and `_` (underscore), and start with either an Unicode letter or `_`. Names of code elements, package names and package import names must be identifiers.

***variadic***: a variadic function is a function that receives an indeterminated number of parameters.

> Keywords cannot be used as identifiers.

***keywords***: reserved words to prevent them from being used as identifiers.

***literal***: a literal of a value is a text representation of the value in code.

***non-exported***: identifiers which don't start with an Unicode uppercase letter.Private identifiers. Also called `unexported`.

***unexported identifiers***: identifiers which don't start with an Unicode uppercase letter.Private identifiers. Also called `non-exported`.


### Identifiers

Identifiers name program entities such as variables and types. An identifier is a sequence of one or more letters and digits. The first character in an identifier must be a letter.

#### Blank identifier

The blank identifier is represented by the underscore character `_`. It serves as an anonymous placeholder instead of a regular (non-blank) identifier and has special meaning in declarations, as an operand, and in assignment statements.

#### Predeclared identifiers

The following identifiers are implicitly declared in the universe block:

    Types:
            any bool byte comparable
            complex64 complex128 error float32 float64
            int int8 int16 int32 int64 rune string
            uint uint8 uint16 uint32 uint64 uintptr
    Constants:
            true false iota
    Zero value:
            nil
    Functions:
            append cap clear close complex copy delete imag len
            make max min new panic print println real recover

#### Exported identifiers

An identifier may be exported to permit access to it from another package. An identifier is exported if both:

1. the first character of the identifier's name is a Unicode uppercase letter;
2. the identifier is declared in the package block or it is a field name or method name.

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

## Basic types and Basic Value Literals

### Built-in basic types

- **Boolean**:

  - `bool`;
  > There are only two possible boolean values in memory and they are denoted by the two predeclared named constants: `false` and `true`.
  
  > Zero value: *`false`*

- **Integer**:
  
  - **signed** types:

    - **sized** types: `int8`, `int16`, `int32`, `int64`;
    - **unsized** types: `int` (usually 32 bits wide on 32-bit systems and 64 bits wide on 64-bit systems);

  - **unsigned** types (always non-negative values):

    - **sized** types: `uint8`, `uint16`, `uint32`, `uint64`;
    - **unsized** types: `uint`, `uintptr` (both usually 32 bits wide on 32-bit systems and 64 bits wide on 64-bit systems);
        > `uintptr` is an integer type large enough to contain the bit pattern of any pointer.
  > Zero value: *`0`*   

- **Floating-point**:

  - `float32`, `float64`;
  > Zero value: *`0`*

- **Complex**:

  - `complex64`, `complex128`;
  > Zero value: *`0`*

- **String**:

  - `string`.
  > Zero value: `""` or `` `` ``

#### Built-in type alias

- `byte` is a built-in alias of `uint8`. One can view `byte` and `uint8` as the same type;
- `rune` is a built-in alias of `int32`. One can view `rune` and `int32` as the same type.

### Custom types

One can define custom types for the built-in types.

> Syntax:

    type <custom-type-name> <built-in-type-name>

One can declare custom type alias.

> Syntax:

    type <alias-name> = <built-in-type-name>

### Basic Value Literals

- **Boolean value literals**:

    Go specification doesn't define boolean literals.

- **Integer value literals**:

    - Decimal form (base 10):
      
      Starts with a `0x` or `0X`.

    - Octal form (base 8):

      Starts with a `0`, `0o` or `0O`.

    - Hex form (base 16):

      Starts with a `0b` or `0B`.

    - Binary form (base 2):

      Starts without a `0`.

- **Floating-point value literals**:

    - Decimal literal (base 10):

      May contain a decimal integer part, a decimal point, a decimal fractional part, and an integer exponent part (10-based). Such an integer exponent part starts with a letter `e` or `E` and suffixes with a decimal integer literal (`xEn` is equivalent to `x` is multiplied by `10^n`, and `xE-n` is equivalent to `x` is divided by `10^-n`).

    - Hex literal (base 16):
      
    A hexadecimal floating point literal must end with 2-based exponent part, which starts with a letter `p` or `P` and suffixes with a decimal integer literal (`yPn` is equivalent to `y` is multiplied by `2^n`, and `yP-n` is equivalent to `y` is divided by `2^n`).
    
    Same as hex integer literals, a hexadecimal floating point literal also must start with `0x` or `0X`. Different from hex integer literals, a hexadecimal floating point literal may contain a decimal point and a decimal fractional part.

- **Imaginary value literals**:

    Consists of a floating-point or integer literal and a lower case letter `i`.
    
    Imaginary literals are used to represent the imaginary parts of complex values.

- **Rune value literals**:

     Rune types, including custom defined rune types and the built-in `rune` type (a.k.a., `int32` type), are special integer types, so all rune values can be denoted by the integer literals introduced above. On the other hand, many values of all kinds of integer types can also be represented by rune literals introduced below in the current subsection.

    A rune value is intended to store a Unicode code point. Generally, we can view a code point as a Unicode character, but we should know that some Unicode characters are composed of more than one code points each.

    A rune literal is expressed as one or more characters enclosed in a pair of quotes. The enclosed characters denote one Unicode code point value. There are some minor variants of the rune literal form. The most popular form of rune literals is just to enclose the characters denoted by rune values between two single quotes.

    For example, the following rune literal variants are equivalent to `'a'`(the Unicode value of character `a` is 97):

        // 141 is the octal representation of decimal number 97.
        '\141'
        // 61 is the hex representation of decimal number 97.
        '\x61'
        '\u0061'
        '\U00000061'
    
    Please note, `\` must be followed by exactly three octal digits to represent a byte value, `\x` must be followed by exactly two hex digits to represent a byte value, `\u` must be followed by exactly four hex digits to represent a rune value, and `\U` must be followed by exactly eight hex digits to represent a rune value. Each such octal or hex digit sequence must represent a legal Unicode code point, otherwise, it fails to compile.

    If a rune literal is composed by two characters (not including the two quotes), the first one is the character `\` and the second one is not a digital character, `x`, `u` and `U`, then the two successive characters will be escaped as one special character. The possible character pairs to be escaped are:

        \a   (Unicode value 0x07) alert or bell
        \b   (Unicode value 0x08) backspace
        \f   (Unicode value 0x0C) form feed
        \n   (Unicode value 0x0A) line feed or newline
        \r   (Unicode value 0x0D) carriage return
        \t   (Unicode value 0x09) horizontal tab
        \v   (Unicode value 0x0b) vertical tab
        \\   (Unicode value 0x5c) backslash
        \'   (Unicode value 0x27) single quote

    They are occasionally used in interpreted string literals.

- **String value literals**:

    String value literals in Go are UTF-8 encoded.

    - Double quotes `" "` form: interpreted string literal. Each `\n` character pair will be escaped as one newline character, and each `\"` character pair will be escaped as one double quote character;
    - Back quotes `` ` ` ``  form: raw string literal. No character sequences will be escaped. The back quote character is not allowed to appear in it.

#### Underscore `_` in numeric literals for better readability

Underscores `_` can appear in integer, floating-point and imaginary literals as digit separators to enhance code readability. But please note, in a numeric literal,

- any `_` is not allowed to be used as the first or the last character of the literal;
- the two sides of any `_` must be either literal prefixes (such as `0X`) or legal digit characters.

## Operators

- Basic binary arithmetic operators:

  The two operands must be both values of the same basic numeric type.

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

  The two operands must be both values of the same basic integer type.

  - Remainder:

    `x % y`

- Bitwise binary arithmetic operators (base 2):

  The two operands must be both values of the same integer type.

  - Bitwise and:

    `x & y`

    `1100 & 1010` results in `1000`.

  - Bitwise or:

    `x | y`

    `1100 | 1010` results in `1110`.

  - Bitwise xor:

    `x ^ y`

    `1100 ^ 1010` results in `0110`.

  - Bitwise clear:

    `x &^ y`

    `1100 &^ 1010` results in `0100`.

  The left operand must be an integer and the right operand must be also an integer (if it is a constant, then it must be non-negative), their types are not required to be identical. A negative right operand (must be a non-constant) will cause a panic at run time.

  - Bitwise left shift:

    `x << y`

    `1100 << 3` results in `11000000`.

  - Bitwise right shift:

    `x >> y`

    `1100 >> 3` results in `1`.
    In a bitwise-right-shift operation, all the freed-up bits at left are filled with the sign bit (the highest bit) of the left operand. For example, if the left operand is an `int8` value `-128`, or `10000000` in the binary literal form, then `10000000 >> 2` results in `11100000`, aka, `-32`.

For a binary arithmetic operator `op`, `x = x op y` can be shortened to `x op= y`. In the short form, `x` will be only evaluated once.

- Unary arithmetic operators:

  - Positive:

    `+ x`
  
  - Negative:

    `- x`
  
  - Bitwise complement (bitwise not):

    `^x`
    Equivalent to `y^x`, where `y` is a value all of which bits are 1.

  Operations using the increment and decrement operators don't return any results, so such operations cannot be used as expressions. The operator must follow the operand.

  - Increment:

    `x++`
  
  - Decrement:

    `x--`

- String concatenation operator:

  Both operands must be values of the same string type.

  `x + y`

  The `op=` form also applies for this operator.

- Boolean operators:

  The two operands must be both values of the same boolean type.

  - Boolean and (aka conditional and):

    `x && y`

  - Boolean or (aka conditional or):

    `x || y`
  
  - Boolean not:

    `!x`
  
- Comparison operators:

  Generally, the types of its two operands must be the same.

  - Equal to:

    `x == y`
  
  - Not equal to:

    `x != y`
  
  The two operands must be both values of the same integer type, floating-point type or string type.

  - Less than:
  
    `x < y`
  
  - Less than or equal to:

    `x <= y`
  
  - Larger than:

    `x > y`
  
  - Larger than or equal to:
  
    `x >= y`
  
- Pointer related operators:

  - Dereference a pointer value:

    `*p`
  
  - Take the address of an addressable value:
  
    `&p`

#### Operator Precedence

    1 | *   /   %   <<  >>  &   &^
    2 | +   -   |   ^
    3 | ==  !=  <   <=  >   >=
    4 | &&
    5 | ||

## Verbs

`%v` prints an instance of a struct.

`%+v` prints an instance of a struct, including the struct's field names.

`%#v` prints a Go syntax representation of the value.

`%T` prints the type of a value.

`%t` prints bool types.

`%d` prints standard, 10-based integers.

`%b` prints a binary representation of an integer.

`%c` prints the character corresponding to the given integer.

`%x` provides hex encoding.

`%f` prints basic decimal floating-points.

`%e` and `%E` format the float in scientific notation.

`%s` prints basic string.

`%q` double-quotes strings as in Go source.

When formatting numbers one will often want to control the width and precision of the resulting figure. To specify the width of an integer, use a number after the % in the verb. By default the result will be right-justified and padded with spaces.

One can also specify the width of printed floats, though usually one will also want to restric the decimal precision at the same time with the width.precision syntax.

To left-justifiy, use the `-` flag.

One may also want to control width when formatting strings, especially to ensure that they align in table-like output. For basic right-justified width, use a number after the % in the verb. To left-justify, use the `-` flag as with numbers.

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

## Comments

### Line comments

To comment a line, start with a `//` and the rest of it is ignored by the compiler.

### Block comments

Block comments can span multiple lines. They start with a `/*` and end with a `*/`, enveloping everything inside.

## Documentation

Go includes a program `go doc` for extracting and viewing documentation from `.go` files. For information about a package, use:

    go doc <package-name>

For information about a package function, use:

    go doc <package-name>.<package-function-name>

## Types of commands

- **Code block**: list of instructions delimited by `{}`.

      { <commands> }

  > Go does not accept code blocks alone in a line (beginning with a bracket `{` )

- **Control flow statements**: conditional and laces commands to determine the execution flow.

  - Conditional commands:
    
    - **if-else**

         Syntax:

          if <boolean-condition1> <code-block1> else if <boolean-condition2> <code-block2> else <code-blockN>

    - **switch-case-default**

        Syntax:

          switch <variable/statement> {
          case <variable-value1>:
            <commands-list>
          case <variable-valueN>:
            <commands-list>
          default:
            <commands-list>
          } 

  - Repetition commands:

    - **for**
      
      Syntax:

        - forever loop

              for <code-block>

        - conditional loop

              for <initial-expression>; <boolean-expression>; <incremental-expression> <code-block>

        - iterate over a slice or map

              for <index-variable>, <value-variable> := range <slice-name> <code-block>

          > When ranging over a slice, two values are returned for each iteration. The first is the index, and the second is a copy of the element at that index. One can skip the index or value by assigning to the blank identifier `_`. If one only wants the index, one can omit the second variable.

- **variable**: 
  > Variable names follow the CamelCase convention.
  - Declare a zero-valued variable:

        var <variable-name> <variable-type>

  - Declare a non-zero-valued variable:

        var <variable-name> <variable-type> = <variable-value>

  - Declare a non-zero-valued variable (shortened) with type inference:

        <variable-name> := <variable-value>

    > Go infers the variable type from the value one assigns to it. If one assigns an integer to a variable, Go will infer it as an `int` type (32-bit integer in 32-bit systems and 64-bit integer in 64-bit systems). If one assigns a float or a complex to a variable, Go will infer it as the largest type, i.e. `float64` and `complex128`.

  - Declare multiple non-zero-valued variables (shortened) with type inference:

        <variable-name1>, <variable-nameN> := <variable-value1>, <variable-valueN>

- **constant**: a value of a constant cannot change.

  - Declare a constant:

        const <constant-name> <constant-type> = <constant-value>

- **arrays**: fixed-sized set of values of the same type.

  - Declare an empty array:

        var <array-name> [<array-length(integer)>]<array-type>
    
    > An empty array has zero-values in each of its entry.

  - Declare an array specifying its values:

        var <array-name> [<array-length(integer)>]<array-type> = {<value1>,<valueN>}
  
  - Declare an array specifying its values (shortened):

        <array-name> := [<array-length(integer)>]<array-type>{<value1>,<valueN>}

- **slices**: abstract set of values which is of dinamic size and is based on an existing array, empty (default) or not.

  > A slice does not store any data, it just describes a section of an underlying array. Changing the elements of a slice modifies the corresponding elements of its underlying array. Other slices that share the same underlying array will see those changes. 

  > A slice has both a length and a capacity. The length of a slice is the number of elements it contains. The capacity of a slice is the number of elements in the underlying array, counting from the first element in the slice. 

  - Declare an slice from an empty (default) array:

        <slice-name> := make([]<slice-type>, <slice-length(integer)>, <slice-capacity(integer)>)

  - Declare an slice from an empty (default) array specifying its values:

        <slice-name> := []<slice-type>{<value1>,<valueN>}

  - Declare an slice from an existing array:

        var <slice-name> []<slice-type> = <existing-array-name>[<lowest>:<highest-value>]
    
    > This selects a half-open range which includes the first element (lowest) but excludes the last one (highest).

- **struct**: set of variable or constants which characterize a type.

  - Declare a new struct type:

        type <struct-type-name> struct {
          <variable-name1> <variable-type1>
          <variable-nameN> <variable-typeN>
        }
  
  - Declare an struct and assign it to a variable (extended):

        var <variable-name> <struct-type-name>  = {<variable-name1>: <variable-value1>,<variable-nameN>: <variable-valueN>}
  
  - Declare an struct and assign it to a variable:

        var <variable-name> <struct-type-name> = {<variable-value1>,<variable-valueN>}
  
  - Declare an struct and assign it to a variable (shortened):

        <variable-name> := <struct-type-name>{<variable-value1>,<variable-valueN>}

  - Declare an struct using `new` operator, assigning it to a pointer variable:

        <variable-name> = new(<struct-type-name>)

    > This variable must be a pointer. To get the value in the address of the pointer, one must refer to the variable using `*<variable-name>`.

- **function**: set of commands to be executed when the function is called. May need arguments (parameters) and may return a value.

  - Declare a non-returnable and argumentless function:

        func <function-name>() <code-block>

  > The executable part of the code is the non-returnable and argumentless function called `main` inside the package `main`.

  > There must not be a breakline in between the function name and the block's opening bracket.

  - Declare a single-valued returnable function:

        func <function-name> (<argument1> <argument-type1>, <argumentN> <argument-typeN>) <returned-value-type> <code-block>

  - Declare a multiple-valued returnable function:
  
        func <function-name> (<argument1> <argument-type1>, <argumentN> <argument-typeN>) (<returned-value-type1>, <returned-value-typeN>) <code-block> 

  - Declare a variadic function:

        func <function-name> (<argument> ...<argument-type>) (<returned-value-type1>, <returned-value-typeN>) <code-block>

- **interface**: set of methods common to one or more types.

  - Declare an interface type:

        type <interface-name> interface {
          <method1> <method-type1>
          <methodN> <method-typeN>
          }

- **package**: directory of `.go` files.

  - Declare a package:

        package <package-name>

    > If the package declaration is `package main`, then the program will be compiled into an executable.

  - Import a local package:

        import "<package-name>"

    > One can assign an alias to the imported package, which will be used to call functions instead of the name of the package itself.
    >
    >     import <alias> "<package-name>"

  - Import an external package:

        import "<path-to-the-external-package>"

  - Import multiple packages:

        import (<insert-packages-separated-by-linebreak>)

## Compiling and running a code in Go

> The path to the code file is explicited when one's not working in the folder where the file is located.

Compile a code in terminal and create an executable file:

    go build <path-to-code-file>/<code-file-name>.go

Compile and run a code in terminal, without creating an executable file:

    go run <path-to-code-file>/<code-file-name>.go

## Go commands

### Commands from built-in packages

Return the length of an array or slice:

      len(<array/slice-name>)

Return the capacity of a slice:

      cap(<slice-name>)

Append new elements to a slice:

     <slice-name> = append(<slice-name>,<value-to-append1>,<value-to-appendN>) 

### Packages

#### bufio package

Start file to read:

    bufio.NewReader(<file-name>)

  > The file must be opened before this command. One can open it using os package function Open.

Return string read until specified character delimiter:

    bufio.ReadString(<character-delimiter>)

  > Also returns an error status.

  > Characters use single quotes `''`.

#### fmt package

Concatenate data and return it in a string:

    fmt.Sprint(<value1>,<valueN>)

Concatenate data and return it in a string, adding a space in between arguments:

    fmt.Sprintln(<value1>,<valueN>)

Interpolate strings or leave placeholders in a string, using values to fill them in, then return the string:

    fmt.Sprintf("%v",<variable-name>)

Concatenate strings in `fmt.Print` and `fmt.Println` functions:

    fmt.Print(<string1>, <string2>)
    fmt.Println(<string1>,<string2>)
 
  > Concatenating strings with a comma in Print and Println are different things. `Println` function formats the data including a space in between each argument and adding a line break at the end. `Print` function does not format its data and adds no line break at the end.

Interpolate strings or leave placeholders in a string, using values to fill them in, then print in terminal:

    fmt.Printf("%v",<variable-name>)
  
  > `%v` gets the value from the following argument. One can add multiple placeholders, the verbs will get the value from the arguments in the order they are written.

Read a value from the keyboard and assign it to a variable (only assigns values of the same type as the specified variable):

    fmt.Scan(&<variable>)

  > It only reads the value before the first space.

Read and format a value from the keyboard and assign it to a variable:

    fmt.Scanf("%v", &<variable>)

#### io package

End of file error:

    io.EOF

#### net package

##### http package

Return a response and an error status from a web address:

    http.Get(<web-address>)

Get status code from an HTTP response:

    <response>.StatusCode

#### os package

Return opened file:

    os.Open(<file-path>)

Close opened file f:

    f.Close()

Exit the program with success status:

    os.Exit(0)

Exit the program with failure status:

    os.Exit(-1)

#### reflect package

Return the type name of a variable:

    reflect.TypeOf(<variable-name>)

#### strings package

Return a slice of the string s, with all leading and trailing white space removed:

    strings.TrimSpace(s)

#### time package

Wait for a moment before executing next steps:

    time.Sleep(d Duration)