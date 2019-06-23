# Fundamentos V de JavaScript

Esta é a continuação de [Fundamentos IV de JS](fundamento4_js.md).

## Conversão de Tipos em JavaScript (https://www.w3schools.com/js/js_type_conversion.asp)

*Number\(\)* converte para um Number, *String\(\)* converte para uma String,
*Boolean\(\)* converte para um Boolean.

### Tipos de Dados em JavaScript

JavaScript tem 5 tipos de dados diferentes que podem conter valores:

  * *string* (texto)
  * *number* (número)
  * *boolean* (booleano, ou lógico)
  * *object* (objeto)
  * *function* (função)

Existem 3 tipos de objetos:

  * *Object* (Objeto)
  * *Date* (Data ou Horário)
  * *Array* (Vetor)

E dois tipos de dados que não podem conter valores:

  * *null* (vazio, nulo)
  * *undefined* (indefinido)

### O Operador typeof

Você pode usar o operador typeof para descobrir o tipo de dado de uma variável
em JavaScript.

Exemplo

```javascript
typeof "João"                 // Retorna "string"
typeof 3.14                   // Retorna "number"
typeof NaN                    // Retorna "number"
typeof false                  // Retorna "boolean"
typeof [1,2,3,4]              // Retorna "object"
typeof {name:'John', age:34}  // Retorna "object"
typeof new Date()             // Retorna "object"
typeof function () {}         // Retorna "function"
typeof myCar                  // Retorna "undefined" *
typeof null                   // Retorna "object"
```

Por favor, observe que:

  * O tipo de dado de *NaN* é number
  * O tipo de dado de um *array* é object
  * O tipo de dado de uma instância de *Date* é object
  * O tipo de dado de *null* é object
  * O tipo de dado de uma variável indefinida é *undefined*
  * O tipo de dado de uma variável que não teve um valor atribuido a ela é
  também *undefined*

    Você não pode usar typeof para determinar se um objeto de JavaScript é um
    array (ou uma data).

### O Tipo de Dados de typeof

O operador **typeof** não é uma variável. É um operador. Operadores como
\( + - * / \) não têm um tipo de dado.

Mas, o operador typeof sempre retorna uma string \(contendo o tipo do operando\).

### A Propriedade **constructor**

A propriedade *constructor* retorna a função construtora para todas as
variáveis de JavaScript. E pode ser usada para determinar o tipo de uma variável.

Exemplo

```javascript
"João".constructor                // Retorna function String()  {[native code]}
(3.14).constructor                // Retorna function Number()  {[native code]}
false.constructor                 // Retorna function Boolean() {[native code]}
[1,2,3,4].constructor             // Retorna function Array()   {[native code]}
{nome:'João',idade:34}.constructor  // Retorna function Object()  {[native code]}
new Date().constructor            // Retorna function Date()    {[native code]}
function () {}.constructor        // Retorna function Function(){[native code]}
```

Você pode checar a propriedade *constructor* para descobrir se um objeto é
um *Array* (contém a palavra "Array"):

Exemplo

```javascript
function isArray(myArray) {
  return myArray.constructor.toString().indexOf("Array") > -1;
}
```

Ou mais simples ainda, você pode checar se o objeto é uma função *Array*:

Exemplo

```javascript
function isArray(myArray) {
  return myArray.constructor === Array;
}
```

Você pode verificar a propridade constructor para descobrir se um objeto é
um *Date* (contém a palavra "Date"):

Exemplo

```javascript
function isDate(myDate) {
  return myDate.constructor.toString().indexOf("Date") > -1;
}
```

Ou mais simplesmente, você pode verificar se o objeto é uma função *Date*:

Exemplo

```javascript
function isDate(myDate) {
  return myDate.constructor === Date;
}
```

### JavaScript Type Conversion

JavaScript variables can be converted to a new variable and another data type:

  * By the use of a JavaScript function
  * Automatically by JavaScript itself

### Converting Numbers to Strings

The global method String\(\) can convert numbers to strings.

It can be used on any type of numbers, literals, variables, or expressions:

Exemplo

```javascript
String(x)         // returns a string from a number variable x
String(123)       // returns a string from a number literal 123
String(100 + 23)  // returns a string from a number from an expression
```

The Number method toString\(\) does the same.

Exemplo

```javascript
x.toString()
(123).toString()
(100 + 23).toString()
```

In the section Number Methods, you will find more methods that can be used to convert numbers to strings:

Method            | Description
-------------------------------------------------------
toExponential\(\) | Retorna a string, with a number rounded and written using exponential notation.
toFixed\(\)       | Retorna a string, with a number rounded and written with a specified number of decimals.
toPrecision\(\)   | Retorna a string, with a number written with a specified length

### Converting Booleans to Strings

The global method String\(\) can convert booleans to strings.

```javascript
String(false)      // returns "false"
String(true)       // returns "true"
```

The Boolean method toString() does the same.

```javascript
false.toString()   // returns "false"
true.toString()    // returns "true"
```

### Converting Dates to Strings

The global method String() can convert dates to strings.

```javascript
String(Date())  // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

The Date method toString() does the same.

Exemplo
```javascript
Date().toString()  // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

In the section Date Methods, you find more methods that can be used to convert dates to strings.

### Converting Strings to Numbers

The global method Number\(\) can convert strings to numbers.

Strings containing numbers \(like "3.14"\) convert to numbers \(like 3.14\).

