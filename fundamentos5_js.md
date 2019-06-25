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

### Conversão de Tipo em JavaScript

Variáveis de JavaScript podem ser convertidos em uma nova variável e em um
novo tipo de dado:

  * Pelo uso de uma função do JavaScript
  * Automaticamente pelo próprio JavaScript

### Conversão de Números em Strings

O método global String\(\) pode converter convert números em strings.

Ele pode ser usado em qualquer tipo de números, literais, variáveis ou expressões:

Exemplo

```javascript
String(x)         // retorna uma string de uma variável x com um número
String(123)       // retorna uma string de um número literal 123
String(100 + 23)  // retorna uma string de um número de uma expressão
```

O método *toString\(\)* de *Number* faz a mesma coisa.

Exemplo

```javascript
x.toString()
(123).toString()
(100 + 23).toString()
```

Na seção Métodos de Number, você outros métodos que podem converter um número
numa string:

| Método            | Descrição |
|-------------------|------------------------------------|
| toExponential\(\) | Retorna uma string, com um número arredondado e escrito em notação científica. |
| toFixed\(\)       | Retorna uma string, com um número arredondado e escrito com um número especificado de dígitos decimais. |
| toPrecision\(\)   | Retorna uma string, com um número escrito com um comprimento especificado. |

### Conversão de Booleanos em Strings

O método global String\(\) pode converter booleanos em strings.

```javascript
String(false)      // retorna "false"
String(true)       // retorna "true"
```

O método toString() de Boolean faz a mesma coisa.

```javascript
false.toString()   // retorna "false"
true.toString()    // retorna "true"
```

### Conversão de Dates em Strings

O método global String() pode converter dates em strings.

```javascript
String(Date())  // retorna "Mon Jun 24 2019 00:35:08 GMT-0300 (Horário Padrão de Brasília)"
```

O método toString() de Date faz a mesma coisa.

Exemplo
```javascript
Date().toString()  // retorna "Mon Jun 24 2019 00:35:08 GMT-0300 (Horário Padrão de Brasília)"
```

Na seção Métodos de Date, você encontra outros métodos que podem ser usados
para converter dates em  strings.

### Conversão de Strings em Números

O método global Number\(\) pode converter strings em números.

Strings contendo números \(como "3.14"\) converte em numbers \(como 3.14\).

A string vazia converte em 0.

Qualquer outra coisa converte em NaN \(Not a Number, Não é um Número\).

```javascript
Number("3.14")    // retorna 3.14
Number(" ")       // retorna 0
Number("")        // retorna 0
Number("99 88")   // retorna NaN
```

Na seção de Métodos de Números, você encontra mais métodos que podem ser usados
para converter strings em números.

### O Operador + Unário

O operador + unário pode ser usado para converter uma variável num  número:

Exemplo
```javascript
var y = "5";      // y é uma string
var x = + y;      // x é um número
```

Se a variável não puder ser convertida, ela ainda assim será um número, mas
seu valor será NaN (Not a Number, Não Número):

Exemplo
```javascript
var y = "John";   // y é uma string
var x = + y;      // x é um número (NaN)
```

### Conversão de Booleanos em Números

O método global Number\(\) também pode converter booleanos em números.

```javascript
Number(false)     // retorna 0
Number(true)      // retorna 1
```

### Conversão de Dates em Números

O método Number\(\) pode ser usado para converter dates em números.

```javascript
d = new Date();
Number(d)          // retorna 1404568027739
```

O método getTime\(\) de Date obtém o mesmo resultado.

### Conversão Automática de Tipos

Quando o JavaScript tenta *operar* com um tipo *errado* de dados,
ele tentará converter o valor para o tipo *certo*.

O resultado, nem sempre, é o esperado:

```javascript
5 + null    // retorna 5         porque null é convertido em 0
"5" + null  // retorna "5null"   porque null é convertido em "null"
"5" + 2     // retorna "52"      porque 2 é convertiido em "2"
"5" - 2     // retorna 3         porque "5" é convertido em 5
"5" * "2"   // retorna 10        porque "5" e "2" são convertidos em 5 e 2
"5" + "2"   // retorna "52"      porque não há necessidade de conversão
```

### Conversão Automatica para String

JavaScript chama automaticamente a função toString\(\) da variável quando
você tenta "imprimir" um objeto ou uma variável:

```javascript
document.getElementById("demo").innerHTML = myVar;

// se myVar = {name:"Fjohn"}  // toString converte para "[object Object]"
// se myVar = [1,2,3,4]       // toString converte para "1,2,3,4"
// se myVar = new Date()      
// toString converte para "Tue Jun 25 2019 00:25:30 GMT-0300 (Horário Padrão de Brasília)"
```

Números e booleanos também são convertidos, mas isto não é muito visível:

```javascript
// se myVar = 123             // toString converte para "123"
// se myVar = true            // toString converte para "true"
// se myVar = false           // toString converte para "false"
```

### Tabela de Conversão de Tipo do JavaScript

Esta tabela mostra o resultado da conversão de diferente valores de JavaScript
para Número, String e Booleano:

| Valor Original | Convertido para to Number | Convertido para String | Convertido para Boolean |
|----------------|---------------------------|------------------------|--------------|
| false          | 0                   | "false"             | false |
| true           | 1                   | "true"              | true |
| 0              | 0                   | "0"                 | false |
| 1              | 1                   | "1"                 | true |
| "0"            | 0                   | "0"                 | true |
| "000"          | 0                   | "000"               | true |
| "1"            | 1                   | "1"                 | true |
| NaN            | NaN                 | "NaN"               | false |
| Infinity       | Infinity            | "Infinity"          | true |
| -Infinity      | -Infinity           | "-Infinity"         | true |
| ""             | 0                   | ""                  | false |
| "20"           | 20                  | "20"                | true |
| "twenty"       | NaN                 | "twenty"            | true |
| [ ]            | 0                   | ""                  | true |
| [20]           | 20                  | "20"                | true |
| [10,20]        | NaN                 | "10,20"             | true |
| ["twenty"]     | NaN                 | "twenty"            | true |
| ["ten","five"] | NaN                 | "ten,five"          | true |
| function(){}   | NaN                 | "function(){}"      | true |
| { }            | NaN                 | "[object Object]"   | true |
| null           | 0                   | "null"              | false |
| undefined      | NaN                 | "undefined"         | false |

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

    The examples above uses 4 bits unsigned binary numbers. Because of this ~ 5 retorna 10.

    Since JavaScript uses 32 bits signed integers, it will not return 10. It will return -6.

    00000000000000000000000000000101 (5)

    11111111111111111111111111111010 (~5 = -6)

    A signed integer uses the leftmost bit as the minus sign.

### Bitwise AND

When a bitwise AND is performed on a pair of bits, it retorna 1 if both bits are 1.

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

When a bitwise OR is performed on a pair of bits, it retorna 1 if one of the bits are 1:

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

When a bitwise XOR is performed on a pair of bits, it retorna 1 if the bits are different:

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

Bitwise AND retorna 1 only if both bits are 1:

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

Bitwise OR retorna 1 if one of the bits are 1:

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

Bitwise XOR retorna 1 if the bits are different:

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

The search\(\) method uses an expression to search for a match, and retorna the position of the match.

The replace\(\) method retorna a modified string where the pattern is replaced.

#### Using String search\(\) With a String

The search\(\) method searches a string for a specified value and retorna the position of the match:

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

It searches a string for a pattern, and retorna true or false, depending on the result.

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

It searches a string for a specified pattern, and retorna the found text as an object.

If no match is found, it retorna an empty \(null\) object.

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
name     | Sets or retorna an error name
message  | Sets or retorna an error message \(a string\)

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

[Próxima unidade](intermediario1_js.md)
