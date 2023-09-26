# Java Notes

***

> All expressions in between <> ought to be replaced with expressions following as suggested inside it.

## Glossary

<br>

***abstrat class***: similar to a common class, it allows some (or all) of its methods to be only declared, not defined. A class which inherits from an abstract class must define all of the abstract methods. An abstract class cannot instantiate objects and it must be extended.

***attribute***: characteristics of a class which distinguish its objects.

***static attributes***: constant valued attributes which can be shared with all instances of a class.

***bytecode***: **.java** extension program compiled to **.class** extension, which is interpreted by *Java Virtual Machine (JVM)*. *JVM* runs the same bytecode on different platforms (operational systems).

***casting***: converting a data type into another data type that isn't compatible to the original one. Casting can only be validated during program execution.

***class***: comportamental pattern of known objects. A class has attributes and methods.

> When a class is created, a new type of object is created.

***class constructor***: a special class method named with the class name which is used to create/initialize an object of the class. It doesn't necessarily receive all or any parameters, it depends on its objective. It can have verifications and/or methods before attributing a parameter to the class attributes. If a constructor is declared in a class, it automatically loses the standard constructor Java creates for it, unless it is declared explicitly. A class can have as many constructors as necessary, by method overloading. When an object of a subclass is initialized, it is interesting to call the super constructor inside the subclass constructor, unless the constructor overwrites the super constructor. If not specified to do it, Java will call the standard super constructor and create a non specific object of the super class.

***encapsulation***: restricting the direct acces to some components of an object, so users cannot access state values for all of the variables of a particular object. Can be used to hide both data members and data functions or methods associated with an instantiated class or object. In object-oriented programming, it refers to the bundling of data, along with the methods that operate on that data, into a single unit.

***inheritance***: basing an object or class upon another object (*prototype-based* inheritance) or class (*class-based* inheritance), retaining similar implementation. **Subclasses** are the new classes derived from existing ones (**super/parent** class) and **inherits** (have the same) attributes and methods from its parent class, unless they're **overriden** in the subclass code. The super class is a *generalization* of the subclasses and the subclasses are *specializations* of the super class. The super and subclasses belong to a **class hierarchy**, the ***inheritance tree***, of arbitrary size. In general, the further down in the hierarchy a class appears, the more specialized its behaviour.

***inheritance forest***: multiple hierarchies connected to each other through different classes, without existing one common-to-all super class.

***inheritance tree***: a single hierarchy comprehends all existent classes, meaning there's one common-to-all super class. It is the adopted model in Java (the common-to-all super class in Java is the *Object* class).

***interface***: declares an empty set of static attributes and public methods, which must be defined in each class that implements the interface.

***late binding***: resource which postpones a method resolution until when it is effectively called; it will resolve in execution time and the method used will be defined by the object *actual* class, though additional processing will be demanded to find out its type and can turn the code less efficient. To avoid late binding, declare constant methods.

***method***: actions done by/on the objects of a class.

***method overloading***: the difference in the parameters type or the number of parameters in each method (or both) allows a class to have more than one method with the same name, and allows these methods to have different signatures. Method overloading cannot be done by changing the return type of methods.

***object***: individual which is characterized by a certain comportamental pattern known as class. Also referred to as instance. Every object inherits from the class *Object*.

***package***: group of related classes, interfaces and other packages, providing access privileges and namespace management. The package name characterizes all of the classes, interfaces and packages it contains. It is implemented as a directory and the belonging classes, interfaces and packages must be in it. Package hierarchy is built through directory hierarchy.
> To declare a file as belonging to a package, the first line must be:

>		package <package-name>

> To use a specific class from a package, you must import it:

>		import <package-name>.<class-name>

> To import all classes from a package, use *:

>		import <package-name>.*

> Classes from the standard package java.lang don't need to be imported.

***package (default) access***: the member acts as public within the package and as private outside the package. Attributes and methods with no access modifier are package access type by default.

***private access***: can only be accessed within the current class.

***protected access***: can only be accessed within the current package or in the *child class* of the outside package.

***public access***: can be accessed indiscriminately within any class.



***polymorphism***: capacity of an object of acquiring multiple forms. It occurs due to inheritance: when a class is extended, it does not lose compatibility with its super class. The opposite is not true though: an object of the super class is not compatible with its subclasses.

### Reserved words in Java

***abstract***: used to declare an abstract class or method.

***extends***: used to create a subclass or subinterface. A Java subclass can extend *only* one class, as it's called **simple inheritance**. All classes implicitly extend the *Object* class. Interfaces can also respond to a hierarchy; a class which implements a subinterface must define all methods from the subinterface, including superinterface ones. Java allows **multiple inheritance** through interface implementation. An interface can extend one or more interfaces.

***final***: used to declare a constant attribute, local variable, method or class (meaning it cannot be overwritten). Final classes cannot be extended.

***implements***: used to implement an interface to a class. A class can implement one or more interfaces.

***private***: used to define an attribute or method as private.