Empty strings convert to 0.

Anything else converts to NaN \(Not a Number\).

```javascript
Number("3.14")    // returns 3.14
Number(" ")       // returns 0
Number("")        // returns 0
Number("99 88")   // returns NaN
```

In the section Number Methods, you find more methods that can be used to convert strings to numbers.

### The Unary + Operator

The unary + operator can be used to convert a variable to a number:

Exemplo
```javascript
var y = "5";      // y is a string
var x = + y;      // x is a number
```

If the variable cannot be converted, it will still become a number, but with the value NaN (Not a Number):

Exemplo
```javascript
var y = "John";   // y is a string
var x = + y;      // x is a number (NaN)
```

### Converting Booleans to Numbers

The global method Number\(\) can also convert booleans to numbers.

```javascript
Number(false)     // returns 0
Number(true)      // returns 1
```

### Converting Dates to Numbers

The global method Number\(\) can be used to convert dates to numbers.

```javascript
d = new Date();
Number(d)          // returns 1404568027739
```

The date method getTime\(\) does the same.

### Automatic Type Conversion

When JavaScript tries to operate on a "wrong" data type, it will try to convert the value to a "right" type.

The result is not always what you expect:

```javascript
5 + null    // returns 5         because null is converted to 0
"5" + null  // returns "5null"   because null is converted to "null"
"5" + 2     // returns "52"      because 2 is converted to "2"
"5" - 2     // returns 3         because "5" is converted to 5
"5" * "2"   // returns 10        because "5" and "2" are converted to 5 and 2
```

### Automatic String Conversion

JavaScript automatically calls the variable's toString\(\) function when you try to "output" an object or a variable:

```javascript
document.getElementById("demo").innerHTML = myVar;

// if myVar = {name:"Fjohn"}  // toString converts to "[object Object]"
// if myVar = [1,2,3,4]       // toString converts to "1,2,3,4"
// if myVar = new Date()      // toString converts to "Fri Jul 18 2014 09:08:55 GMT+0200"
```

Numbers and booleans are also converted, but this is not very visible:

```javascript
// if myVar = 123             // toString converts to "123"
// if myVar = true            // toString converts to "true"
// if myVar = false           // toString converts to "false"
```

### JavaScript Type Conversion Table

This table shows the result of converting different JavaScript values to Number, String, and Boolean:

Original Value | Converted to Number | Converted to String | Converted to Boolean
---------------------------------------------------------------------------------
false          | 0                   | "false"             | false
true           | 1                   | "true"              | true
0              | 0                   | "0"                 | false
1              | 1                   | "1"                 | true
"0"            | 0                   | "0"                 | true
"000"          | 0                   | "000"               | true
"1"            | 1                   | "1"                 | true
NaN            | NaN                 | "NaN"               | false
Infinity       | Infinity            | "Infinity"          | true
-Infinity      | -Infinity           | "-Infinity"         | true
""             | 0                   | ""                  | false
"20"           | 20                  | "20"                | true
"twenty"       | NaN                 | "twenty"            | true
[ ]            | 0                   | ""                  | true
[20]           | 20                  | "20"                | true
[10,20]        | NaN                 | "10,20"             | true
["twenty"]     | NaN                 | "twenty"            | true
["ten","five"] | NaN                 | "ten,five"          | true
function(){}   | NaN                 | "function(){}"      | true
{ }            | NaN                 | "[object Object]"   | true
null           | 0                   | "null"              | false
undefined      | NaN                 | "undefined"         | false

## JavaScript Bitwise Operations (https://www.w3schools.com/js/js_bitwise.asp)

### JavaScript Bitwise Operators

Operator | Name | Description
-------------------------------------------------------------------
&        | AND  | Sets each bit to 1 if both bits are 1
\|       | OR   | Sets each bit to 1 if one of two bits is 1
^        | XOR  | Sets each bit to 1 if only one of two bits is 1
~        | NOT  | Inverts all the bits
<<       | Zero fill left shift | Shifts left by pushing zeros in from the right and let the leftmost bits fall off
\>>      | Signed right shift | Shifts right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off
\>>>     | Zero fill right shift | Shifts right by pushing zeros in from the left, and let the rightmost bits fall off

Exemplos

Operation | Result | Same as      | Result
----------------------------------------
5 & 1     | 1      | 0101 & 0001  |  0001
5 \| 1    | 5      | 0101 \| 0001 |  0101
~ 5       | 10     |  ~0101       |  1010
5 << 1    | 10     | 0101 << 1    |  1010
5 ^ 1     | 4      | 0101 ^ 0001  |  0100
5 >> 1    | 2      | 0101 >> 1    |  0010
5 >>> 1   | 2      | 0101 >>> 1   |  0010

### JavaScript Uses 32 bits Bitwise Operands

JavaScript stores numbers as 64 bits floating point numbers, but all bitwise operations are performed on 32 bits binary numbers.

Before a bitwise operation is performed, JavaScript converts numbers to 32 bits signed integers.

After the bitwise operation is performed, the result is converted back to 64 bits JavaScript numbers.

    The examples above uses 4 bits unsigned binary numbers. Because of this ~ 5 returns 10.

    Since JavaScript uses 32 bits signed integers, it will not return 10. It will return -6.

    00000000000000000000000000000101 (5)

    11111111111111111111111111111010 (~5 = -6)

    A signed integer uses the leftmost bit as the minus sign.

