# Fundamentos II de JavaScript

Esta é a continuação de [Fundamentos de JS](fundamento_js.md).

## Tipos de Dados em JavaScript [JS Data Types](https://www.w3schools.com/js/js_datatypes.asp)

Variáveis de JavaScript podem armazenar muitos tipos de dados: números, strings, objetos e mais:

```javascript
var comprimento = 16;                                    // Número
var ultimoNome = "Almeida";                              // String
var x = {primeiroNome:"João", ultimoNome:"Carvalho"};    // Objeto
```

### O Conceito de Tipos de Dados

Em programação, tipos de dados é um conceito importante.

To be able to operate on variables, it is important to know something about the type.

Without data types, a computer cannot safely solve this:

```javascript
var x = 16 + "Volvo";
```

JavaScript evaluates expressions from left to right. Different sequences can produce different results:

```javascript
var x = 16 + 4 + "Volvo";    // == "20Volvo" -- is different of
var y = "Volvo" + 16 + 4;    // == "Volvo164"
```

### JavaScript Types are Dynamic

JavaScript has dynamic types. This means that the same variable can be used to hold different data types:

```javascript
var x;           // Now x is *undefined*
x = 5;           // Now x is a Number
x = "John";      // Now x is a String
```

### JavaScript Strings

A string (or a text string) is a series of characters like "John Doe".

Strings are written with quotes. You can use single or double quotes:

```javascript
var carName = "Volvo XC60";   // Using double quotes
var carName = 'Volvo XC60';   // Using single quotes
var answer = "It's alright";             // Single quote inside double quotes
var answer = "He is called 'Johnny'";    // Single quotes inside double quotes
var answer = 'He is called "Johnny"';    // Double quotes inside single quotes
```

### JavaScript Numbers

JavaScript has only one type of numbers.

Numbers can be written with, or without decimals:

```javascript
var x1 = 34.00;     // Written with decimals
var x2 = 34;        // Written without decimals
```

Extra large or extra small numbers can be written with scientific (exponential) notation:

```javascript
var y = 123e5;      // 12300000
var z = 123e-5;     // 0.00123
```

### JavaScript Booleans

Booleans can only have two values: true or false.

```javascript
var x = 5;
var y = 5;
var z = 6;
(x == y)       // Returns true
(x == z)       // Returns false
```

Booleans are often used in conditional testing.

### JavaScript arrays are written with square brackets.

Array items are separated by commas.

The following code declares (creates) an array called cars, containing three items (car names):

```javascript
var cars = ["Saab", "Volvo", "BMW"];
```

Array indexes are zero-based, which means the first item is [0], second is [1], and so on.

### JavaScript Objects

JavaScript objects are written with curly braces.

Object properties are written as name:value pairs, separated by commas.

```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.

### The typeof Operator

You can use the JavaScript typeof operator to find the type of a JavaScript variable.

The typeof operator returns the type of a variable or an expression:

```javascript
typeof ""                  // Returns "string"
typeof "John"              // Returns "string"
typeof "John Doe"          // Returns "string"
```

### Undefined

In JavaScript, a variable without a value, has the value undefined. The type is also undefined.

```javascript
car = undefined;        // Value is undefined, type is undefined
```

### Empty Values

An empty value has nothing to do with undefined.

An empty string has both a legal value and a type.

```javascript
var car = "";              // The value is "", the typeof is "string"
```

    You can consider it a bug in JavaScript that typeof null is an object. It should be null.

### Difference Between Undefined and Null

Undefined and null are equal in value but different in type:

```javascript
typeof undefined           // undefined
typeof null                // object

