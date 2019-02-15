# JavaScript Tutorial: Advanced I

This is my annotations from [javascript tutorial W3C school study](https://www.w3schools.com/js/).

## JavaScript Debugging (https://www.w3schools.com/js/js_debugging.asp)

Errors can \(will\) happen, every time you write some new computer code.

### Code Debugging

Programming code might contain syntax errors, or logical errors.

Many of these errors are difficult to diagnose.

Often, when programming code contains errors, nothing will happen. There are no error messages, and you will get no indications where to search for errors.

Searching for \(and fixing\) errors in programming code is called code debugging.

### JavaScript Debuggers

Debugging is not easy. But fortunately, all modern browsers have a built-in JavaScript debugger.

Built-in debuggers can be turned on and off, forcing errors to be reported to the user.

With a debugger, you can also set breakpoints \(places where code execution can be stopped\), and examine variables while the code is executing.

Normally, otherwise follow the steps at the bottom of this page, you activate debugging in your browser with the F12 key, and select "Console" in the debugger menu.

### The console.log() Method

If your browser supports debugging, you can use console.log\(\) to display JavaScript values in the debugger window:

Example


```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>

<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>

</body>
</html>
```

### Setting Breakpoints

In the debugger window, you can set breakpoints in the JavaScript code.

At each breakpoint, JavaScript will stop executing, and let you examine JavaScript values.

After examining values, you can resume the execution of code \(typically with a play button\).

### The debugger Keyword

The debugger keyword stops the execution of JavaScript, and calls (if available) the debugging function.

This has the same function as setting a breakpoint in the debugger.

If no debugging is available, the debugger statement has no effect.

With the debugger turned on, this code will stop executing before it executes the third line.

Example

```javascript
var x = 15 * 5;
debugger;
document.getElementById("demo").innerHTML = x;
```

### Major Browsers' Debugging Tools

Normally, you activate debugging in your browser with F12, and select "Console" in the debugger menu.

Otherwise follow these steps:

#### Chrome
  1. Open the browser.
  2. From the menu, select "More tools".
  3. From tools, choose "Developer tools".
  4. Finally, select Console.
  
#### Firefox
  1. Open the browser.
  2. From the menu, select "Web Developer".
  3. Finally, select "Web Console".

#### Edge
  1. Open the browser.
  2. From the menu, select "Developer Tools".
  3. Finally, select "Console".

#### Opera
  1. Open the browser.
  2. From the menu, select "Developer".
  3. From "Developer", select "Developer tools".
  4. Finally, select "Console".

#### Safari
  1. Go to Safari, Preferences, Advanced in the main menu.
  2. Check "Enable Show Develop menu in menu bar".
  3. When the new option "Develop" appears in the menu:
  4. Choose "Show Error Console".

## JavaScript Style Guide and Coding Conventions (https://www.w3schools.com/js/js_conventions.asp)

Always use the same coding conventions for all your JavaScript projects.

### JavaScript Coding Conventions

Coding conventions are style guidelines for programming. They typically cover:

  * Naming and declaration rules for variables and functions.
  * Rules for the use of white space, indentation, and comments.
  * Programming practices and principles

Coding conventions secure quality:

  * Improves code readability
  * Make code maintenance easier

Coding conventions can be documented rules for teams to follow, or just be your individual coding practice.

    This section describes the general JavaScript code conventions used by W3Schools.
    You should also read the next chapter "Best Practices", and learn how to avoid coding pitfalls.

### Variable Names

At W3schools we use camelCase for identifier names (variables and functions).

All names start with a letter.

At the end of this subsection, you will find a wider discussion about naming rules.

```javascript
firstName = "John";
lastName = "Doe";

price = 19.90;
tax = 0.20;

fullPrice = price + (price * tax);
```

### Spaces Around Operators

Always put spaces around operators \( = + - * / \), and after commas:

Examples:

```javascript
var x = y + z;
var values = ["Volvo", "Saab", "Fiat"];
```

### Code Indentation

Always use 2 spaces for indentation of code blocks:

Functions:
```javascript
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}
```

    Do not use tabs \(tabulators\) for indentation. Different editors interpret tabs differently.

### Statement Rules

General rules for simple statements:

Always end a simple statement with a semicolon.

Examples

```javascript
var values = ["Volvo", "Saab", "Fiat"];

var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

General rules for complex (compound) statements:

  * Put the opening bracket at the end of the first line.
  * Use one space before the opening bracket.
  * Put the closing bracket on a new line, without leading spaces.
  * Do not end a complex statement with a semicolon.

Functions:
```javascript
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}
```

Loops:
```javascript
for (i = 0; i < 5; i++) {
  x += i;
}
```

Conditionals:
```javascript
if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