### Bitwise AND

When a bitwise AND is performed on a pair of bits, it returns 1 if both bits are 1.

One bit example:

Operation | Result
-------------------
0 & 0     | 0
0 & 1     | 0
1 & 0     | 0
1 & 1     | 1

4 bits example:

Operation   | Result
--------------------
1111 & 0000 | 0000
1111 & 0001 | 0001
1111 & 0010 | 0010
1111 & 0100 | 0100

### Bitwise OR

When a bitwise OR is performed on a pair of bits, it returns 1 if one of the bits are 1:

One bit example:

Operation |  Result
-------------------
0 \| 0    |  0
0 \| 1    |  1
1 \| 0    |  1
1 \| 1    |  1

4 bits example:

Operation    |  Result
----------------------
1111 \| 0000 |  1111
1111 \| 0001 |  1111
1111 \| 0010 |  1111
1111 \| 0100 |  1111

### Bitwise XOR

When a bitwise XOR is performed on a pair of bits, it returns 1 if the bits are different:

One bit example:

Operation | Result
------------------
0 ^ 0     | 0
0 ^ 1     | 1
1 ^ 0     | 1
1 ^ 1     | 0

4 bits example:

Operation   | Result
--------------------
1111 ^ 0000 | 1111
1111 ^ 0001 | 1110
1111 ^ 0010 | 1101
1111 ^ 0100 | 1011

### JavaScript Bitwise AND \(&\)

Bitwise AND returns 1 only if both bits are 1:

Decimal | Binary
---------------------------------------------
5       | 00000000000000000000000000000101
1       | 00000000000000000000000000000001
5 & 1   | 00000000000000000000000000000001 \(1\)

Exemplo

```javascript
var x = 5 & 1;
```

### JavaScript Bitwise OR \(\|\)

Bitwise OR returns 1 if one of the bits are 1:

Decimal | Binary
-----------------------------------------------
5       | 00000000000000000000000000000101
1       | 00000000000000000000000000000001
5 \| 1  | 00000000000000000000000000000101 \(5\)

Exemplo

```javascript
var x = 5 | 1;
```

### JavaScript Bitwise XOR \(^\)

Bitwise XOR returns 1 if the bits are different:

Decimal | Binary
-----------------------------------------------
5       | 00000000000000000000000000000101
1       | 00000000000000000000000000000001
5 ^ 1   | 00000000000000000000000000000100 (4)

Exemplo

```javascript
var x = 5 ^ 1;
```

### JavaScript Bitwise NOT \(~\)

Decimal | Binary
--------------------------------------------
5       | 00000000000000000000000000000101
~5      | 11111111111111111111111111111010 (-6)

Exemplo

```javascript
var x = ~5;
```

### JavaScript \(Zero Fill\) Bitwise Left Shift \(<<\)

This is a zero fill left shift. One or more zero bits are pushed in from the right, and the leftmost bits fall off:

Decimal | Binary
-----------------------------------------------
5       | 00000000000000000000000000000101
5 << 1  | 00000000000000000000000000001010 (10)

Exemplo

```javascript
var x = 5 << 1;
```

### JavaScript \(Sign Preserving\) Bitwise Right Shift \(>>\)

This is a sign preserving right shift. Copies of the leftmost bit are pushed in from the left, and the rightmost bits fall off:

Decimal  | Binary
-------------------------------------------------
-5       | 11111111111111111111111111111011
-5 >> 1  | 11111111111111111111111111111101 (-3)

Exemplo

```javascript
var x = -5 >> 1;
```

### JavaScript \(Zero Fill\) Right Shift \(>>>\)

This is a zero fill right shift. One or more zero bits are pushed in from the left, and the rightmost bits fall off:

Decimal  | Binary
------------------------------------------------
5        | 00000000000000000000000000000101
5 >>> 1  | 00000000000000000000000000000010 (2)

Exemplo

```javascript
var x = 5 >>> 1;
```

### Binary Numbers

Binary numbers with only one bit set is easy to understand:

Binary Representation             |  Decimal value
-----------------------------------------
00000000000000000000000000000001  |  1
00000000000000000000000000000010  |  2
00000000000000000000000000000100  |  4
00000000000000000000000000001000  |  8
00000000000000000000000000010000  |  16
00000000000000000000000000100000  |  32
00000000000000000000000001000000  |  64

Setting a few more bits reveals the binary pattern:

Binary Representation             |  Decimal value
---------------------------------------------------------
00000000000000000000000000000101  |  5 \(4 + 1\)
00000000000000000000000000001101  |  13 \(8 + 4 + 1\)
00000000000000000000000000101101  |  45 \(32 + 8 + 4 + 1\)

JavaScript binary numbers are stored in two's complement format.

This means that a negative number is the bitwise NOT of the number plus 1:

Binary Representation             |  Decimal value
---------------------------------------------------
00000000000000000000000000000101  |  5
11111111111111111111111111111011  |  -5
00000000000000000000000000000110  |  6
11111111111111111111111111111010  |  -6
00000000000000000000000000101000  |  40
11111111111111111111111111011000  |  -40

### Converting Decimal to Binary

Exemplo

```javascript
function dec2bin(dec){
  return (dec >>> 0).toString(2);
}
```

### Converting Binary to Decimal

Exemplo

```javascript
function bin2dec(bin){
  return parseInt(bin, 2).toString(10);
}
```