null === undefined         // false
null == undefined          // true
```

### Primitive Data

A primitive data value is a single simple data value with no additional properties and methods.

The typeof operator can return one of these primitive types:

* string
* number
* boolean
* undefined

```javascript
typeof "John"              // Returns "string"
typeof 3.14                // Returns "number"
typeof true                // Returns "boolean"
typeof false               // Returns "boolean"
typeof x                   // Returns "undefined" (if x has no value)
```

### Complex Data

The typeof operator can return one of two complex types:

* function
* object

The typeof operator returns object for both objects, arrays, and null.

The typeof operator does not return object for functions.

```javascript
typeof {name:'John', age:34} // Returns "object"
typeof [1,2,3,4]             // Returns "object" (not "array", see note below)
typeof null                  // Returns "object"
typeof function myFunc(){}   // Returns "function"
```

    The typeof operator returns "object" for arrays because in JavaScript arrays are objects.

## JavaScript Functions (https://www.w3schools.com/js/js_functions.asp)

A JavaScript function is a block of code designed to perform a particular task.

A JavaScript function is executed when "something" invokes it (calls it).

```javascript
function myFunction(p1, p2) {
  return p1 * p2;    // The function returns the product of p1 and p2
}
```

### JavaScript Function Syntax

A JavaScript function is defined with the **function** keyword, followed by a name, followed by parentheses \(\).

Function names can contain letters, digits, underscores, and dollar signs \(same rules as variables\).

The parentheses may include parameter names separated by commas:
**\(parameter1, parameter2, ...\)**

The code to be executed, by the function, is placed inside curly brackets: \{\}

```javascript
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

Function **parameters** are listed inside the parentheses \(\) in the function definition.

Function **arguments** are the **values** received by the function when it is invoked.

Inside the function, the arguments \(the parameters\) behave as local variables.

    A Function is much the same as a Procedure or a Subroutine, in other programming languages.

### Function Invocation

The code inside the function will execute when "something" invokes \(calls\) the function:

  * When an event occurs \(when a user clicks a button\)
  * When it is invoked \(called\) from JavaScript code
  * Automatically \(self invoked\)

### Function Return

When JavaScript reaches a **return statement**, the function will stop executing.

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

Functions often compute a return value. The **return value** is "returned" back to the "caller".

Example: Calculate the sum of two number and return it.

```javascript
var x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```

### Why Functions?

You can reuse code: Define the code once, and use it many times.

You can use the same code many times with different arguments, to produce different results.

Example: Convert Fahrenheit to Celsius: (funct_demo1.html)

```javascript
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius(77);
```

### The () Operator Invokes the Function
Using the example above, toCelsius refers to the function object, and toCelsius() refers to the function result.

Accessing a function without () will return the function definition instead of the function result: (funct_demo2.html)

```javascript
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius;
```

### Functions Used as Variable Values

Functions can be used the same way as you use variables, in all types of formulas, assignments, and calculations.

```javascript
var text = "The temperature is " + toCelsius(77) + " Celsius";
```

### Local Variables

Variables declared within a JavaScript function, become **LOCAL** to the function.

Local variables can only be accessed from within the function.

```javascript
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```

Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.

## JavaScript Objects (https://www.w3schools.com/js/js_objects.asp)

### Real Life Objects, Properties, and Methods

In real life, a car is an **object**.

A car has properties like weight and color, and methods like start and stop:

![Object Explained](images/objectExplained.gif)

All cars have the same properties, but the property values differ from car to car.

All cars have the same methods, but the methods are performed at different times.

### JavaScript Objects

You have already learned that JavaScript variables are containers for data values.

This code assigns a simple value (Fiat) to a variable named car:

```javascript
var car = "Fiat";
```

Objects are variables too. But objects can contain many values.

This code assigns many values (Fiat, 500, white) to a variable named car:

```javascript
var car = {type:"Fiat", model:"500", color:"white"};
```

The values are written as name:value pairs (name and value separated by a colon).

    JavaScript objects are containers for named values called properties or methods.

### Object Definition

You define (and create) a JavaScript object with an object literal:

