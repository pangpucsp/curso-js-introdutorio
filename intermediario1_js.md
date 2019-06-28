# Fundamentos VI de JavaScript

Esta é a continuação de [Fundamentos V de JS](fundamento5_js.md).

## [Uso Estrito do JavaScript](https://www.w3schools.com/js/js_strict.asp)

"use strict"; define que o código de JavaScript deve ser executado no modo
estrito, "strict mode".

### A Diretiva "use strict"

A diretiva "use strict" era nova na versão 5 do ECMAScript.

Ela não é uma instrução, mas uma expressão literal, ignorada pelas versão
anteriores de JavaScript.

O propósito de "use strict" é indicar que o código deve ser executado no "strict mode".

Com o modo estrito, você não pode, por exemplo, usar variáveis não declaradas.

todos os navegadores modernos dão suporte ao "use strict", exceto o Internet
Explorer 9 e predecessores.

    Você pode usar o modo estrito em todos os seus programas.
    Ele ajuda-o a escrever código mais limpo, como quando evita que você use
    variáveis não declaradas.

    "use strict" é apenas uma string, logo o IE 9 não lançará um erro
    se ele não o entender.

### Declaração do Modo Estrito

Strict mode é declarado pela adição de "use strict"; no início de um *script*
ou de uma função.

Declarado no início de um *script*, ele tem escopo global \(todo código no
  *script* será executado no modo estrito\):

Exemplo

```javascript
"use strict";
x = 3.14;       // Isto vai causar um erro porque x não foi declarada
```

Exemplo

```javascript
"use strict";
myFunction();

function myFunction() {
  y = 3.14;   // Isto também vai causar um erro porque y não foi declarada
}
```

Declarado dentro de uma função, ela tem escopo local \(apenas o código dentro
  da função está no modo estrito\):

```javascript
x = 3.14;       // Isto não causa erro.
myFunction();

function myFunction() {
  "use strict";
  y = 3.14;   // Isto causa erro.
}
```

### A Sintaxe de "use strict";

A sintaxe, para a declaração do modo estrito, foi projetada para ser compatível
com versões mais antigas de JavaScript.

Compilar uma literal numérica \(4 + 5;\), ou uma literal de texto
\("John Doe";\) num programa JavaScript não produz efeitos colaterais.
Ela simplesmente compila para uma variável inexistente e morre.

Portanto, "use strict"; só intersssa aos novos compiladores que *entendem* o
significado da declaração.

### Por que Strict Mode?

Strict mode torna mais fácil escrever código JavaScript *seguro*.

Strict mode transforma "más sintaxes" anteriormente aceitas em erros.

Por exemplo, no JavaScript normal, erro de datilografia no nome de uma variável
criava uma nova variável global. No strict mode, isto lança um erro, fazendo com
que seja impossível de criar variáveis globais acidentalmente.

No JavaScript normal, um desenvolvedor não recebe retorno de erro ao atribuir
um valor a propriedades sem direito de escrita.

No strict mode, qualquer atribuição a uma propriedade não-alterável, uma
propriedade de apenas-leitura \(getter-only property\), uma propriedade
inexistente, uma variável inexistente, ou um objeto inexistente lançará um *error*.

### Não Permitido no Modo Estrito

Usar uma variável sem declará-la antes não é permitido:

```javascript
"use strict";
x = 3.14;                // Isto causa erro
```

Objetos também são variáveis.

Usar um objeto sem declará-lo antes não é permitido:

```javascript
"use strict";
x = {p1:10, p2:20};      // Isto também causa erro
```

Apagar uma variável \(ou objeto\) não é permitido.

```javascript
"use strict";
var x = 3.14;
delete x;                // Isto causa erro
```

Apagar uma função não é permitido.

```javascript
"use strict";
function x(p1, p2) {};
delete x;                // Isto causa erro
```

Duplicar o nome de um parâmetro não é permitido:

```javascript
"use strict";
function x(p1, p1) {};   // Isto causa erro
```

Literais numéricas em octal não são permitidas:

```javascript
"use strict";
var x = 010;             // Isto causa erro
```

Caracteres em octal não são permitidas:

```javascript
"use strict";
var x = "\010";            // Isto causa erro
```

Escrever numa propriedade de apenas-leitura não é permitido:

```javascript
"use strict";
var obj = {};
Object.defineProperty(obj, "x", {value:0, writable:false});

obj.x = 3.14;            // isto causa erro
```

Escrever numa propriedade  *get-only* não é permitido:

```javascript
"use strict";
var obj = {get x() {return 0} };

obj.x = 3.14;            // Isto causa erro
```

Remover uma propriedade não deletável não é permitido:

```javascript
"use strict";
delete Object.prototype; // Isto causa erro
```

O nome "eval" não pode ser usada como nome de variável:

```javascript
"use strict";
var eval = 3.14;         // Isto causa erro
```

A string "arguments" não pode ser usada com uma variável:

```javascript
"use strict";
var arguments = 3.14;    // Isto causa erro
```

A instrução *with* não é permitida:

```javascript
"use strict";
with (Math){x = cos(2)}; // Isto causa erro
```

Por motivo de segurança, eval\(\) não é permitida a criação de variáveis no
escopo a partir do qual ele está sendo chamado:

```javascript
"use strict";
eval ("var x = 2");
alert (x);             // Isto causará erro
```

A palavra-chave *this* em funções comporta-se diferentemente no modo estrito.

A palavra-chave *this* refere-se a um objeto que chamou a função, se o objeto
não for especificado, funções no modo estrito retornam *undefined* e funções
no modo normal retornam o objeto global \(windows\).

Exemplo

```JavaScript
"use strict";
function myFunction() {
  alert(this); // alerta "undefined"
}
myFunction();
```

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

[Próxima unidade](intermediario2_js.md)