## JavaScript Regular Expressions (https://www.w3schools.com/js/js_regexp.asp)

A regular expression is a sequence of characters that forms a search pattern.

The search pattern can be used for text search and text replace operations.

### What Is a Regular Expression?

A regular expression is a sequence of characters that forms a search pattern.

When you search for data in a text, you can use this search pattern to describe what you are searching for.

A regular expression can be a single character, or a more complicated pattern.

Regular expressions can be used to perform all types of text search and text replace operations.

Syntax

```javascript
/pattern/modifiers;
```

Exemplo

```javascript
var patt = /w3schools/i;
```

Exemplo explained:

**/w3schools/i**  is a regular expression.

**w3schools**  is a pattern \(to be used in a search\).

**i**  is a modifier \(modifies the search to be case-insensitive\).

### Using String Methods

In JavaScript, regular expressions are often used with the two string methods: search\(\) and replace\(\).

The search\(\) method uses an expression to search for a match, and returns the position of the match.

The replace\(\) method returns a modified string where the pattern is replaced.

#### Using String search\(\) With a String

The search\(\) method searches a string for a specified value and returns the position of the match:

Exemplo: Use a string to do a search for "W3schools" in a string:

```javascript
var str = "Visit W3Schools!";
var n = str.search("W3Schools");
```

#### Using String search\(\) With a Regular Expression

Exemplo: Use a regular expression to do a case-insensitive search for "w3schools" in a string:

```javascript
var str = "Visit W3Schools";
var n = str.search(/w3schools/i);
```

The result in n will be:

  6

#### Using String replace() With a String

The replace\(\) method replaces a specified value with another value in a string:

```javascript
var str = "Visit Microsoft!";
var res = str.replace("Microsoft", "W3Schools");
```

#### Use String replace() With a Regular Expression

Exemplo: Use a case insensitive regular expression to replace Microsoft with W3Schools in a string:

```javascript
var str = "Visit Microsoft!";
var res = str.replace(/microsoft/i, "W3Schools");
```

The result in res will be:

  Visit W3Schools!

#### Did You Notice?

    Regular expression arguments (instead of string arguments) can be used in the methods above.
    Regular expressions can make your search much more powerful (case insensitive for example).

#### Regular Expression Modifiers

Modifiers can be used to perform case-insensitive more global searches:

Modifier |  Description
-------------------------------------------------------------------------------------
i        |  Perform case-insensitive matching
g        |  Perform a global match \(find all matches rather than stopping after the first match\)
m        |  Perform multiline matching

### Regular Expression Patterns

Brackets are used to find a range of characters:

Expression | Description
---------------------------------------------------------
[abc]      | Find any of the characters between the brackets
[0-9]      | Find any of the digits between the brackets
(x\|y)     | Find any of the alternatives separated with \|

Metacharacters are characters with a special meaning:

Metacharacter | Description
------------------------------------------------------------------------------
\d            | Find a digit
\s            | Find a whitespace character
\b            | Find a match at the beginning or at the end of a word
\uxxxx        | Find the Unicode character specified by the hexadecimal number xxxx

Quantifiers define quantities:

Quantifier | Description
------------------------------------------------------------------------
n+         | Matches any string that contains at least one n
n*         | Matches any string that contains zero or more occurrences of n
n?         | Matches any string that contains zero or one occurrences of n

### Using the RegExp Object

In JavaScript, the RegExp object is a regular expression object with predefined properties and methods.

#### Using test\(\)

The test\(\) method is a RegExp expression method.

It searches a string for a pattern, and returns true or false, depending on the result.

The following example searches a string for the character "e":

Exemplo

```javascript
var patt = /e/;
patt.test("The best things in life are free!");
```

Since there is an "e" in the string, the output of the code above will be:

  true

You don't have to put the regular expression in a variable first. The two lines above can be shortened to one:

```javascript
/e/.test("The best things in life are free!");
```

#### Using exec\(\)

The exec\(\) method is a RegExp expression method.

It searches a string for a specified pattern, and returns the found text as an object.

If no match is found, it returns an empty \(null\) object.

The following example searches a string for the character "e":

Exemplo

```javascript
/e/.exec("The best things in life are free!");
```

## JavaScript Errors - Throw and Try to Catch (https://www.w3schools.com/js/js_errors.asp)

The **try** statement lets you test a block of code for errors.

The **catch** statement lets you handle the error.

The **throw** statement lets you create custom errors.

The **finally** statement lets you execute code, after try and catch, regardless of the result.

### Errors Will Happen!

When executing JavaScript code, different errors can occur.

Errors can be coding errors made by the programmer, errors due to wrong input, and other unforeseeable things.

Exemplo: In this example we have written alert as adddlert to deliberately produce an error: (try_demo1.html)

```javascript
<p id="demo"></p>

<script>
try {
  adddlert("Welcome guest!");
}
catch(err) {
  document.getElementById("demo").innerHTML = err.message;
}
</script>
```

    JavaScript catches **adddlert** as an error, and executes the catch code to handle it.

### JavaScript try and catch

The try statement allows you to define a block of code to be tested for errors while it is being executed.

The catch statement allows you to define a block of code to be executed, if an error occurs in the try block.

The JavaScript statements **try** and **catch** come in pairs:

```javascript
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
```

### JavaScript Throws Errors

When an error occurs, JavaScript will normally stop and generate an error message.

The technical term for this is: JavaScript will throw an exception \(throw an error\).

    JavaScript will actually create an Error object with two properties: name and message.

