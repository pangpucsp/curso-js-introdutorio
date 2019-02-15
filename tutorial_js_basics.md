# JavaScript Tutorial Basics

This is my annotations from [javascript tutorial W3C school study](https://www.w3schools.com/js/).

  JavaScript is the programming language of HTML and the Web.
  
## Introduction \([JS Tutorial](https://www.w3schools.com/js/)\)

Some of JS examples may need some adaption to execute on Chrome Browser console \(to get it, F12, select Console Tab\).

Example (first.html)

```html+javascript
<!DOCTYPE html>
<html>
<body>

<h2>My First JavaScript</h2>

<button type="button"
onclick="document.getElementById('demo').innerHTML = Date()">
Click me to display Date and Time.</button>

<p id="demo"></p>

</body>
</html> 
```

### Why Study JavaScript?

JavaScript is one of the 3 languages all web developers must learn:

   1. HTML to define the content of web pages

   2. CSS to specify the layout of web pages

   3. JavaScript to program the behavior of web pages

Reference:
[Javascript reference](https://www.w3schools.com/jsref/default.asp)

## JS Introduction \([JS Introduction](https://www.w3schools.com/js/js_intro.asp)\)

### JavaScript Can Change HTML Content

Demo: (intro_demo1.html)
```javascript
document.getElementById("demo").innerHTML = "Hello JavaScript!";
```

Strings may be double or single quote:
Demo:
```javascript
document.getElementById('demo').innerHTML = 'Hello JavaScript!';
```

### JavaScript Can Change HTML Attribute Values

Demo: (intro_demo2.html)

```html+javascript
<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>

<img id="myImage" src="pic_bulboff.gif" style="width:100px">

<button onclick="document.getElementById('myImage').src='pic_bulboff.gif'">Turn off the light</button>
```
### JavaScript Can Change HTML Styles \(CSS\)

Demo: (intro_demo3.html)

```javascript
document.getElementById("demo").style.fontSize = "35px";
```

### JavaScript Can Hide HTML Elements

Demo: (intro_demo4.html)

```javascript
document.getElementById("demo").style.display = "none";
```

### JavaScript Can Show HTML Elements

Demo: (intro_demo5.html)

```javascript
document.getElementById('demo').style.display = 'block';
```

## JavaScript Where To \([Where To](https://www.w3schools.com/js/js_whereto.asp)\)

### The <script> Tag

In HTML, JavaScript code must be inserted between <script> and </script> tags.

Example: (where_demo1.html)

```html
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

### JavaScript Functions and Events

A JavaScript function is a block of JavaScript code, that can be executed when "called" for.

For example, a function can be called when an event occurs, like when the user clicks a button.

### JavaScript in <head> or <body>

You can place any number of scripts in an HTML document.

Scripts can be placed in the <body>, or in the <head> section of an HTML page, or in both.
    
#### JavaScript in <head>

Example: (where_demo2.html)
```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>
</head>
<body>

<h1>A Web Page</h1>
<p id="demo">A Paragraph</p>
<button type="button" onclick="myFunction()">Try it</button>

</body>
</html>
```

#### JavaScript in <body>

Example: (where_demo3.html)
```html
<!DOCTYPE html>
<html>
<body> 

<h1>A Web Page</h1>
<p id="demo">A Paragraph</p>
<button type="button" onclick="myFunction()">Try it</button>

<script>
function myFunction() {
 document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>

</body>
</html>
```

    Placing scripts at the bottom of the <body> element improves the display speed, because script compilation slows down the display.

### External JavaScript

Scripts can also be placed in external files: (myScript1.js)

```javascript
function myFunction() {
 document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```

And loaded in html files with: (where_demo4.html)

```html
<script src="myScript.js"></script>
```

    External scripts cannot contain <script> tags.
    
#### External JavaScript Advantages

  * It separates HTML and code
  * It makes HTML and JavaScript easier to read and maintain
  * Cached JavaScript files can speed up page loads
  
#### External References

Example: (where_demo5.html)

```html
<script src="https://www.w3schools.com/js/myScript1.js"></script>
```

## JS Output (https://www.w3schools.com/js/js_output.asp)

### JavaScript Display Possibilities

JavaScript can "display" data in different ways:

  * Writing into an HTML element, using innerHTML.
  * Writing into the HTML output using document.write().
  * Writing into an alert box, using window.alert().
  * Writing into the browser console, using console.log().
  
#### Using innerHTML

To access an HTML element, JavaScript can use the document.getElementById(id) method.

Example: (output_demo1.html)

```html
<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>
```

#### Using document.write()

Example: (output_demo2.html)

```html
<script>
document.write(5 + 6);
</script>
```

    Using document.write() after an HTML document is loaded, will delete all existing HTML (output_demo3.html).
    The document.write() method should only be used for testing.

#### Using window.alert()

Example: (output_demo4.html)

```html
<script>
window.alert(5 + 6);
</script>
```

#### Using console.log()

For debugging purposes, you can use the console.log() method to display data.

Example: (output_demo5.html)

```html
<script>
console.log(5 + 6);
</script>
```

## JavaScript Statements (https://www.w3schools.com/js/js_statements.asp)

Example: (stmt_demo1.html)

```javascript
var x, y, z;    // Statement 1
x = 5;          // Statement 2
y = 6;          // Statement 3
z = x + y;      // Statement 4
```

### JavaScript Programs

A JavaScript program is a list of programming statements.

    In HTML, JavaScript programs are executed by the web browser.
    
### JavaScript Statements

JavaScript statements are composed of:

Values, Operators, Expressions, Keywords, and Comments.

Most JavaScript programs contain many JavaScript statements.

The statements are executed, one by one, in the same order as they are written.

#### Semicolons ;

Semicolons separate JavaScript statements.

When separated by semicolons, multiple statements on one line are allowed:

```javascript
a = 5; b = 6; c = a + b;
```

   On the web, you might see examples without semicolons. 
   Ending statements with semicolon is not required, but highly recommended.

#### JavaScript White Space

JavaScript ignores multiple spaces. You can add white space to your script to make it more readable.

A good practice is to put spaces around operators ( = + - * / ):

```javascript
var x = y + z;
```

#### JavaScript Line Length and Line Breaks

For best readability, programmers often like to avoid code lines longer than 80 characters.

If a JavaScript statement does not fit on one line, the best place to break it is after an operator:

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

#### JavaScript Code Blocks

JavaScript statements can be grouped together in code blocks, inside curly brackets {...}.

Example:

```javascript
function myFunction() {
    document.getElementById("demo1").innerHTML = "Hello Dolly!";
    document.getElementById("demo2").innerHTML = "How are you?";
}
```

#### JavaScript Keywords

JavaScript statements often start with a keyword to identify the JavaScript action to be performed.

Keyword  | Description
------------------------------------------------------
break    | Terminates a switch or a loop
continue | Jumps out of a loop and starts at the top
debugger | Stops the execution of JavaScript, and calls (if available) the debugging function
do ... while | Executes a block of statements, and repeats the block, while a condition is true
for      | Marks a block of statements to be executed, as long as a condition is true
function | Declares a function
if ... else | Marks a block of statements to be executed, depending on a condition
return   | Exits a function
switch   | Marks a block of statements to be executed, depending on different cases
try ... catch | Implements error handling to a block of statements
var      | Declares a variable

    JavaScript keywords are reserved words. Reserved words cannot be used as names for variables.

## JS Syntax (https://www.w3schools.com/js/js_syntax.asp)

### JavaScript Values

The JavaScript syntax defines two types of values: Fixed values and variable values.
Fixed values are called literals. Variable values are called variables.

### JavaScript Literals

**Numbers** are written with or without decimals:

```javascript
10.50

1001
```

**Strings** are text, written within double or single quotes:

```javascript
"John Doe"

'John Doe'
```

### JavaScript Variables

In a programming language, variables are used to store data values.

JavaScript uses the var keyword to declare variables.

An equal sign is used to assign values to variables.

### JavaScript Operators

JavaScript uses arithmetic operators ( + - *  / ) to compute values:

```javascript
(5 + 6) * 10
```

JavaScript uses an assignment operator ( = ) to assign values to variables:

```javascript
var x, y;
x = 5;
y = 6;
```

### JavaScript Expressions

An expression is a combination of values, variables, and operators, which computes to a value.

The computation is called an evaluation.

The values can be of various types, such as numbers and strings.

For example, "John" + " " + "Doe", evaluates to "John Doe":

```javascript
"John" + " " + "Doe"
```

### JavaScript Keywords

JavaScript keywords are used to identify actions to be performed.

The var keyword tells the browser to create variables:

```javascript
var x, y;
x = 5 + 6;
y = x * 10;
```

### JavaScript Comments

Code after double slashes // or between /\* and \*/ is treated as a **comment**.

### JavaScript Identifiers

Identifiers are names.

In JavaScript, identifiers are used to name variables (and keywords, and functions, and labels).

In JavaScript, the first character must be a letter, or an underscore (\_), or a dollar sign ($).

### JavaScript is Case Sensitive

All JavaScript identifiers are case sensitive.

### JavaScript and Camel Case

![Camel Case](images/pic_camelcase.jpg)

Lower Camel Case:

JavaScript programmers tend to use camel case that starts with a lowercase letter:

firstName, lastName, masterCard, interCity.

### JavaScript Character Set

JavaScript uses the Unicode character set. See (https://www.w3schools.com/charsets/ref_html_utf8.asp) for a reference on unicode.

## JS Comments (https://www.w3schools.com/js/js_comments.asp)

### Single Line Comments

Single line comments start with //.

### Multi-line Comments

Multi-line comments start with /\* and end with \*/.

Any text between /\* and \*/ will be ignored by JavaScript.

    It is most common to use single line comments.
    Block comments are often used for formal documentation.
    
### Using Comments to Prevent Execution

Use comments to prevent execution of code is suitable for code testing.

## JavaScript Variables

JavaScript variables are containers for storing data values.

### Much Like Algebra

In this example, price1, price2, and total, are variables:

```javascript
var price1 = 5;
var price2 = 6;
var total = price1 + price2;
```

    JavaScript variables are containers for storing data values.

### JavaScript Identifiers

All JavaScript **variables** must be identified with **unique names**. These unique names are called **identifiers**.

The general rules for constructing names for variables (unique identifiers) are:

  * Names can contain letters, digits, underscores, and dollar signs.
  * Names must begin with a letter
  * Names can also begin with $ and \_ (but we will not use it in this tutorial)
  * Names are case sensitive (y and Y are different variables)
  * Reserved words (like JavaScript keywords) cannot be used as names.
  
### The Assignment Operator
  
  In JavaScript, the equal sign (=) is an "assignment" operator, not an "equal to" operator.
  
    The "equal to" operator is written like == in JavaScript.
    
### JavaScript Data Types

JavaScript variables can hold numbers like 100 and text values like "John Doe".

In programming, text values are called text strings.

JavaScript can handle many types of data, but for now, just think of numbers and strings.

Strings are written inside double or single quotes. Numbers are written without quotes.

### Declaring (Creating) JavaScript Variables

Creating a variable in JavaScript is called "declaring" a variable.

You declare a JavaScript variable with the var keyword:

```javascript
var carName;
```

After the declaration, the variable has no value. (Technically it has the value of **undefined**)

    It's a good programming practice to declare all variables at the beginning of a script.

### One Statement, Many Variables

Start the statement with var and separate the variables by comma:

```javascript
var person = "John Doe", carName = "Volvo", price = 200;
```

A declaration can span multiple lines:

```javascript
var person = "John Doe",
carName = "Volvo",
price = 200;
```

### Value = undefined

A variable declared without a value will have the value **undefined**.

### Re-Declaring JavaScript Variables

If you re-declare a JavaScript variable, it will not lose its value. (var_demo1.html)

### JavaScript Arithmetic

As with algebra, you can do arithmetic with JavaScript variables, using operators like = and +:

```javascript
var x = 5 + 2 * 3;
```

You can also add strings, but strings will be concatenated:

```javascript
var x = "John" + " " + "Doe";
```

Also try this:

```javascript
var x = "5" + 2 + 3;
```

    If you put a number in quotes, the rest of the numbers will be treated as strings, and concatenated.

What next code evaluate to?

```javascript
var x = 2 + 3 + "5";
```

## JavaScript Operators (https://www.w3schools.com/js/js_operators.asp)

The assignment operator (=) assigns a value to a variable.

The addition operator (+) adds numbers and concatenates strings.

### JavaScript Arithmetic Operators

Arithmetic operators are used to perform arithmetic on numbers:

Operator  | Description
-----------------------------------------------------------
+         | Addition
-         | Subtraction
*         | Multiplication
**        | Exponentiation (ES6)
/         | Division
%         | Modulus (Division Remainder)
++        | Increment
--        | Decrement

    Arithmetic operators are fully described in the JS Arithmetic chapter.

### JavaScript Assignment Operators

Operator | Example | Same As
-----------------------------
=        | x = y   | x = y
+=       | x += y  | x = x + y
-=       | x -= y  | x = x - y
*=       | x *= y  | x = x * y
/=       | x /= y  | x = x / y
%=       | x %= y  | x = x % y

### JavaScript String Operators

The + operator can also be used to add (concatenate) strings.

The += assignment operator can also be used to add (concatenate) strings.

    If you add a number and a string, the result will be a string!

### JavaScript Comparison Operators

Operator | Description
--------------------------------------------------------
==       | equal to
===      | equal value and equal type
!=       | not equal
!==      | not equal value or not equal type
>        | greater than
<        | less than
>=       | greater than or equal to
<=       | less than or equal to
?        | ternary operator

## JavaScript Logical Operators

Operator | Description
------------------------------
&&       | logical and
||       | logical or
!        | logical not

### JavaScript Type Operators

Operator   | Description
-------------------------------------------------------------
typeof     | Returns the type of a variable
instanceof | Returns true if an object is an instance of an object type

### JavaScript Bitwise Operators

Any numeric operand in the operation is converted into a 32 bit number. The result is converted back to a JavaScript number.

Operator | Description |  Example  |   Same as   | Result | Decimal
&        | AND         | 5 & 1     | 0101 & 0001 | 0001   | 1
\|       | OR          | 5 \| 1    | 0101 \| 0001 | 0101   | 5
~        | NOT         | ~ 5       | ~0101       | 1010   | 10
^        | XOR         | 5 ^ 1     | 0101 ^ 0001 | 0100 |   | 4
<<       | Zero fill left shift | 5 << 1 | 0101 << 1 | 1010 | 10
>>       | Signed right shift | 5 >> 1 | 0101 >> 1 | 0010 | 2
>>>      | Zero fill right shift | 5 >>> 1 | 0101 >>> 1 | 0010 | 2

### Arithmetic Operations

A typical arithmetic operation operates on two numbers.

The two numbers can be literals:

```javascript
var a = 6;
var x = 100 + 50;
var y = (100 + 50) * a;
```

### Operators and Operands

The numbers (in an arithmetic operation) are called **operands**.

The operation (to be performed between the two operands) is defined by an **operator**.

Operand | Operator | Operand
-----------------------------
100     | +        | 50

    In arithmetic, the division of two integers produces a quotient and a remainder.
    In mathematics, the result of a modulo operation is the remainder of an arithmetic division.

### Operator Precedence

Operator precedence describes the order in which operations are performed in an arithmetic expression.

```javascript
var x = 100 + 50 * 3;
```

Multiplication (*) and division (/) have higher precedence than addition (+) and subtraction (-).

And (as in school mathematics) the precedence can be changed by using parentheses:

```javascript
var x = (100 + 50) * 3;
```

When many operations have the same precedence (like addition and subtraction), they are computed from left to right:

```javascript
var x = 100 + 50 - 3;
```

### JavaScript Operator Precedence Values

Value | Operator    | Description               | Example
--------------------------------------------------------------
20    | ( )         | Expression grouping       | (3 + 4)
  |   |   |  
19    | .           | Member                    | person.name
19    | []          | Member                    | person["name"]
19    | ()          | Function call             | myFunction()
19    | new         | Create                    | new Date()
  |   |   |  
17    | ++          | Postfix Increment         | i++
17    | --          | Postfix Decrement         | i--
  |   |   |  
16    | ++          | Prefix Increment          | ++i
16    | --          | Prefix Decrement          | --i
16    | !           | Logical not               | !(x==y)
16    | typeof      | Type                      | typeof x
  |   |   |  
15    | **          | Exponentiation (ES7)          | 10 ** 2
  |   |   |  
14    | *           | Multiplication            | 10 * 5
14    | /           | Division                  | 10 / 5
14    | %           | Division Remainder        | 10 % 5
  |   |   |  
13    | +           | Addition                  | 10 + 5
13    | -           | Subtraction               | 10 - 5
  |   |   |  
12    | <<          | Shift left                | x << 2
12    | >>          | Shift right               | x >> 2
12    | >>>         | Shift right (unsigned)    | x >>> 2
  |   |   |  
11    | <           | Less than                 | x < y 
11    | <=          | Less than or equal        | x <= y
11    | >           | Greater than              | x > y
11    | >=          | Greater than or equal     | x >= y
11    | in          | Property in Object        | "PI" in Math
11    | instanceof  | Instance of Object        | instanceof Array
  |   |   |  
10    | ==          | Equal                     | x == y
10    | ===         | Strict equal              | x === y
10    | !=          | Unequal                   | x != y
10    | !==         | Strict unequal            | x !== y
  |   |   |  
9     | &           | Bitwise AND               | x & y
8     | ^           | Bitwise XOR               | x ^ y
7     | \|          | Bitwise OR                | x \| y
6     | &&          | Logical AND               | x && y
5     | \|\|        | Logical OR                | x \|\| y
4     | ? :         | Condition                 | (x == y) ? "Yes" : "No"

3     | +=          | Assignment                | x += y
3     | +=          | Assignment                | x += y
3     | -=          | Assignment                | x -= y
3     | *=          | Assignment                | x *= y
3     | %=          | Assignment                | x %= y
3     | <<=         | Assignment                | x <<= y
3     | >>=         | Assignment                | x >>= y
3     | >>>=        | Assignment                | x >>>= y
3     | &=          | Assignment                | x &= y
3     | ^=          | Assignment                | x ^= y
3     | \|=         | Assignment                | x \|= y

2     | yield       | Pause Function            | yield x
1     | ,           | Comma                     | 5 , 6

    Expressions in parentheses are fully computed before the value is used in the rest of the expression.

## JavaScript Assignment (https://www.w3schools.com/js/js_assignment.asp)

Assignment operators assign values to JavaScript variables.

Operator | Example  | Same As
-------------------------------------------------
=        | x = y    | x = y
+=       | x += y   | x = x + y
-=       | x -= y   | x = x - y
*=       | x *= y   | x = x * y
/=       | x /= y   | x = x / y
%=       | x %= y   | x = x % y
<<=      | x <<= y  | x = x << y
>>=      | x >>= y  | x = x >> y
>>>=     | x >>>= y | x = x >>> y
&=       | x &= y   | x = x & y
^=       | x ^= y   | x = x ^ y
\|=      | x \|= y  | x = x \| y
**=      | x **= y  | x = x ** y