```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

### Object Properties

The name:values pairs in JavaScript objects are called properties:

Property  | Property Value
---------------------------
firstName | John
lastName  | Doe
age       | 50
eyeColor  | blue

## Accessing Object Properties

You can access object properties in two ways:

```javascript
objectName.propertyName
```

or

```javascript
objectName["propertyName"]
```

### Object Methods

Objects can also have methods.

Methods are actions that can be performed on objects.

Methods are stored in properties as function definitions.

Property  | Property Value
---------------------------
firstName | John
lastName  | Doe
age       | 50
eyeColor  | blue
fullName  | function() {return this.firstName + " " + this.lastName;}

    A method is a function stored as a property.

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

### The this Keyword

In a function definition, this refers to the "owner" of the function.

In the example above, this is the person object that "owns" the fullName function.

In other words, this.firstName means the firstName property of this object.

### Accessing Object Methods

You access an object method with the following syntax:

```javascript
objectName.methodName()
```

Example: (obj_demo1.html)

### **Do Not** Declare Strings, Numbers, and Booleans as Objects!

When a JavaScript variable is declared with the keyword "new", the variable is created as an object:

```javascript
var x = new String();        // Declares x as a String object
var y = new Number();        // Declares y as a Number object
var z = new Boolean();       // Declares z as a Boolean object
```

    Avoid String, Number, and Boolean objects. They complicate your code and slow down execution speed.

## JavaScript Events (https://www.w3schools.com/js/js_events.asp)

HTML events are "things" that happen to HTML elements.

When JavaScript is used in HTML pages, JavaScript can "react" on these events.

### HTML Events

An HTML event can be something the browser does, or something a user does.

Here are some examples of HTML events:

  * An HTML web page has finished loading
  * An HTML input field was changed
  * An HTML button was clicked
  * Often, when events happen, you may want to do something.

JavaScript lets you execute code when events are detected.

HTML allows event handler attributes, with JavaScript code, to be added to HTML elements.

With single quotes:

```html
<element event='some JavaScript'>
```

With double quotes:

```html
<element event="some JavaScript">
```

In the following example, an onclick attribute (with code), is added to a button element: (ev_demo1.html)

```html
<button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button>
```

    JavaScript code is often several lines long. It is more common to see event attributes calling functions: (ev.demo2.html)

```javascript
<button onclick="displayDate()">The time is?</button>
```

### Common HTML Events

Here is a list of some common HTML events:

Event       | Description
----------------------------------------------------------------------
onchange    | An HTML element has been changed
onclick     | The user clicks an HTML element
onmouseover | The user moves the mouse over an HTML element
onmouseout  | The user moves the mouse away from an HTML element
onkeydown   | The user pushes a keyboard key
onload      | The browser has finished loading the page

A complete list of HTML events may be found on (https://www.w3schools.com/jsref/dom_obj_event.asp)

### What can JavaScript Do?

Event handlers can be used to handle, and verify, user input, user actions, and browser actions:

  * Things that should be done every time a page loads
  * Things that should be done when the page is closed
  * Action that should be performed when a user clicks a button
  * Content that should be verified when a user inputs data
  * And more ...

Many different methods can be used to let JavaScript work with events:

  * HTML event attributes can execute JavaScript code directly
  * HTML event attributes can call JavaScript functions
  * You can assign your own event handler functions to HTML elements
  * You can prevent events from being sent or being handled
  * And more ...

## JavaScript Strings (https://www.w3schools.com/js/js_strings.asp)

### JavaScript Strings

A JavaScript string is zero or more characters written inside quotes.

```javascript
var x = "John Doe";
```

### String Length

The length of a string is found in the built in property length:

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

### Special Characters

Because strings must be written within quotes, JavaScript will misunderstand this string:

```javascript
var x = "We are the so-called "Vikings" from the north.";
```

The string will be chopped to "We are the so-called ".

The solution to avoid this problem, is to use the backslash escape character.

The backslash (\\) escape character turns special characters into string characters:

Code | Result | Description
----------------------------
\\'  | '      | Single quote
\\"  | "      | Double quote
\\\\ | \\     | Backslash

The sequence \\"  inserts a double quote in a string:

```javascript
var x = "We are the so-called \"Vikings\" from the north.";
```

Six other escape sequences are valid in JavaScript:

Code | Result
--------------------------
\\b  | Backspace
\\f  | Form Feed
\\n  | New Line
\\r  | Carriage Return
\\t	 | Horizontal Tabulator
\\v  | Vertical Tabulator

    The 6 escape characters above were originally designed to control typewriters, teletypes, and fax machines. They do not make any sense in HTML.

### Breaking Long Code Lines

For best readability, programmers often like to avoid code lines longer than 80 characters.

If a JavaScript statement does not fit on one line, the best place to break it is after an operator:

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

You can also break up a code line within a text string with a single backslash:

```javascript
document.getElementById("demo").innerHTML = "Hello \
Dolly!";
```

    The \\ method is not the preferred method. It might not have universal support.
    Some browsers do not allow spaces behind the \\ character.

A safer way to break up a string, is to use string addition:

```javascript
document.getElementById("demo").innerHTML = "Hello " +
"Dolly!";
```

You **cannot break up** a code line with a backslash:

```javascript
document.getElementById("demo").innerHTML = \
"Hello Dolly!";
```

### Strings Can be Objects

Normally, JavaScript strings are primitive values, created from literals:

**var firstName = "John";**

But strings can also be defined as objects with the keyword new:

**var firstName = new String("John");**

```javascript
var x = "John";
var y = new String("John");