### The throw Statement

The throw statement allows you to create a custom error.

Technically you can throw an exception (throw an error).

The exception can be a JavaScript String, a Number, a Boolean or an Object:

```javascript
throw "Too big";    // throw a text
throw 500;          // throw a number
```

If you use throw together with try and catch, you can control program flow and generate custom error messages.

### Input Validation Exemplo

This example examines input. If the value is wrong, an exception \(err\) is thrown.

The exception \(err\) is caught by the catch statement and a custom error message is displayed: (inVal_demo1.html)

```html
<!DOCTYPE html>
<html>
<body>

<p>Please input a number between 5 and 10:</p>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>
<p id="p01"></p>

<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "empty";
    if(isNaN(x)) throw "not a number";
    x = Number(x);
    if(x < 5) throw "too low";
    if(x > 10) throw "too high";
  }
  catch(err) {
    message.innerHTML = "Input is " + err;
  }
}
</script>

</body>
</html>
```

### HTML Validation

The code above is just an example.

Modern browsers will often use a combination of JavaScript and built-in HTML validation, using predefined validation rules defined in HTML attributes:

```html
<input id="demo" type="number" min="5" max="10" step="1">
```

### The finally Statement

The finally statement lets you execute code, after try and catch, regardless of the result:

Syntax

```javascript
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
finally {
  Block of code to be executed regardless of the try / catch result
}
```

Exemplo

```javascript
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10) throw "is too high";
    if(x < 5) throw "is too low";
  }
  catch(err) {
    message.innerHTML = "Error: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}
```

### The Error Object

JavaScript has a built in error object that provides error information when an error occurs.

The error object provides two useful properties: name and message.

#### Error Object Properties

Property | Description
---------------------------------------------------------------
name     | Sets or returns an error name
message  | Sets or returns an error message \(a string\)

#### Error Name Values

Six different values can be returned by the error name property:

Error Name     | Description
--------------------------------------------------------------
EvalError      | An error has occurred in the eval\(\) function
RangeError     | A number "out of range" has occurred
ReferenceError | An illegal reference has occurred
SyntaxError    | A syntax error has occurred
TypeError      | A type error has occurred
URIError       | An error in encodeURI\(\) has occurred

##### Eval Error

An EvalError indicates an error in the eval\(\) function.

Newer versions of JavaScript do not throw EvalError. Use SyntaxError instead.

##### Range Error

A RangeError is thrown if you use a number that is outside the range of legal values.

For example: You cannot set the number of significant digits of a number to 500.