***protected***: used to define an attribute or method as protected.

***public***: used to define an attribute or method as public.

***super***: used in subclasses to call a method or attribute from the parent class identical to it.

***this***: operator used to make it clear that it is referring to the current class attribute or method.
> Syntax:

>	  this.<class-method-or-class-attribute>


<br>

## Java installation

***

1. Download the *Java Development Kit (JDK) corresponding to your operational System.

2. Install it following the instructions (preferably on a simple path such as "**C:\>Java**).

3. Check on the following ambient variables:

        JAVA_HOME = <path-chosen-during-installation>

#### Using Java on command line

1. Save file as **.java** (extension). File must have same name as the class in it.

2. Edit file on preferred text editor.

3. In the same directory as the file, compile the program using terminal:

        javac <file-name>.java

It will generate a **.class** file of same name (bytecode).

4. Run it using terminal:

        java <file-name>

<br>

## Basic operators

- Assignement operator:

  Assigning a value to a variable.
  
      `=`

- Arithmetic operators:

  Valid to integer and floating-point types.

   - Addition:
          `+`
   - Subtraction:
          `-`
   - Division:
          `/`
   - Module:
          `%`

 	- Increment and decrement operators:

   	 Incrementing and decrementing of 1 variable x before assigning it to variable y:
         
   			int x,y;
  			y = ++x;
  			y = --x;

   	 Incrementing and decrementing of 1 variable x after assigning it to variable y:
            
            int x,y;
            y = x++;
            y = x--;

- Relational operators:

  - Equality:
          `=`

  - Inequality:
          `!=`

  - Less than:
          `<`

  - Less than or equal to:
          `<=`

  - Greater than:
          `>`

  - Greater than or equal to:
          `>=`

- Logical operators:

  - Logical **and**: returns true if both statements are true.
          `&&`

  - Logical **or**: returns true if one of the statements is true.
          `||`

  - Logical **not**: returns false if the result is true.
          `!`

- Assignment operators (*same as*):

  - x = y
   
   		 `x = y`

  - x = x+y
       
       `x += y`

  - x = x-y

       `x -= y`

  - x = x*y
        
        `x *= y`

  - x = x/y
        
        `x /= y`

  - x = x%y
        
        `x %= y`

  - x = x&y
        
        `x &= y`

  - x = x|y
        
        `x |= y`

- Bitwise operators:

  - **and**:
        `&`
  - **or**:
        `|`
  - **exclusive or**:
        `^`
  - **not**
       `~`

- Bit shift operators:

  Shifts a bit pattern x, y positions to the left:
          `x << y`

  Shifts a bit pattern x, y positions to the right:
          `x >> y`

  Shifts a bit pattern x, y positions to the right putting zeros in the most significatives bits:
          `x >>> y`

- Ternary operator:

  Equivalent to the if-else command. It consists of three operands and it's used to evaluate Boolean expressions. The operator decides which value will be assigned to the variable.
  
  Syntax:
        
    	variable = (condition) ? expression1 : expression2

  > If the condition returns true, expression1 gets executed, else the expression2 gets executed and the final result is stored in a variable.


![Operator's precedence in Java](https://1.bp.blogspot.com/-SOa-Kwn7Mhs/XfPBNAlW_pI/AAAAAAAAEyg/i0K2hmq6avkAg0aupGhYkp_StMKHJASIwCLcBGAsYHQ/s1600/Screenshot%2B%2528447%2529.png)

<br>

## Primitive (built-in) types of data

***

- Integer:

  - **byte**: 1-byte signal number (from -128 to 127).

  - **short**: 2-byte signal number (from -32768 to 32767).

  - **int**: 4-byte signal number (range of a little more than - 2 billion to a little more than 2 billion).

  - **long**: 8-byte signal number (+/- 9233372036854775807).

- Floating-point:

  - **float**: 4-byte signal number (+/- 3.40282347E+38).

  - **double**: 8-byte signal number (+/- 1.7976931348623E+308).

> #### Converting numeric types
> Numeric type conversion can be done, however information may be lost during the process.
  
>  - Casting

> Cast variable x into a different type and assign it to variable y:
			
>		<type> x;
>	 	<other-type> y;
>		y = (<other-type>) x;
 
>  Different type conversion that can be done without casting:

>        byte -> short -> int -> long -> float -> double 

- Character:

  - **char**: 2-byte UNICODE character. ASCII table and majority of the existent natural languages. Written in single quotation marks ''.

	> String is a built-in class in Java for text type. Written in double quotation marks "".

- Boolean:

  - **boolean**: 1-byte. It can be either true, false or null.


<br>

## Types of commands

- **Code block**: list of instructions delimited by {}.
     
		<code-block> = {<commands-list>}

- **Control flow statements**: conditional and laces commands to determine the execution flow.

  - Conditional commands:

  		- **if-else**
    	
    		> Syntax:
            
			>		if(<condition>) <code-block1> else if <code-block2> else <code-blockN>

 	 - **switch-case-default**
  
  		> Syntax:
       
       >		 switch (<condition>) {
		          case 1:
		            <commands-list>
		            break
		          (...)
		          case N:
		            <commands-list>
		            break
		          default:
		            <commands-list>
		        }
    	
    	> Condition is char or integer (except long) variable. Execution begins in respective case (N corresponding to condition chosen) and ends in next break. Default is optional and corresponds to the situation where to the condition is assigned a value to which there isn't a corresponding case.

  - Repetition commands:

    	- **while**
    
    		> Syntax:
          		
          >		while (<condition>) <code-block>
    		
    		> Only executes the code block if condition is true.

    	- **do-while**
    		
    		> Syntax:
    	
    		>		do code-block while (<condition>)
    		
    		> Executes the code block at least once, even if condition is false.

    	- **for**
    
    		> Syntax:
          
          >		for (<initial-expression>; <boolean-expression>; <incremental-expression>) <code-block>
    		
    		> Initial expression is evaluated once. Boolean expression is evaluated, executes the code if true, incremental expression is then executed; else, stops. After incrementing, boolean expression is evaluated again.

  - Unconditional branch command:

    	- **break**
    
    		> When executed in a lace, it finishes its execution.

  - Method exit command:

    	- **return**
    
    		> Finishes the method execution and returns the specified result.

<br>

## Java commands

***

### Creating classes and instantiating objects

Create a class:

    <(public/private)> class <class-name> {}

Create the executing method in which the program will run:

    public static void main (String args[]) {}

Initialize an empty variable or an attribute:

    <variable/attribute-type> <variable/attribute-name>;

Initialize a variable or an attribute with specific value:

    <variable/attribute-type> <variable/attribute-name> = <value>;

Create simple class constructor without parameters (standard constructor):

    <class-name>(){
      attribute1 = <value>;
      (...)
      attributeN = <value>;
    }

Create simple class constructor with parameters:

    <class-name>(parameter1,...,parameterN){
      attribute1 = parameter1;
      (...)
      attributeN = parameterN;
    }

Instantiate an object (**new** operator):

    new <class-constructor>(<possible-parameters>);

> The object type is the name of the class which instantiates it.

Assign an instance to a new variable:

    <object-type> <variable-name> = new <class-constructor>(<possible-paramaters);

> Since JAVA 10, it is possible to create a variable without specifying its type twice in the same line (as seen above). It can be done as following:

>      var <variable-name> = new <object-type>(<possible-paramaters>);

Refer to specific public attribute of object:

    <variable-which-contains-the-object>.<attribute-name>



#### Arrays

> Array is a built-in class in Java. It can have multiple elements of a same type.

Declare an empty array of length x:

    <type> <array-name>[] = new <type>[x];

Initialize an array:

    <type> <array-name> = new <type>[]{<elements-separated-by-comma>};

> While instantiating the array, it's not needed to specify its type:

>      <type> <array-name>[] = {<elements-separated-by-comma>};



### Printing in terminal

Output in terminal (with automatic line break):

  - Specific string/character:
    
        System.out.println("<sentence/character-to-print-out>");

  - Numeric/boolean data:
    
        System.out.println(<numeric/boolean-data>);

  - Variables:
    
        System.out.println(<variable-name>);

Formatted output in terminal (without automatic line break):

	System.out.printf("<sentence-to-format>",<arguments>);
	
> It follows the rules of String formatting using String.format().



### *Object* class methods

#### Boolean

Verify object actual type:

	<object-name> instanceof <type(class)-name>

#### String

Return a description of the object:

	<object-name>.toString();
	
#### Void

Destroy an object:

	<object-name>.finalize();


### *String* class methods

#### String

Format a String:

  - Syntax:
  
        String.format("<sentence-to-format>",<arguments>);

  - Format Rules:
  
        %[flags][width][.precision]conversion-character

  - Line separator:
  
        %n

  - Conversion characters:

    - *s* formats lowercase strings. *S* formats uppercase strings.

		> To specify a minimum length, specify the flag width. To left-justify the string, use the - flag. To limit the number of characters in the output, specify a precision with the syntax:
		
		>	   %x.ys
		
		> Where the first number x is the padding and y is the number of chars.

    - *c* formats lowercase char. *C* formats uppercase char. The result is a Unicode character.

    - *d* formats decimal integers.

		> To format the number with the thousands separator, use the , flag. You can also format it for different locales, adding Locale.<country> as the first of three arguments of the function.

    - *f* formats floating-point numbers.

		> Syntax to define x as the width of the number and y as the length of the decimal part:
       
		>	   %x.yf

		> To have the output in scientific notation, use the e conversion-character:
      
		>	   %x.ye

    - *t* formats date/time values.
   
    - *b* formats lower case boolean. *B* formats upper case boolean.

		> If the second argument is null, the result is "false". If the argument is a boolean or Boolean, the result is the string returned by String.valueOf(arg). Otherwise, the result is "true".

		