// typeof x will return string
// typeof y will return object
```

    Don't create strings as objects. It slows down execution speed.
    The new keyword complicates the code. This can produce some unexpected results:

```javascript
var x = "John";             
var y = new String("John");

// (x == y) is true because x and y have equal values
// (x === y) is false because x and y have different types (string and object)
```

When using the === operator, equal strings are not equal, because the === operator expects equality in both type and value.


Or even worse. Objects cannot be compared:

```javascript
var x = new String("John");             
var y = new String("John");

// (x == y) is false because x and y are different objects
// (x === y) is false because x and y are different objects
```

## JavaScript String Methods (https://www.w3schools.com/js/js_string_methods.asp)

## String Methods and Properties

Primitive values, like "John Doe", cannot have properties or methods \(because they are not objects\).

But with JavaScript, methods and properties are also available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

### String Length

The length property returns the length of a string:

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

### Finding a String in a String

The indexOf\(\) method returns the index of \(the position of\) the first occurrence of a specified text in a string: (str_demo1.html)

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
```

The lastIndexOf() method returns the index of the last occurrence of a specified text in a string:

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.lastIndexOf("locate");
```

Both indexOf\(\), and lastIndexOf\(\) return -1 if the text is not found.

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.lastIndexOf("John");
```

Both methods accept a second parameter as the starting position for the search: (str_demo3.html)

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate",15);
```

### Searching for a String in a String

The search\(\) method searches a string for a specified value and returns the position of the match:

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.search("locate");
```

The two methods, indexOf\(\) and search\(\), *are equal*?

They accept the same arguments \(parameters\), and return the same value?

The two methods are NOT equal. These are the differences:

  * The search\(\) method cannot take a second start position argument.
  * The indexOf\(\) method cannot take powerful search values \(regular expressions\).

### Extracting String Parts
There are 3 methods for extracting a part of a string:

  - slice\(start, end\)
  - substring\(start, end\)
  - substr\(start, length\)

#### The slice\(\) Method

slice\(\) extracts a part of a string and returns the extracted part in a new string.

The method takes 2 parameters: the start position, and the end position \(end not included\).

Example: (str_demo2.html)

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.slice(7, 13);
```

If a parameter is negative, the position is counted from the end of the string. (str_demo4.html)

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.slice(-12, -6);
```

If you omit the second parameter, the method will slice out the rest of the string:

```javascript
var res = str.slice(7);  // same as (in this case): var res = str.slice(-12);
```

    Negative positions do not work in Internet Explorer 8 and earlier.

#### The substring\(\) Method

**substring\(\)** is similar to slice\(\).

The difference is that substring() cannot accept negative indexes.

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.substring(7, 13);
```

#### The substr\(\) Method

**substr\(\)** is similar to slice\(\).

The difference is that the second parameter specifies the length of the extracted part.

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.substr(7, 6);
```

If you omit the second parameter, substr() will slice out the rest of the string.

#### Replacing String Content

The replace() method replaces a specified value with another value in a string:

```javascript
str = "Please visit Microsoft!";
var n = str.replace("Microsoft", "W3Schools");
```

    The replace\(\) method does not change the string it is called on. It returns a new string.

To replace case insensitive, use a regular expression with an /i flag \(insensitive\):

```javascript
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3Schools");
```

    Note that regular expressions are written without quotes.

To replace all matches, use a regular expression with a /g flag \(global match\):

```javascript
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3Schools");
```

#### Converting to Upper and Lower Case

A string is converted to upper case with toUpperCase\(\):

```javascript
var text1 = "Hello World!";       // String
var text2 = text1.toUpperCase();  // text2 is text1 converted to upper
```

A string is converted to lower case with toLowerCase():

```javascript
var text1 = "Hello World!";       // String
var text2 = text1.toLowerCase();  // text2 is text1 converted to lower
```

#### The concat\(\) Method

concat\(\) joins two or more strings:

```javascript
var text1 = "Hello";
var text2 = "World";
var text3 = text1.concat(" ", text2);
```

The concat() method can be used instead of the plus operator. These two lines do the same:

```javascript
var text = "Hello" + " " + "World!";
var text = "Hello".concat(" ", "World!");
```

    All string methods return a new string. They don't modify the original string.
    Formally said: Strings are immutable: Strings cannot be changed, only replaced.

#### String.trim\(\)

String.trim\(\) removes whitespace from both sides of a string.

```javascript
var str = "       Hello World!        ";
alert(str.trim());
```

    String.trim() is not supported in Internet Explorer 8 or lower.

If you need to support IE 8, you can use String.replace with a regular expression instead:

```javascript
var str = "       Hello World!        ";
alert(str.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, ''));
```

### Extracting String Characters

There are 3 methods for extracting string characters:

  * charAt\(position\)
  * charCodeAt(position)
  * Property access \[ \]

#### The charAt\(\) Method

The charAt\(\) method returns the character at a specified index \(position\) in a string:

```javascript
var str = "HELLO WORLD";
str.charAt(0);            // returns H
```

#### The charCodeAt\(\) Method

The charCodeAt\(\) method returns the unicode of the character at a specified index in a string:

The method returns a UTF-16 code \(an integer between 0 and 65535\).

```javascript
var str = "HELLO WORLD";

str.charCodeAt(0);         // returns 72
```

#### Property Access

ECMAScript 5 \(2009\) allows property access \[ \] on strings:

```javascript
var str = "HELLO WORLD";
str[0];                   // returns H
```

    Property access might be a little unpredictable:

    * It does not work in Internet Explorer 7 or earlier
    * It makes strings look like arrays (but they are not)
    * If no character is found, [ ] returns undefined, while charAt() returns an empty string.
    * It is read only. str[0] = "A" gives no error (but does not work!)

    If you want to work with a string as an array, you can convert it to an array.

#### Converting a String to an Array

A string can be converted to an array with the split() method:

```javascript
var txt = "a,b,c,d,e";   // String
txt.split(",");          // Split on commas
txt.split(" ");          // Split on spaces
txt.split("|");          // Split on pipe
```

If the separator is "", the returned array will be an array of single characters:

```javascript
var txt = "Hello";       // String
txt.split("");           // Split in characters
```