### Object Rules

General rules for object definitions:

  * Place the opening bracket on the same line as the object name.
  * Use colon plus one space between each property and its value.
  * Use quotes around string values, not around numeric values.
  * Do not add a comma after the last property-value pair.
  * Place the closing bracket on a new line, without leading spaces.
  * Always end an object definition with a semicolon.
  
Example

```javascript
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

Short objects can be written compressed, on one line, using spaces only between properties, like this:

```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

### Line Length < 80

For readability, avoid lines longer than 80 characters.

If a JavaScript statement does not fit on one line, the best place to break it, is after an operator or a comma.

Example

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly.";
```

### Naming Conventions

Always use the same naming convention for all your code. For example:

  * Variable and function names written as camelCase
  * Global variables written in UPPERCASE \(We don't, but it's quite common\)
  * Constants \(like PI\) written in UPPERCASE

Should you use hyp-hens, camelCase, or under_scores in variable names?

This is a question programmers often discuss. The answer depends on who you ask:

#### Hyphens in HTML and CSS:

HTML5 attributes can start with data- \(data-quantity, data-price\).

CSS uses hyphens in property-names \(font-size\).

    Hyphens can be mistaken as subtraction attempts. Hyphens are not allowed in JavaScript names.

#### Underscores:

Many programmers prefer to use underscores \(date_of_birth\), especially in SQL databases.

Underscores are often used in PHP documentation.

#### PascalCase:

PascalCase is often preferred by C programmers.

#### camelCase:

camelCase is used by JavaScript itself, by jQuery, and other JavaScript libraries.

    Do not start names with a $ sign. It will put you in conflict with many JavaScript library names.

### Loading JavaScript in HTML

Use simple syntax for loading external scripts (the type attribute is not necessary):

```html
<script src="myscript.js"></script>
```

### Accessing HTML Elements

A consequence of using "untidy" HTML styles, might result in JavaScript errors.

These two JavaScript statements will produce different results:

```javascript
var obj = getElementById("Demo")

var obj = getElementById("demo")
```

If possible, use the same naming convention \(as JavaScript\) in HTML.

### File Extensions

HTML files should have a **.html** extension (not **.htm**).

CSS files should have a **.css** extension.

JavaScript files should have a **.js** extension.

### Use Lower Case File Names

Most web servers \(Apache, Unix\) are case sensitive about file names:

london.jpg cannot be accessed as London.jpg.

Other web servers \(Microsoft, IIS\) are not case sensitive:

london.jpg can be accessed as London.jpg or london.jpg.

If you use a mix of upper and lower case, you have to be extremely consistent.

If you move from a case insensitive, to a case sensitive server, even small errors can break your web site.

To avoid these problems, always use lower case file names \(if possible\).

### Performance

Coding conventions are not used by computers. Most rules have little impact on the execution of programs.

Indentation and extra spaces are not significant in small scripts.

For code in development, readability should be preferred. Larger production scripts should be minified. 


## JavaScript Best Practices (https://www.w3schools.com/js/js_best_practices.asp)

Avoid global variables, avoid new, avoid ==, avoid eval\(\)

### Avoid Global Variables

Minimize the use of global variables.

This includes all data types, objects, and functions.

Global variables and functions can be overwritten by other scripts.

Use local variables instead, and learn how to use closures.

### Always Declare Local Variables

All variables used in a function should be declared as local variables.

Local variables must be declared with the var keyword, otherwise they will become global variables.

Strict mode does not allow undeclared variables.

### Declarations on Top

It is a good coding practice to put all declarations at the top of each script or function.

This will:

  * Give cleaner code
  * Provide a single place to look for local variables
  * Make it easier to avoid unwanted (implied) global variables
  * Reduce the possibility of unwanted re-declarations

```javascript
// Declare at the beginning
var firstName, lastName, price, discount, fullPrice;