```javascript
var num = 1;
try {
  num.toPrecision(500);   // A number cannot have 500 significant digits
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### A ReferenceError is thrown if you use \(reference\) a variable that has not been declared:

Exemplo

```javascript
var x;
try {
  x = y + 1;   // y cannot be referenced (used)
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### Syntax Error

A SyntaxError is thrown if you try to evaluate code with a syntax error.

Exemplo

```javascript
try {
  eval("alert('Hello)");   // Missing ' will produce an error
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### Type Error

A TypeError is thrown if you use a value that is outside the range of expected types:

Exemplo

```javascript
var num = 1;
try {
  num.toUpperCase();   // You cannot convert a number to upper case
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### URI \(Uniform Resource Identifier\) Error

A URIError is thrown if you use illegal characters in a URI function:

Exemplo

```javascript
try {
  decodeURI("%%%");   // You cannot URI decode percent signs
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

### on-Standard Error Object Properties

Mozilla and Microsoft defines some non-standard error object properties:

fileName \(Mozilla\)
lineNumber \(Mozilla\)
columnNumber \(Mozilla\)
stack \(Mozilla\)
description \(Microsoft\)
number \(Microsoft\)

Do not use these properties in public web sites. They will not work in all browsers.

## JavaScript Scope (https://www.w3schools.com/js/js_scope.asp)

Scope determines the accessibility (visibility) of variables.

### JavaScript Function Scope

In JavaScript there are two types of scope:

  * Local scope
  * Global scope

JavaScript has function scope: Each function creates a new scope.

Scope determines the accessibility (visibility) of these variables.

Variables defined inside a function are not accessible (visible) from outside the function.

### Local JavaScript Variables

Variables declared within a JavaScript function, become **LOCAL** to the function.

Local variables have Function scope: They can only be accessed from within the function.

Exemplo

```javascript
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";

  // code here CAN use carName

}
```

Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.

### Global JavaScript Variables

A variable declared outside a function, becomes **GLOBAL**.

A global variable has global scope: All scripts and functions on a web page can access it.

Exemplo

```javascript
var carName = "Volvo";

// code here can use carName

function myFunction() {

  // code here can also use carName

}
```

### JavaScript Variables

In JavaScript, objects and functions are also variables.

    Scope determines the accessibility of variables, objects, and functions from different parts of the code.

### Automatically Global

If you assign a value to a variable that has not been declared, it will automatically become a **GLOBAL** variable.

This code example will declare a global variable carName, even if the value is assigned inside a function.

Exemplo

```javascript
myFunction();

// code here can use carName

function myFunction() {
  carName = "Volvo";
}
```

### Strict Mode

All modern browsers support running JavaScript in "Strict Mode".

You will learn more about how to use strict mode in a later section of this tutorial.

    Global variables are not created automatically in "Strict Mode".

### Global Variables in HTML

With JavaScript, the global scope is the complete JavaScript environment.

In HTML, the global scope is the window object. All global variables belong to the window object.

Exemplo

```javascript
var carName = "Volvo";

// code here can use window.carName
```

### Warning

    Do NOT create global variables unless you intend to.

    Your global variables (or functions) can overwrite window variables (or functions).
    Any function, including the window object, can overwrite your global variables and functions.

### The Lifetime of JavaScript Variables

The lifetime of a JavaScript variable starts when it is declared.

Local variables are deleted when the function is completed.

In a web browser, global variables are deleted when you close the browser window (or tab), but remain available to new pages loaded into the same window.

### Function Arguments

Function arguments (parameters) work as local variables inside functions.

## JavaScript Hoisting (https://www.w3schools.com/js/js_hoisting.asp)

Hoisting is JavaScript's default behavior of moving declarations to the top.

### JavaScript Declarations are Hoisted

In JavaScript, a variable can be declared after it has been used.

In other words; a variable can be used before it has been declared.

Exemplo 1 gives the same result as Exemplo 2:

Exemplo 1

```javascript
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element

var x; // Declare x
```

Exemplo 2

```javascript
var x; // Declare x
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element
```

To understand this, you have to understand the term "hoisting".

Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope \(to the top of the current script or the current function\).

### The **let** and **const** Keywords

Variables and constants declared with let or const are not hoisted!

### JavaScript Initializations are Not Hoisted

JavaScript only hoists declarations, not initializations.

Exemplo 1 does not give the same result as Exemplo 2:

Exemplo 1

```javascript
var x = 5; // Initialize x
var y = 7; // Initialize y

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y
```

Exemplo 2

```javascript
var x = 5; // Initialize x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

var y = 7; // Initialize y
```

Does it make sense that y is undefined in the last example?

This is because only the declaration (var y), not the initialization (=7) is hoisted to the top.

Because of hoisting, y has been declared before it is used, but because initializations are not hoisted, the value of y is undefined.

Exemplo 2 is the same as writing:

Exemplo

```javascript
var x = 5; // Initialize x
var y;     // Declare y

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

y = 7;    // Assign 7 to y
```

### Declare Your Variables At the Top !

Hoisting is \(to many developers\) an unknown or overlooked behavior of JavaScript.

If a developer doesn't understand hoisting, programs may contain bugs \(errors\).

To avoid bugs, always declare all variables at the beginning of every scope.

Since this is how JavaScript interprets the code, it is always a good rule.

    JavaScript in strict mode does not allow variables to be used if they are not declared.

## JavaScript Use Strict (https://www.w3schools.com/js/js_strict.asp)

"use strict"; Defines that JavaScript code should be executed in "strict mode".

### The "use strict" Directive

The "use strict" directive was new in ECMAScript version 5.

It is not a statement, but a literal expression, ignored by earlier versions of JavaScript.

The purpose of "use strict" is to indicate that the code should be executed in "strict mode".

With strict mode, you can not, for example, use undeclared variables.

All modern browsers support "use strict" except Internet Explorer 9 and lower.

    You can use strict mode in all your programs. It helps you to write cleaner code, like preventing you from using undeclared variables.

    "use strict" is just a string, so IE 9 will not throw an error even if it does not understand it.

### Declaring Strict Mode

Strict mode is declared by adding "use strict"; to the beginning of a script or a function.

Declared at the beginning of a script, it has global scope \(all code in the script will execute in strict mode\):

Exemplo

```javascript
"use strict";
x = 3.14;       // This will cause an error because x is not declared
```

Exemplo

```javascript
"use strict";
myFunction();

function myFunction() {
  y = 3.14;   // This will also cause an error because y is not declared
}
```

Declared inside a function, it has local scope (only the code inside the function is in strict mode):

```javascript
x = 3.14;       // This will not cause an error.
myFunction();

function myFunction() {
  "use strict";
  y = 3.14;   // This will cause an error
}
```

### The "use strict"; Syntax

The syntax, for declaring strict mode, was designed to be compatible with older versions of JavaScript.

Compiling a numeric literal (4 + 5;) or a string literal ("John Doe";) in a JavaScript program has no side effects. It simply compiles to a non existing variable and dies.

So "use strict"; only matters to new compilers that "understand" the meaning of it.

### Why Strict Mode?

Strict mode makes it easier to write "secure" JavaScript.

Strict mode changes previously accepted "bad syntax" into real errors.

As an example, in normal JavaScript, mistyping a variable name creates a new global variable. In strict mode, this will throw an error, making it impossible to accidentally create a global variable.

In normal JavaScript, a developer will not receive any error feedback assigning values to non-writable properties.

In strict mode, any assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object, will throw an error.

### Not Allowed in Strict Mode

Using a variable, without declaring it, is not allowed:

```javascript
"use strict";
x = 3.14;                // This will cause an error
```

Objects are variables too.

Using an object, without declaring it, is not allowed:

```javascript
"use strict";
x = {p1:10, p2:20};      // This will cause an error
```

Deleting a variable (or object) is not allowed.

```javascript
"use strict";
var x = 3.14;
delete x;                // This will cause an error
```

Deleting a function is not allowed.

```javascript
"use strict";
function x(p1, p2) {};
delete x;                // This will cause an error
```

Duplicating a parameter name is not allowed:

```javascript
"use strict";
function x(p1, p1) {};   // This will cause an error
```

Octal numeric literals are not allowed:

```javascript
"use strict";
var x = 010;             // This will cause an error
```

Octal escape characters are not allowed:

```javascript
"use strict";
var x = "\010";            // This will cause an error
```

Writing to a read-only property is not allowed:

```javascript
"use strict";
var obj = {};
Object.defineProperty(obj, "x", {value:0, writable:false});

obj.x = 3.14;            // This will cause an error
```

Writing to a get-only property is not allowed:

```javascript
"use strict";
var obj = {get x() {return 0} };

obj.x = 3.14;            // This will cause an error
```

Deleting an undeletable property is not allowed:

```javascript
"use strict";
delete Object.prototype; // This will cause an error
```

The string "eval" cannot be used as a variable:

```javascript
"use strict";
var eval = 3.14;         // This will cause an error
```

The string "arguments" cannot be used as a variable:

```javascript
"use strict";
var arguments = 3.14;    // This will cause an error
```

The with statement is not allowed:

```javascript
"use strict";
with (Math){x = cos(2)}; // This will cause an error
```

For security reasons, eval\(\) is not allowed to create variables in the scope from which it was called:

```javascript
"use strict";
eval ("var x = 2");
alert (x);             // This will cause an error
```

In function calls like f\(\), the this value was the global object. In strict mode, it is now undefined.

### Future Proof!
Keywords reserved for future JavaScript versions can NOT be used as variable names in strict mode.

These are:

  * implements
  * interface
  * let
  * package
  * private
  * protected
  * public
  * static
  * yield

    **Watch Out!**
    The "use strict" directive is only recognized at the beginning of a script or a function.

## The JavaScript this Keyword (https://www.w3schools.com/js/js_this.asp)

Exemplo

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

### What is **this**?

The JavaScript **this** keyword refers to the object it belongs to.

It has different values depending on where it is used:

  In a method, this refers to the **owner object**.
  Alone, this refers to the **global object**.
  In a function, this refers to the **global object**.
  In a function, in strict mode, this is **undefined**.
  In an event, this refers to the **element** that received the event.
  Methods like call(), and apply() can refer this to **any object**.

#### this in a Method

In an object method, this refers to the "owner" of the method.

In the example on the top of this section, this refers to the person object.

The person object is the owner of the fullName method.

```javascript
fullName : function() {
  return this.firstName + " " + this.lastName;
}
```

### this Alone

When used alone, the owner is the Global object, so this refers to the Global object.

In a browser window the Global object is \[object Window\]:

Exemplo

```javascript
var x = this;
```

In strict mode, when used alone, this also refers to the Global object \[object Window\]:

Exemplo

```javascript
"use strict";
var x = this;
```

### this in a Function \(Default\)

In a JavaScript function, the owner of the function is the default binding for this.

So, in a function, this refers to the Global object \[object Window\].

Exemplo

```javascript
function myFunction() {
  return this;
}
```

### this in a Function \(Strict\)

JavaScript strict mode does not allow default binding.

So, when used in a function, in strict mode, this is undefined.

Exemplo

```javascript
"use strict";
function myFunction() {
  return this;
}
```

### this in Event Handlers

In HTML event handlers, this refers to the HTML element that received the event:

Exemplo

```html
<button onclick="this.style.display='none'">
  Click to Remove Me!
</button>
```

### Object Method Binding

In these examples, this is the person object \(The person object is the "owner" of the function\):

Exemplo

```javascript
var person = {
  firstName  : "John",
  lastName   : "Doe",
  id         : 5566,
  myFunction : function() {
    return this;
  }
};
```

Exemplo

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

In other words: this.firstName means the firstName property of this (person) object.

### Explicit Function Binding

The call\(\) and apply\(\) methods are predefined JavaScript methods.

They can both be used to call an object method with another object as argument.

You can read more about call() and apply() later in this tutorial.

In the example below, when calling person1.fullName with person2 as argument, this will refer to person2, even if it is a method of person1:

Exemplo

```javascript
var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
person1.fullName.call(person2);  // Will return "John Doe"
```

## JavaScript Let (https://www.w3schools.com/js/js_let.asp)

### ECMAScript 2015

ES2015 introduced two important new JavaScript keywords: let and const.

These two keywords provide Block Scope variables \(and constants\) in JavaScript.

Before ES2015, JavaScript had only two types of scope: Global Scope and Function Scope.

### Global Scope

Variables declared Globally \(outside any function\) have Global Scope.

Exemplo

```javascript
var carName = "Volvo";

// code here can use carName

function myFunction() {
  // code here can also use carName
}
```

Global variables can be accessed from anywhere in a JavaScript program.

### Function Scope

Variables declared **Locally** (inside a function) have **Function Scope**.

Exemplo

```javascript
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```

Local variables can only be accessed from inside the function where they are declared.

### JavaScript Block Scope

Variables declared with the **var** keyword can not have Block Scope.

Variables declared inside a block {} can be accessed from outside the block.

Exemplo

```javascript
{
  var x = 2;
}
// x CAN be used here
```

Before ES2015 JavaScript did not have **Block Scope**.

Variables declared with the let keyword can have Block Scope.

Variables declared inside a block {} can not be accessed from outside the block:

Exemplo

```javascript
{
  let x = 2;
}
// x can NOT be used here
```

### Redeclaring Variables

Redeclaring a variable using the var keyword can impose problems.

Redeclaring a variable inside a block will also redeclare the variable outside the block:

Exemplo

```javascript
var x = 10;
// Here x is 10
{
  var x = 2;
  // Here x is 2
}
// Here x is 2
```

Redeclaring a variable using the let keyword can solve this problem.

Redeclaring a variable inside a block will not redeclare the variable outside the block:

Exemplo

```javascript
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
```

### Loop Scope

Using var in a loop:

Exemplo

```javascript
var i = 5;
for (var i = 0; i < 10; i++) {
  // some statements
}
// Here i is 10
```

Using let in a loop:

Exemplo

```javascript
let i = 5;
for (let i = 0; i < 10; i++) {
  // some statements
}
// Here i is 5
```

In the first example, using var, the variable declared in the loop redeclares the variable outside the loop.

In the second example, using let, the variable declared in the loop does not redeclare the variable outside the loop.

When let is used to declare the i variable in a loop, the i variable will only be visible within the loop.

### Function Scope

Variables declared with var and let are quite similar when declared inside a function.

They will both have Function Scope:

```javascript
function myFunction() {
  var carName = "Volvo";   // Function Scope
}
function myFunction() {
  let carName = "Volvo";   // Function Scope
}
```

### Global Scope

Variables declared with var and let are quite similar when declared outside a block.

They will both have Global Scope:

```javascript
var x = 2;       // Global scope
let x = 2;       // Global scope
```

### Global Variables in HTML

With JavaScript, the global scope is the JavaScript environment.

In HTML, the global scope is the window object.

Global variables defined with the var keyword belong to the window object:

Exemplo

```javascript
var carName = "Volvo";
// code here can use window.carName
```

Global variables defined with the let keyword do not belong to the window object:

Exemplo

```javascript
let carName = "Volvo";
// code here can not use window.carName
```

### Redeclaring

Redeclaring a JavaScript variable with var is allowed anywhere in a program:

Exemplo

```javascript
var x = 2;

// Now x is 2

var x = 3;

// Now x is 3
```

Redeclaring a var variable with let, in the same scope, or in the same block, is not allowed:

Exemplo
```javascript
var x = 2;       // Allowed
let x = 3;       // Not allowed

{
  var x = 4;   // Allowed
  let x = 5   // Not allowed
}
```

Redeclaring a let variable with let, in the same scope, or in the same block, is not allowed:

Exemplo
```javascript
let x = 2;       // Allowed
let x = 3;       // Not allowed

{
  let x = 4;   // Allowed
  let x = 5;   // Not allowed
}
```

Redeclaring a let variable with var, in the same scope, or in the same block, is not allowed:

Exemplo
```javascript
let x = 2;       // Allowed
var x = 3;       // Not allowed

{
  let x = 4;   // Allowed
  var x = 5;   // Not allowed
}
```

Redeclaring a variable with let, in another scope, or in another block, is allowed:

Exemplo
```javascript
let x = 2;       // Allowed

{
  let x = 3;   // Allowed
}

{
  let x = 4;   // Allowed
}
```

### Hoisting

Variables defined with var are hoisted to the top.

You can use a variable before it is declared:

Exemplo

```javascript
// you CAN use carName here
var carName;
Variables defined with let are not hoisted to the top.
```

Using a let variable before it is declared will result in a ReferenceError.

The variable is in a "temporal dead zone" from the start of the block until it is declared:

Exemplo

```javascript
// you can NOT use carName here
let carName;
```

## JavaScript Const (https://www.w3schools.com/js/js_const.asp)

### ECMAScript 2015

ES2015 intoduced two important new JavaScript keywords: let and const.

Variables defined with const behave like let variables, except they cannot be reassigned:

Exemplo

```javascript
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

### Block Scope

Declaring a variable with const is similar to let when it comes to Block Scope.

The x declared in the block, in this example, is not the same as the x declared outside the block:

Exemplo

```javascript
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
}
// Here x is 10
```

### Assigned when Declared

JavaScript const variables must be assigned a value when they are declared:

#### Incorrect

```javascript
const PI;
PI = 3.14159265359;
```

#### Correct

```javascript
const PI = 3.14159265359;
```

### Not Real Constants

The keyword **const** is a little misleading.

It does NOT define a constant value. It defines a constant reference to a value.

Because of this, we cannot change constant primitive values, but we can change the properties of constant objects.

### Primitive Values

If we assign a primitive value to a constant, we cannot change the primitive value:

Exemplo

```javascript
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

### Constant Objects can Change

You can change the properties of a constant object:

Exemplo

```javascript
// You can create a const object:
const car = {type:"Fiat", model:"500", color:"white"};

// You can change a property:
car.color = "red";

// You can add a property:
car.owner = "Johnson";
```

But you can NOT reassign a constant object:

Exemplo

```javascript
const car = {type:"Fiat", model:"500", color:"white"};
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

### Constant Arrays can Change

You can change the elements of a constant array:

Exemplo

```javascript
// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";

// You can add an element:
cars.push("Audi");
```

### Hoisting

Variables defined with var are hoisted to the top.

You can use a var variable before it is declared:

Exemplo

```javascript
carName = "Volvo";    // You CAN use carName here
var carName;
```

Variables defined with const are not hoisted to the top.

A const variable cannot be used before it is declared

Exemplo

```javascript
carName = "Volvo";    // You can NOT use carName here
const carName = "Volvo";
```

[Próxima unidade](fundamentos4_js.md)