For a complete reference on JavaScript strings see (https://www.w3schools.com/jsref/jsref_obj_string.asp).

## JavaScript Numbers (https://www.w3schools.com/js/js_numbers.asp)

JavaScript has only one type of number. Numbers can be written with or without decimals.

```javascript
var x = 3.14;    // A number with decimals
var y = 3;       // A number without decimals
```

### JavaScript Numbers are Always 64-bit Floating Point

Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc.

JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.

This format stores numbers in 64 bits, where the number (the fraction) is stored in bits 0 to 51, the exponent in bits 52 to 62, and the sign in bit 63:

Value (aka Fraction/Mantissa) | Exponent          | Sign
--------------------------------------------------------------
52 bits (0 - 51)              | 11 bits (52 - 62) | 1 bit (63)

### Precision

Integers (numbers without a period or exponent notation) are accurate up to 15 digits.

```javascript
var x = 999999999999999;   // x will be 999999999999999
var y = 9999999999999999;  // y will be 10000000000000000
```

The maximum number of decimals is 17, but floating point arithmetic is not always 100% accurate:

```javascript
var x = 0.2 + 0.1;         // x will be 0.30000000000000004
```

To solve the problem above, it helps to multiply and divide:

```javascript
var x = (0.2 * 10 + 0.1 * 10) / 10;       // x will be 0.3
```

### Adding Numbers and Strings

    WARNING !!
    JavaScript uses the \+ operator for both addition and concatenation.
    Numbers are added. Strings are concatenated.

If you add two numbers, the result will be a number, if you add two strings, the result will be string:

```javascript
var x = 10;
var y = 20;
var z = x + y;           // z will be 30 (a number)
var x = 10;
var y = "20";
var z = x + y;           // z will be 1020 (a string)
```

A common mistake is to expect this result to be 102030:

```javascript
var x = 10;
var y = 20;
var z = "30";
var result = x + y + z;  // z will be "3030"
```

### Numeric Strings

JavaScript strings can have numeric content:

```javascript
var x = 100;         // x is a number

var y = "100";       // y is a string
```

JavaScript will try to convert strings to numbers in all numeric operations:

This will work:

```javascript
var x = "100";
var y = "10";
var z = x / y;       // z will be 10
```

This will also work:

```javascript
var x = "100";
var y = "10";
var z = x * y;       // z will be 1000
```

But this will not work:

```javascript
var x = "100";
var y = "10";
var z = x + y;       // z will not be 110 (It will be 10010)
```

    In the last example JavaScript uses the + operator to concatenate the strings.

### NaN - Not a Number

**NaN** is a JavaScript reserved word indicating that a number is not a legal number.

Trying to do arithmetic with a non-numeric string will result in NaN (Not a Number):

```javascript
var x = 100 / "Apple";  // x will be NaN (Not a Number)
```
However, if the string contains a numeric value , the result will be a number:

```javascript
var x = 100 / "10";     // x will be 10
```

You can use the global JavaScript function isNaN() to find out if a value is a number:

```javascript
var x = 100 / "Apple";
isNaN(x);               // returns true because x is Not a Number
```

Watch out for NaN. If you use NaN in a mathematical operation, the result will also be NaN:

```javascript
var x = NaN;
var y = 5;
var z = x + y;         // z will be NaN
```

Or the result might be a concatenation:

```javascript
var x = NaN;
var y = "5";
var z = x + y;         // z will be NaN5
```

NaN is a number: typeof NaN returns number:

```javascript
typeof NaN;            // returns "number"
```

### Infinity

Infinity \(or -Infinity\) is the value JavaScript will return if you calculate a number outside the largest possible number.

```javascript
var myNumber = 2;
while (myNumber != Infinity) {          // Execute until Infinity
  myNumber = myNumber * myNumber;
}
```

### Division by 0 \(zero\) also generates Infinity:

```javascript
var x =  2 / 0;          // x will be Infinity
var y = -2 / 0;          // y will be -Infinity
```

Infinity is a number: typeof Infinity returns number.

```javascript
typeof Infinity;        // returns "number"
```

### Hexadecimal

JavaScript interprets numeric constants as hexadecimal if they are preceded by 0x.

```javascript
var x = 0xFF;           // x will be 255
```

    Never write a number with a leading zero (like 07).
    Some JavaScript versions interpret numbers as octal if they are written with a leading zero.

By default, JavaScript displays numbers as base 10 decimals.

But you can use the toString() method to output numbers from base 2 to base 36.

Hexadecimal is base 16. Decimal is base 10. Octal is base 8. Binary is base 2.

```javascript
var myNumber = 32;
myNumber.toString(10);  // returns 32
myNumber.toString(32);  // returns 10
myNumber.toString(16);  // returns 20
myNumber.toString(8);   // returns 40
myNumber.toString(2);   // returns 100000
```

### Numbers Can be Objects

Normally JavaScript numbers are primitive values created from literals:

```javascript
var x = 123;
```

But numbers can also be defined as objects with the keyword new:

```javascript
var y = new Number(123);
```

```javascript
var x = 123;
var y = new Number(123);

// typeof x returns number
// typeof y returns object
```

    Do not create Number objects. It slows down execution speed.
    The new keyword complicates the code. This can produce some unexpected results:

When using the == operator, equal numbers are equal:

```javascript
var x = 500;             
var y = new Number(500);

// (x == y) is true because x and y have equal values
// (x === y) is false because x and y have different types
```

When using the === operator, equal numbers are not equal, because the === operator expects equality in both type and value.

## JavaScript Number Methods (https://www.w3schools.com/js/js_number_methods.asp)

### Number Methods and Properties
Primitive values (like 3.14 or 2014), cannot have properties and methods (because they are not objects).

But with JavaScript, methods and properties are also available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

### The toString\(\) Method

toString\(\) returns a number as a string.

All number methods can be used on any type of numbers \(literals, variables, or expressions\):

```javascript
var x = 123;
x.toString();            // returns 123 from variable x
(123).toString();        // returns 123 from literal 123
(100 + 23).toString();   // returns 123 from expression 100 + 23
```

### The toExponential\(\) Method

toExponential\(\) returns a string, with a number rounded and written using exponential notation.

A parameter defines the number of characters behind the decimal point:

```javascript
var x = 9.656;
x.toExponential(2);     // returns 9.66e+0
x.toExponential(4);     // returns 9.6560e+0
x.toExponential(6);     // returns 9.656000e+0
```

The parameter is optional. If you don't specify it, JavaScript will not round the number.

### The toFixed\(\) Method

toFixed\(\) returns a string, with the number written with a specified number of decimals:

```javascript
var x = 9.656;
x.toFixed(0);           // returns 10
x.toFixed(2);           // returns 9.66
x.toFixed(4);           // returns 9.6560
x.toFixed(6);           // returns 9.656000
```

    toFixed(2) is perfect for working with money.

### The toPrecision\(\) Method
toPrecision\(\) returns a string, with a number written with a specified length:

```javascript
var x = 9.656;
x.toPrecision();        // returns 9.656
x.toPrecision(2);       // returns 9.7
x.toPrecision(4);       // returns 9.656
x.toPrecision(6);       // returns 9.65600
```

### The valueOf\(\) Method

valueOf\(\) returns a number as a number.

```javascript
var x = 123;
x.valueOf();            // returns 123 from variable x
(123).valueOf();        // returns 123 from literal 123
(100 + 23).valueOf();   // returns 123 from expression 100 + 23
```

In JavaScript, a number can be a primitive value \(typeof = number\) or an object \(typeof = object\).

The valueOf\(\) method is used internally in JavaScript to convert Number objects to primitive values.

There is no reason to use it in your code.

    All JavaScript data types have a valueOf() and a toString() method.

### Converting Variables to Numbers

There are 3 JavaScript methods that can be used to convert variables to numbers:

  * The Number\(\) method
  * The parseInt\(\) method
  * The parseFloat\(\) method

These methods are not number methods, but global JavaScript methods.

### Global JavaScript Methods

JavaScript global methods can be used on all JavaScript data types.

These are the most relevant methods, when working with numbers:

Method          | Description
--------------------------------------------------------------------------
Number\(\)      | Returns a number, converted from its argument.
parseFloat\(\)  | Parses its argument and returns a floating point number
parseInt\(\)    | Parses its argument and returns an integer

#### The Number\(\) Method

Number\(\) can be used to convert JavaScript variables to numbers:

```javascript
Number(true);          // returns 1
Number(false);         // returns 0
Number("10");          // returns 10
Number("  10");        // returns 10
Number("10  ");        // returns 10
Number(" 10  ");       // returns 10
Number("10.33");       // returns 10.33
Number("10,33");       // returns NaN
Number("10 33");       // returns NaN
Number("John");        // returns NaN
```

    If the number cannot be converted, NaN (Not a Number) is returned.

#### The Number\(\) Method Used on Dates

Number\(\) can also convert a date to a number:

```javascript
Number(new Date("2017-09-30"));    // returns 1506729600000
```

    The Number() method above returns the number of milliseconds since 1.1.1970.

#### The parseInt\(\) Method

parseInt\(\) parses a string and returns a whole number. Spaces are allowed. Only the first number is returned:

```javascript
parseInt("10");         // returns 10
parseInt("10.33");      // returns 10
parseInt("10 20 30");   // returns 10
parseInt("10 years");   // returns 10
parseInt("years 10");   // returns NaN
```

If the number cannot be converted, NaN (Not a Number) is returned.

#### The parseFloat\(\) Method

parseFloat\(\) parses a string and returns a number. Spaces are allowed. Only the first number is returned:

```javascript
parseFloat("10");        // returns 10
parseFloat("10.33");     // returns 10.33
parseFloat("10 20 30");  // returns 10
parseFloat("10 years");  // returns 10
parseFloat("years 10");  // returns NaN
```

### Number Properties

Property           | Description
-------------------------------------------------------------------------------
MAX_VALUE          | Returns the largest number possible in JavaScript
MIN_VALUE          | Returns the smallest number possible in JavaScript
POSITIVE_INFINITY  | Represents infinity (returned on overflow)
NEGATIVE_INFINITY  | Represents negative infinity (returned on overflow)
NaN                | Represents a "Not-a-Number" value

#### JavaScript MIN_VALUE and MAX_VALUE

Example: (num_demo1.html)

```javascript
var x = Number.MAX_VALUE;
var y = Number.MIN_VALUE;
```

#### JavaScript POSITIVE_INFINITY

```javascript
var x = Number.POSITIVE_INFINITY;
```

POSITIVE_INFINITY is returned on overflow:

```javascript
var x = 1 / 0;
```

#### JavaScript NEGATIVE_INFINITY

```javascript
var x = Number.NEGATIVE_INFINITY;
// NEGATIVE_INFINITY is returned on overflow:
var y = -1 / 0;
```

#### JavaScript NaN - Not a Number

```javascript
var x = Number.NaN;
// Trying to do arithmetic with a non-numeric string will result in NaN (Not a Number):
var x = 100 / "Apple";  // x will be NaN (Not a Number)
```

#### Number Properties Cannot be Used on Variables

Number properties belongs to the JavaScript's number object wrapper called Number.

These properties can only be accessed as Number.MAX_VALUE.

Using myNumber.MAX_VALUE, where myNumber is a variable, expression, or value, will return undefined:

```javascript
var x = 6;
var y = x.MAX_VALUE;    // y becomes undefined
```

A complete reference to JavaScript numbers can be seen on (https://www.w3schools.com/jsref/jsref_obj_number.asp).