// Use later
firstName = "John";
lastName = "Doe";

price = 19.90;
discount = 0.10;

fullPrice = price * 100 / discount;
```

This also goes for loop variables:

```javascript
// Declare at the beginning
var i;

// Use later
for (i = 0; i < 5; i++) {
```

    By default, JavaScript moves all declarations to the top (JavaScript Hoisting).

### Initialize Variables

It is a good coding practice to initialize variables when you declare them.

This will:

  * Give cleaner code
  * Provide a single place to initialize variables
  * Avoid undefined values

```javascript
// Declare and initiate at the beginning
var firstName = "",
lastName = "",
price = 0,
discount = 0,
fullPrice = 0,
myArray = [],
myObject = {};
```

    Initializing variables provides an idea of the intended use \(and intended data type\).

### Never Declare Number, String, or Boolean Objects

Always treat numbers, strings, or booleans as primitive values. Not as objects.

Declaring these types as objects, slows down execution speed, and produces nasty side effects:

Example

```javascript
var x = "John";             
var y = new String("John");
(x === y) // is false because x is a string and y is an object.
```

Or even worse:

Example
```javascript
var x = new String("John");             
var y = new String("John");
(x == y) // is false because you cannot compare objects.
```

#### Don't Use new Object()

  * Use {} instead of new Object()
  * Use "" instead of new String()
  * Use 0 instead of new Number()
  * Use false instead of new Boolean()
  * Use [] instead of new Array()
  * Use /()/ instead of new RegExp()
  * Use function (){} instead of new Function()

Example

```javascript
var x1 = {};           // new object
var x2 = "";           // new primitive string
var x3 = 0;            // new primitive number
var x4 = false;        // new primitive boolean
var x5 = [];           // new array object
var x6 = /()/;         // new regexp object
var x7 = function(){}; // new function object
```

### Beware of Automatic Type Conversions

Beware that numbers can accidentally be converted to strings or NaN \(Not a Number\).

JavaScript is loosely typed. A variable can contain different data types, and a variable can change its data type:

Example

```javascript
var x = "Hello";     // typeof x is a string
x = 5;               // changes typeof x to a number
```

When doing mathematical operations, JavaScript can convert numbers to strings:

Example

```javascript
var x = 5 + 7;       // x.valueOf() is 12,  typeof x is a number
var x = 5 + "7";     // x.valueOf() is 57,  typeof x is a string
var x = "5" + 7;     // x.valueOf() is 57,  typeof x is a string
var x = 5 - 7;       // x.valueOf() is -2,  typeof x is a number
var x = 5 - "7";     // x.valueOf() is -2,  typeof x is a number
var x = "5" - 7;     // x.valueOf() is -2,  typeof x is a number
var x = 5 - "x";     // x.valueOf() is NaN, typeof x is a number
```

Subtracting a string from a string, does not generate an error but returns NaN (Not a Number):

Example

```javascript
"Hello" - "Dolly"    // returns NaN
```

### Use === Comparison

The == comparison operator always converts \(to matching types\) before comparison.

The === operator forces comparison of values and type:

Example

```javascript
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```

### Use Parameter Defaults

If a function is called with a missing argument, the value of the missing argument is set to undefined.

Undefined values can break your code. It is a good habit to assign default values to arguments.

Example

```javascript
function myFunction(x, y) {
  if (y === undefined) {
    y = 0;
  }
}
```

ECMAScript 2015 allows default parameters in the function call:

```javascript
function (a=1, b=1) { // function code }
```

### End Your Switches with Defaults

Always end your switch statements with a default. Even if you think there is no need for it.

Example

```javascript
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
    break;
  default:
    day = "Unknown";
}
```

### Avoid Using eval\(\)

The eval\(\) function is used to run text as code. In almost all cases, it should not be necessary to use it.

Because it allows arbitrary code to be run, it also represents a security problem.

## JavaScript Common Mistakes (https://www.w3schools.com/js/js_mistakes.asp)

### Accidentally Using the Assignment Operator

JavaScript programs may generate unexpected results if a programmer accidentally uses an assignment operator \(=\), instead of a comparison operator \(==\) in an if statement.

This if statement returns false \(as expected\) because x is not equal to 10:

```javascript
var x = 0;
if (x == 10)
```

This if statement returns true (maybe not as expected), because 10 is true:

```javascript
var x = 0;
if (x = 10)
```

This if statement returns false (maybe not as expected), because 0 is false:

```javascript
var x = 0;
if (x = 0)
```

An assignment always returns the value of the assignment.

### Expecting Loose Comparison

In regular comparison, data type does not matter. This if statement returns true:

```javascript
var x = 10;
var y = "10";
if (x == y)
```

In strict comparison, data type does matter. This if statement returns false:

```javascript
var x = 10;
var y = "10";
if (x === y)
```

It is a common mistake to forget that switch statements use strict comparison:

This case switch will display an alert:

```javascript
var x = 10;
switch(x) {
  case 10: alert("Hello");
}
```

This case switch will not display an alert:

```javascript
var x = 10;
switch(x) {
  case "10": alert("Hello");
}
```

### Confusing Addition & Concatenation

Addition is about adding numbers.

Concatenation is about adding strings.

In JavaScript both operations use the same + operator.

Because of this, adding a number as a number will produce a different result from adding a number as a string:

```javascript
var x = 10 + 5;          // the result in x is 15
var x = 10 + "5";        // the result in x is "105"
```

When adding two variables, it can be difficult to anticipate the result:

```javascript
var x = 10;
var y = 5;
var z = x + y;           // the result in z is 15

var x = 10;
var y = "5";
var z = x + y;           // the result in z is "105"
```

### Misunderstanding Floats

All numbers in JavaScript are stored as 64-bits Floating point numbers \(Floats\).

All programming languages, including JavaScript, have difficulties with precise floating point values:

```javascript
var x = 0.1;
var y = 0.2;
var z = x + y            // the result in z will not be 0.3
```

To solve the problem above, it helps to multiply and divide:

Example

```javascript
var z = (x * 10 + y * 10) / 10;       // z will be 0.3
```

### Breaking a JavaScript String

JavaScript will allow you to break a statement into two lines:

Example 1

```javascript
var x =
"Hello World!";
```

But, breaking a statement in the middle of a string will not work:

Example 2

```javascript
var x = "Hello
World!";
```

You must use a "backslash" if you must break a statement in a string:

Example 3

```javascript
var x = "Hello \
World!";
```

### Misplacing Semicolon

Because of a misplaced semicolon, this code block will execute regardless of the value of x:

```javascript
if (x == 19);
{
  // code block  
}
```

### reaking a Return Statement

It is a default JavaScript behavior to close a statement automatically at the end of a line.

Because of this, these two examples will return the same result:

Example 1
```javascript
function myFunction(a) {
  var power = 10  
  return a * power
}
```

Example 2
```javascript
function myFunction(a) {
  var power = 10;
  return a * power;
}
```

JavaScript will also allow you to break a statement into two lines.

Because of this, example 3 will also return the same result:

Example 3
```javascript
function myFunction(a) {
  var
  power = 10;  
  return a * power;
}
```

But, what will happen if you break the return statement in two lines like this:

Example 4
```javascript
function myFunction(a) {
  var
  power = 10;  
  return
  a * power;
}
```

The function will return undefined!

Why? Because JavaScript thought you meant:

Example 5
```javascript
function myFunction(a) {
  var
  power = 10;  
  return;
  a * power;
}
```

#### Explanation

If a statement is incomplete like:

```javascript
var
```

JavaScript will try to complete the statement by reading the next line:

```javascript
power = 10;
```

But since this statement is complete:

```javascript
return
```

JavaScript will automatically close it like this:

```javascript
return;
```

This happens because closing \(ending\) statements with semicolon is optional in JavaScript.

JavaScript will close the return statement at the end of the line, because it is a complete statement.

    Never break a return statement.

### Accessing Arrays with Named Indexes

Many programming languages support arrays with named indexes.

Arrays with named indexes are called associative arrays (or hashes).

JavaScript does not support arrays with named indexes.

In JavaScript, arrays use numbered indexes:  

Example:

```javascript
var person = [];
person[0] = "John";
person[1] = "Doe";
person[2] = 46;
var x = person.length;       // person.length will return 3
var y = person[0];           // person[0] will return "John"
```

In JavaScript, objects use named indexes.

If you use a named index, when accessing an array, JavaScript will redefine the array to a standard object.

After the automatic redefinition, array methods and properties will produce undefined or incorrect results:

Example:

```javascript
var person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
var x = person.length;      // person.length will return 0
var y = person[0];          // person[0] will return undefined
```

### Ending Definitions with a Comma

Trailing commas in object and array definition are legal in ECMAScript 5.

Object Example:
```javascript
person = {firstName:"John", lastName:"Doe", age:46,}
```

Array Example:
```javascript
points = [40, 100, 1, 5, 25, 10,];
```

WARNING !!

    Internet Explorer 8 will crash.

    JSON does not allow trailing commas.

JSON:
```javascript
person = {"firstName":"John", "lastName":"Doe", "age":46}
```

JSON:
```javascript
points = [40, 100, 1, 5, 25, 10];
```

### Undefined is Not Null

JavaScript objects, variables, properties, and methods can be undefined.

In addition, empty JavaScript objects can have the value null.

This can make it a little bit difficult to test if an object is empty.

You can test if an object exists by testing if the type is undefined:

Example:

```javascript
if (typeof myObj === "undefined")
```
 
But you cannot test if an object is null, because this will throw an error if the object is undefined:

Incorrect:
```javascript
if (myObj === null)
```
 
To solve this problem, you must test if an object is not null, and not undefined.

But this can still throw an error:

Incorrect:
```javascript
if (myObj !== null && typeof myObj !== "undefined")
```
 
Because of this, you must test for not undefined before you can test for not null:

Correct:
```javascript
if (typeof myObj !== "undefined" && myObj !== null)
```

### Expecting Block Level Scope

JavaScript does not create a new scope for each code block.

It is true in many programming languages, but not true in JavaScript.

This code will display the value of i \(10\), even OUTSIDE the for loop block:

Example

```javascript
for (var i = 0; i < 10; i++) {
  // some code
}
return i;
```

## JavaScript Performance (https://www.w3schools.com/js/js_performance.asp)

### Reduce Activity in Loops

Loops are often used in programming.

Each statement in a loop, including the for statement, is executed for each iteration of the loop.

Statements or assignments that can be placed outside the loop will make the loop run faster.

Bad:
```javascript
var i;
for (i = 0; i < arr.length; i++) {
```

Better Code:
```javascript
var i;
var l = arr.length;
for (i = 0; i < l; i++) {
```

The bad code accesses the length property of an array each time the loop is iterated.

The better code accesses the length property outside the loop and makes the loop run faster.

### Reduce DOM Access

Accessing the HTML DOM is very slow, compared to other JavaScript statements.

If you expect to access a DOM element several times, access it once, and use it as a local variable:

Example
```javascript
var obj;
obj = document.getElementById("demo");
obj.innerHTML = "Hello";
```

### Reduce DOM Size

Keep the number of elements in the HTML DOM small.

This will always improve page loading, and speed up rendering \(page display\), especially on smaller devices.

Every attempt to search the DOM \(like getElementsByTagName\) will benefit from a smaller DOM.

### Avoid Unnecessary Variables

Don't create new variables if you don't plan to save values.

Often you can replace code like this:

```javascript
var fullName = firstName + " " + lastName;
document.getElementById("demo").innerHTML = fullName;
```

With this:

```javascript
document.getElementById("demo").innerHTML = firstName + " " + lastName
```

### Delay JavaScript Loading

Putting your scripts at the bottom of the page body lets the browser load the page first.

While a script is downloading, the browser will not start any other downloads. In addition all parsing and rendering activity might be blocked.

The HTTP specification defines that browsers should not download more than two components in parallel.

An alternative is to use defer="true" in the script tag. The defer attribute specifies that the script should be executed after the page has finished parsing, but it only works for external scripts.

If possible, you can add your script to the page by code, after the page has loaded:

Example

```javascript
<script>
window.onload = function() {
  var element = document.createElement("script");
  element.src = "myScript.js";
  document.body.appendChild(element);
};
</script>
```

### Avoid Using with

Avoid using the with keyword. It has a negative effect on speed. It also clutters up JavaScript scopes.

The with keyword is **not allowed** in strict mode.

## JavaScript Reserved Words (https://www.w3schools.com/js/js_reserved.asp)

### In JavaScript you cannot use these reserved words as variables, labels, or function names:

---------|-----------|---------|----------
abstract | arguments | await\* | boolean
break | byte | case | catch
char | class\* | const | continue
debugger | default | delete | do
double | else | enum\* | eval
export\* | extends\* | false | final
finally | float | for | function
goto | if | implements | import\*
in | instanceof | int | interface
let\* | long | native | new
null | package | private | protected
public | return | short | static
super\* | switch | synchronized | this
throw | throws | transient | true
try | typeof | var | void
volatile | while | with | yield

Words marked with \* are new in ECMAScript 5 and 6.

### Removed Reserved Words
The following reserved words has been removed from the ECMAScript 5/6 standard:
-------------------------------------------------
abstract | boolean | byte | char
double | final | float | goto
int | long | native | short
synchronized | throws | transient | volatile

Do not use these words as variables. ECMAScript 5/6 does not have full support in all browsers.

### JavaScript Objects, Properties, and Methods

You should also avoid using the name of JavaScript built-in objects, properties, and methods:

------|------|------|-------------------------------
Array | Date | eval | function
hasOwnProperty | Infinity | isFinite | isNaN
isPrototypeOf | length | Math | NaN
name | Number | Object | prototype
String | toString | undefined | valueOf

### Java Reserved Words

JavaScript is often used together with Java. You should avoid using some Java objects and properties as JavaScript identifiers:

---------|------------------|--------------------
getClass | java | JavaArray | javaClass
JavaObject | JavaPackage | 

### Other Reserved Words

JavaScript can be used as the programming language in many applications.

You should also avoid using the name of HTML and Window objects and properties:

------|-----|--------|-----------------------------------------------
alert | all | anchor | anchors
area | assign | blur | button
checkbox | clearInterval | clearTimeout | clientInformation
close | closed | confirm | constructor
crypto | decodeURI | decodeURIComponent | defaultStatus
document | element | elements | embed
embeds | encodeURI | encodeURIComponent | escape
event | fileUpload | focus | form
forms | frame | innerHeight | innerWidth
layer | layers | link | location
mimeTypes | navigate | navigator | frames
frameRate | hidden | history | image
images | offscreenBuffering | open | opener
option | outerHeight | outerWidth | packages
pageXOffset | pageYOffset | parent | parseFloat
parseInt | password | pkcs11 | plugin
prompt | propertyIsEnum | radio | reset
screenX | screenY | scroll | secure
select | self | setInterval | setTimeout
status | submit | taint | text
textarea | top | unescape | untaint
window |  | 

### HTML Event Handlers

In addition you should avoid using the name of all HTML event handlers.

Examples:

-------|---------|---------|------------------------
onblur | onclick | onerror | onfocus
onkeydown | onkeypress | onkeyup | onmouseover
onload | onmouseup | onmousedown | onsubmit

## JavaScript JSON (https://www.w3schools.com/js/js_json.asp)

JSON is a format for storing and transporting data.

JSON is often used when data is sent from a server to a web page.

### What is JSON?

  * JSON stands for JavaScript Object Notation
  * JSON is a lightweight data interchange format
  * JSON is language independent *
  * JSON is "self-describing" and easy to understand

* The JSON syntax is derived from JavaScript object notation syntax, but the JSON format is text only. Code for reading and generating JSON data can be written in any programming language.

### JSON Example

This JSON syntax defines an employees object: an array of 3 employee records \(objects\):

JSON Example
```json
{
"employees":[
  {"firstName":"John", "lastName":"Doe"}, 
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]
}
```

### The JSON Format Evaluates to JavaScript Objects

The JSON format is syntactically identical to the code for creating JavaScript objects.

Because of this similarity, a JavaScript program can easily convert JSON data into native JavaScript objects.

### JSON Syntax Rules

  * Data is in name/value pairs
  * Data is separated by commas
  * Curly braces hold objects
  * Square brackets hold arrays

### JSON Data - A Name and a Value

JSON data is written as name/value pairs, just like JavaScript object properties.

A name/value pair consists of a field name \(in double quotes\), followed by a colon, followed by a value:

```json
"firstName":"John"
```

    JSON names require double quotes. JavaScript names do not.

### JSON Objects

JSON objects are written inside curly braces.

Just like in JavaScript, objects can contain multiple name/value pairs:

```json
{"firstName":"John", "lastName":"Doe"}
```

### JSON Arrays
JSON arrays are written inside square brackets.

Just like in JavaScript, an array can contain objects:

```json
"employees":[
  {"firstName":"John", "lastName":"Doe"}, 
  {"firstName":"Anna", "lastName":"Smith"}, 
  {"firstName":"Peter", "lastName":"Jones"}
]
```

In the example above, the object "employees" is an array. It contains three objects.

Each object is a record of a person \(with a first name and a last name\).

### Converting a JSON Text to a JavaScript Object

A common use of JSON is to read data from a web server, and display the data in a web page.

For simplicity, this can be demonstrated using a string as input.

First, create a JavaScript string containing JSON syntax:

```json
var text = '{ "employees" : [' +
'{ "firstName":"John" , "lastName":"Doe" },' +
'{ "firstName":"Anna" , "lastName":"Smith" },' +
'{ "firstName":"Peter" , "lastName":"Jones" } ]}';
```

Then, use the JavaScript built-in function JSON.parse\(\) to convert the string into a JavaScript object:

```javascript
var obj = JSON.parse(text);
```

Finally, use the new JavaScript object in your page:

Example
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
obj.employees[1].firstName + " " + obj.employees[1].lastName;
</script>
```

## JavaScript Forms (https://www.w3schools.com/js/js_validation.asp)

### JavaScript Form Validation

HTML form validation can be done by JavaScript.

If a form field (fname) is empty, this function alerts a message, and returns false, to prevent the form from being submitted:

JavaScript Example:
```javascript
function validateForm() {
  var x = document.forms["myForm"]["fname"].value;
  if (x == "") {
    alert("Name must be filled out");
    return false;
  }
}
```

The function can be called when the form is submitted:

HTML Form Example: [Demo: Form Val1](valid_demo1.html)
```html
<form name="myForm" action="/action_page.php" onsubmit="return validateForm()" method="post">
Name: <input type="text" name="fname">
<input type="submit" value="Submit">
</form>
```

### JavaScript Can Validate Numeric Input

JavaScript is often used to validate numeric input: [Demo: Form Val2](valid_demo2.html)
Example:
```javascript
function myFunction() {
  var x, text;

  // Get the value of the input field with id="numb"
  x = document.getElementById("numb").value;

  // If x is Not a Number or less than one or greater than 10
  if (isNaN(x) || x < 1 || x > 10) {
    text = "Input not valid";
  } else {
    text = "Input OK";
  }
  document.getElementById("demo").innerHTML = text;
}
```

### Automatic HTML Form Validation

HTML form validation can be performed automatically by the browser:

If a form field (fname) is empty, the required attribute prevents this form from being submitted:

HTML Form Example
```html
<form action="/action_page.php" method="post">
  <input type="text" name="fname" required>
  <input type="submit" value="Submit">
</form>
```

### Data Validation

Data validation is the process of ensuring that user input is clean, correct, and useful.

Typical validation tasks are:

  * has the user filled in all required fields?
  * has the user entered a valid date?
  * has the user entered text in a numeric field?

Most often, the purpose of data validation is to ensure correct user input.

Validation can be defined by many different methods, and deployed in many different ways.

**Server side validation** is performed by a web server, after input has been sent to the server.

**Client side validation** is performed by a web browser, before input is sent to a web server.

   Obs.: You should do both. DON'T rely only on client side validation. Data may be coming without using your js validation.
   
### HTML Constraint Validation

HTML5 introduced a new HTML validation concept called **constraint validation**.

HTML constraint validation is based on:

  * Constraint validation HTML Input Attributes
  * Constraint validation CSS Pseudo Selectors
  * Constraint validation DOM Properties and Methods

#### Constraint Validation HTML Input Attributes

Attribute | Description
----------|-------------
disabled | Specifies that the input element should be disabled
max | Specifies the maximum value of an input element
min | Specifies the minimum value of an input element
pattern | Specifies the value pattern of an input element
required | Specifies that the input field requires an element
type  | Specifies the type of an input element

#### Constraint Validation CSS Pseudo Selectors

Selector | Description
---------|-------------
:disabled | Selects input elements with the "disabled" attribute specified
:invalid | Selects input elements with invalid values
:optional | Selects input elements with no "required" attribute specified
:required | Selects input elements with the "required" attribute specified
:valid | Selects input elements with valid values

## JavaScript Validation API [JS Validation](https://www.w3schools.com/js/js_validation_api.asp)

### Constraint Validation DOM Methods

Property | Description
---------|---------------
checkValidity\(\) | Returns true if an input element contains valid data.
setCustomValidity\(\) | Sets the validationMessage property of an input element.

If an input field contains invalid data, display a message:

#### The checkValidity\(\) Method

Example: [Demo: Form Val3](valid_demo3.html)
```html
<input id="id1" type="number" min="100" max="300" required>
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var inpObj = document.getElementById("id1");
  if (!inpObj.checkValidity()) {
    document.getElementById("demo").innerHTML = inpObj.validationMessage;
  }
}
</script>
```

### Constraint Validation DOM Properties

Property | Description
---------|------------
validity | Contains boolean properties related to the validity of an input element.
validationMessage | Contains the message a browser will display when the validity is false.
willValidate | Indicates if an input element will be validated.

### Validity Properties
The validity property of an input element contains a number of properties related to the validity of data:

Property | Description
---------|----------------
customError | Set to true, if a custom validity message is set.
patternMismatch | Set to true, if an element's value does not match its pattern attribute.
rangeOverflow | Set to true, if an element's value is greater than its max attribute.
rangeUnderflow | Set to true, if an element's value is less than its min attribute.
stepMismatch | Set to true, if an element's value is invalid per its step attribute.
tooLong | Set to true, if an element's value exceeds its maxLength attribute.
typeMismatch | Set to true, if an element's value is invalid per its type attribute.
valueMissing | Set to true, if an element \(with a required attribute\) has no value.
valid | Set to true, if an element's value is valid.

### Examples

If the number in an input field is greater than 100 \(the input's max attribute\), display a message:

#### The rangeOverflow Property
```html
<input id="id1" type="number" max="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var txt = "";
  if (document.getElementById("id1").validity.rangeOverflow) {
    txt = "Value too large";
  }
  document.getElementById("demo").innerHTML = txt;
}
</script>
```

If the number in an input field is less than 100 \(the input's min attribute\), display a message:

#### The rangeUnderflow Property
```html
<input id="id1" type="number" min="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var txt = "";
  if (document.getElementById("id1").validity.rangeUnderflow) {
    txt = "Value too small";
  }
  document.getElementById("demo").innerHTML = txt;
}
</script>
```
