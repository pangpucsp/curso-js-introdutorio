# Fundamentos VIII de JavaScript

Esta é a continuação de [Fundamentos VII de JS](intermediario2_js.md).

<!--
This is my annotations from [javascript tutorial W3C school study](https://www.w3schools.com/js/).
This part is about Objects in JavaScript.
-->

## Objetos em JavaScript (https://www.w3schools.com/js/js_object_definition.asp)

> Em JavaScript, objetos são reis. Se você entender os objetos, você
> entenderá JavaScript.

Em JavaScript, *quase* tudo é um **objeto**.

  * Booleanos podem ser objetos \(se definidos com a palavra-chave `new`\)
  * Números podem ser objetos \(se definidos com a palavra-chave `new`\)
  * Strings podem ser objetos \(se definidos com a palavra-chave `new`\)
  * Datas sempre são objetos
  * Maths sempre são objetos
  * Expressões regulares são sempre objetos
  * Arrays são sempre objetos
  * Funções são sempre objetos
  * Objetos são sempre objetos

Todos os valores de JavaScript, excetos os primitivos, são objetos.

### Valores Primitivos em JavaScript

Um valor primitivo é um valor que não tem propridades ou métodos.

Um tipo de dado prinitivo é um dado que tenha um valor primitivo.

JavaScript define 5 tipos de dados primitivos:

  * `string`
  * `number`
  * `boolean`
  * `null`
  * `undefined`

Valores primitivos são imutáveis \(eles estão embutidos na linguagem e não
  podem ser modificados\).

> se x = 3.14, você pode mudar o valor de x. Mas não pode mudar o valor de 3.14.

Valor | Tipo | Comentário
------|------|---------
"Alo" | `string` | "Alo" é sempre "Alo"
3.14 | `number` | 3.14 é sempre 3.14
`true` | `boolean` | `true` é sempre `true`
`false` | `boolean` | `false` é sempre `false`
`null` | `null` \(objeto\) | `null` é sempre `null`
`undefined` | `undefined` | `undefined` é sempre `undefined`

### Objetos são Variáveis

Variáveis de JavaScript podem conter valores simples:

Exemplo

```javascript
var pessoa = "José da Silva";
```

Objetos são variáveis, também. Mas objetos podem conter vários valores.

Os valores são escritos como pares `nome : valor` \(nome e valor separados por
  dois pontos\).

Exemplo

```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:50, corDosOlhos:"azul"};
```

> Um objeto JavaScript é uma coleção de valores com nomes.

### Propriedades de Objetos

Os valores com nomes, nos objetos de JavaScript, são chamados de propriedades.

Propriedade | Valor
---------|-------
nome  | José
sobrenome | da Silva
idade | 50
corDosOlhos | azul

Objetos escritos como pares `nome : valor` são similares a:

  * Arrays associativos em PHP
  * Dicionários em Python
  * Tabelas Hash em C
  * Mapas Hash em Java
  * Hashes em Ruby e Perl

### Métodos de Objetos

Métodos são ações que podem ser realizados em objetos.

Propriedades de objetos podem ser ambos, valores primitivos, outros objetos e
funções.

Um método de objeto é uma propriedade de objeto contendo uma definição de função.

Propriedade | Valor
---------|-------
nome | José
sobrenome | da Silva
idade | 50
corDosOlhos | azul
nomeCompleto | function\(\) {return this.nome + " " + this.sobrenome;}

> Objetos de JavaScript são repositórios de valores com nomes,
  chamados de propriedades e métodos.

### Criação de um Objeto em JavaScript

Com JavaScript, você pode definir e criar seus próprios objetos.

Existem diferentes maneiras de criar novos objetos:

  * Defina e crie um único objeto com o uso de um objeto literal.
  * Defina e crie um único objeto com a palavra-chave `new`.
  * Defina um construtor de objetos e, então, crie objetos do tipo construído.

>  A partir do ECMAScript 5, um objeto pode ser criado também com a função
   `Object.create()`.

#### Uso de um Objeto Literal

This is the easiest way to create a JavaScript Object.

Using an object literal, you both define and create an object in one statement.

An object literal is a list of name:value pairs \(like age:50\) inside curly braces {}.

The following example creates a new JavaScript object with four properties:

Exemplo

```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

Spaces and line breaks are not important. An object definition can span multiple lines:

Exemplo

```javascript
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

#### Using the JavaScript Keyword new

The following example also creates a new JavaScript object with four properties:

Exemplo

```javascript
var person = new Object();
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

    The two examples above do exactly the same. There is no need to use new Object().
    For simplicity, readability and execution speed, use the first one (the object literal method).

#### JavaScript Objects are Mutable

Objects are mutable: They are addressed by reference, not by value.

If person is an object, the following statement will not create a copy of person:

```javascript
var x = person;  // This will not create a copy of person.
```

The object x is not a copy of person. It is person. Both x and person are the same object.

Any changes to x will also change person, because x and person are the same object.

Exemplo
```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}

var x = person;
x.age = 10;           // This will change both x.age and person.age
```

    Note: JavaScript variables are not mutable. Only JavaScript objects.

## JavaScript Object Properties (https://www.w3schools.com/js/js_object_properties.asp)

Properties are the most important part of any JavaScript object.

### JavaScript Properties

Properties are the values associated with a JavaScript object.

A JavaScript object is a collection of unordered properties.

Properties can usually be changed, added, and deleted, but some are read only.

### Accessing JavaScript Properties

The syntax for accessing the property of an object is:

```javascript
objectName.property         // person.age
```

or

```javascript
objectName["property"]      // person["age"]
```

or

```javascript
objectName[expression]      // x = "age"; person[x]
```

The expression must evaluate to a property name.

#### Exemplo 1
```javascript
person.firstname + " is " + person.age + " years old.";
```

#### Exemplo 2
```javascript
person["firstname"] + " is " + person["age"] + " years old.";
```

### JavaScript for...in Loop

The JavaScript **for...in** statement loops through the properties of an object.

Syntax
```javascript
for (variable in object) {
  // code to be executed
}
```

The block of code inside of the **for...in** loop will be executed once for each property.

Looping through the properties of an object:

Exemplo
```javascript
var person = {fname:"John", lname:"Doe", age:25};

for (x in person) {
  txt += person[x];
}
```

### Adding New Properties

You can add new properties to an existing object by simply giving it a value.

Assume that the person object already exists - you can then give it new properties:

Exemplo
```javascript
person.nationality = "English";
```

    You cannot use reserved words for property (or method) names. JavaScript naming rules apply.

### Deleting Properties

The **delete** keyword deletes a property from an object:

Exemplo
```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
delete person.age;   // or delete person["age"];
```

The delete keyword deletes both the value of the property and the property itself.

After deletion, the property cannot be used before it is added back again.

The delete operator is designed to be used on object properties. It has no effect on variables or functions.

The delete operator should not be used on predefined JavaScript object properties. It can crash your application.

### Property Attributes

All properties have a name. In addition they also have a value.

The value is one of the property's attributes.

Other attributes are: enumerable, configurable, and writable.

These attributes define how the property can be accessed \(is it readable?, is it writable?\)

In JavaScript, all attributes can be read, but only the value attribute can be changed \(and only if the property is writable\).

\( ECMAScript 5 has methods for both getting and setting all property attributes\)

### Prototype Properties

JavaScript objects inherit the properties of their prototype.

The delete keyword does not delete inherited properties, but if you delete a prototype property, it will affect all objects inherited from the prototype.

## JavaScript Object Methods (https://www.w3schools.com/js/js_object_methods.asp)

#### Exemplo
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

### The **this** Keyword

In a function definition, **this** refers to the "owner" of the function.

In the example above, this is the person object that "owns" the fullName function.

In other words, this.firstName means the firstName property of this object.

Read more about the this keyword at JS this Keyword.

### JavaScript Methods

JavaScript methods are actions that can be performed on objects.

A JavaScript method is a property containing a function definition.

Property | Value
---------|-------
firstName | John
lastName | Doe
age | 50
eyeColor | blue
fullName | function\(\) {return this.firstName + " " + this.lastName;}

Methods are functions stored as object properties.

### Accessing Object Methods

You access an object method with the following syntax:

```javascript
objectName.methodName()
```

You will typically describe fullName\(\) as a method of the person object, and fullName as a property.

The fullName property will execute \(as a function\) when it is invoked with \(\).

This example accesses the fullName\(\) method of a person object:

Exemplo
```javascript
name = person.fullName();
```

If you access the fullName property, without \(\), it will return the function definition:

Exemplo
```javascript
name = person.fullName;
```

### Using Built-In Methods

This example uses the toUpperCase\(\) method of the String object, to convert a text to uppercase:

```javascript
var message = "Hello world!";
var x = message.toUpperCase();
```

The value of x, after execution of the code above will be:

  HELLO WORLD!

### Adding a Method to an Object

Adding a new method to an object is easy:

Exemplo
```javascript
person.name = function () {
  return this.firstName + " " + this.lastName;
};
```

## JavaScript Object Accessors (https://www.w3schools.com/js/js_object_accessors.asp)

### JavaScript Accessors (Getters and Setters)

ECMAScript 5 \(2009\) introduced Getter and Setters.

Getters and setters allow you to define Object Accessors \(Computed Properties\).

#### JavaScript Getter \(The get Keyword\)

This example uses a lang property to get the value of the language property.

Exemplo

```javascript
// Create an object:
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "en",
  get lang() {
    return this.language;
  }
};

// Display data from the object using a getter:
document.getElementById("demo").innerHTML = person.lang;
```

#### JavaScript Setter \(The set Keyword\)

This example uses a lang property to set the value of the language property.

Exemplo
```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "",
  set lang(lang) {
    this.language = lang;
  }
};

// Set an object property using a setter:
person.lang = "en";

// Display data from the object:
document.getElementById("demo").innerHTML = person.language;
```

### JavaScript Function or Getter?

What is the differences between these two examples?

Exemplo 1
```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// Display data from the object using a method:
document.getElementById("demo").innerHTML = person.fullName();
```

Exemplo 2
```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  get fullName() {
    return this.firstName + " " + this.lastName;
  }
};

// Display data from the object using a getter:
document.getElementById("demo").innerHTML = person.fullName;
```

Exemplo 1 access fullName as a function: person.fullName().

Exemplo 2 access fullName as a property: person.fullName.

The second example provides simpler syntax.

### Data Quality

JavaScript can secure better data quality when using getters and setters.

Using the lang property, in this example, returns the value of the language property in upper case:

#### Exemplo

```javascript
// Create an object:
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "en",
  get lang() {
    return this.language.toUpperCase();
  }
};

// Display data from the object using a getter:
document.getElementById("demo").innerHTML = person.lang;
```

Using the lang property, in this example, stores an upper case value in the language property:

#### Exemplo

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "",
  set lang(lang) {
    this.language = lang.toUpperCase();
  }
};

// Set an object property using a setter:
person.lang = "en";

// Display data from the object:
document.getElementById("demo").innerHTML = person.language;
```

### Why Using Getters and Setters?

  * It gives simpler syntax
  * It allows equal syntax for properties and methods
  * It can secure better data quality
  * It is useful for doing things behind-the-scenes

A Counter Exemplo

#### Exemplo

```javascript
var obj = {
  counter : 0,
  get reset() {
    this.counter = 0;
  },
  get increment() {
    this.counter++;
  },
  get decrement() {
    this.counter--;
  },
  set add(value) {
    this.counter += value;
  },
  set subtract(value) {
    this.counter -= value;
  }
};

// Play with the counter:
obj.reset;
obj.add = 5;
obj.subtract = 1;
obj.increment;
obj.decrement;
```

### Object.defineProperty\(\)

The Object.defineProperty\(\) method can also be used to add Getters and Setters:

#### Exemplo

```javascript
// Define object
var obj = {counter : 0};

// Define setters
Object.defineProperty(obj, "reset", {
  get : function () {this.counter = 0;}
});
Object.defineProperty(obj, "increment", {
  get : function () {this.counter++;}
});
Object.defineProperty(obj, "decrement", {
  get : function () {this.counter--;}
});
Object.defineProperty(obj, "add", {
  set : function (value) {this.counter += value;}
});
Object.defineProperty(obj, "subtract", {
  set : function (value) {this.counter -= value;}
});

// Play with the counter:
obj.reset;
obj.add = 5;
obj.subtract = 1;
obj.increment;
obj.decrement;
```

## JavaScript Object Constructors (https://www.w3schools.com/js/js_object_constructors.asp)

#### Exemplo

```javascript
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}
```

    It is considered good practice to name constructor functions with an upper-case first letter.

### Object Types \(Blueprints\) \(Classes\)

The examples from the previous chapters are limited. They only create single objects.

Sometimes we need a "blueprint" for creating many objects of the same "type".

The way to create an *object type*, is to use an **object constructor function**.

In the example above, function Person\(\) is an object constructor function.

Objects of the same type are created by calling the constructor function with the **new** keyword:

```javascript
var myFather = new Person("John", "Doe", 50, "blue");
var myMother = new Person("Sally", "Rally", 48, "green");
```

### The **this** Keyword

In JavaScript, the thing called **this** is the object that *owns* the code.

The value of this, when used in an object, is the object itself.

In a constructor function this does not have a value. It is a substitute for the new object. The value of this will become the new object when a new object is created.

    Note that this is not a variable. It is a keyword.
    You cannot change the value of this.

### Adding a Property to an Object

Adding a new property to an existing object is easy:

#### Exemplo

```javascript
myFather.nationality = "English";
```

The property will be added to myFather. Not to myMother. (Not to any other person objects).

### Adding a Property to a Constructor

You cannot add a new property to an object constructor the same way you add a new property to an existing object:

#### Exemplo

```javascript
Person.nationality = "English";
```

To add a new property to a constructor, you must add it to the constructor function:

Exemplo

```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.nationality = "English";
}
```

This way object properties can have default values.

### Adding a Method to a Constructor

Your constructor function can also define methods:

#### Exemplo

```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.name = function() {return this.firstName + " " + this.lastName;};
}
```

You cannot add a new method to an object constructor the same way you add a new method to an existing object.

Adding methods to an object must be done inside the constructor function:

#### Exemplo

```javascript
function Person(firstName, lastName, age, eyeColor) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
  this.eyeColor = eyeColor;
  this.changeName = function (name) {
    this.lastName = name;
  };
}
```

The changeName\(\) function assigns the value of name to the person's lastName property.

Now You Can Try:

```javascript
myMother.changeName("Doe");
```

JavaScript knows which person you are talking about by "substituting" this with myMother.

### Built-in JavaScript Constructors

JavaScript has built-in constructors for native objects:

#### Exemplo

```javascript
var x1 = new Object();    // A new Object object
var x2 = new String();    // A new String object
var x3 = new Number();    // A new Number object
var x4 = new Boolean();   // A new Boolean object
var x5 = new Array();     // A new Array object
var x6 = new RegExp();    // A new RegExp object
var x7 = new Function();  // A new Function object
var x8 = new Date();      // A new Date object
```

The Math\(\) object is not in the list. Math is a global object. The new keyword cannot be used on Math.

### Did You Know?

As you can see above, JavaScript has object versions of the primitive data types String, Number, and Boolean. But there is no reason to create complex objects. Primitive values are much faster.

ALSO:

  Use object literals {} instead of new Object\(\).

  Use string literals "" instead of new String\(\).

  Use number literals 12345 instead of new Number\(\).

  Use boolean literals true / false instead of new Boolean\(\).

  Use array literals [] instead of new Array\(\).

  Use pattern literals /()/ instead of new RegExp\(\).

  Use function expressions () {} instead of new Function\(\).

#### Exemplo

```javascript
var x1 = {};            // new object
var x2 = "";            // new primitive string
var x3 = 0;             // new primitive number
var x4 = false;         // new primitive boolean
var x5 = [];            // new array object
var x6 = /()/           // new regexp object
var x7 = function(){};  // new function object
```

### String Objects

Normally, strings are created as primitives: **var firstName = "John"**

But strings can also be created as objects using the new keyword: **var firstName = new String\("John"\)**

Learn why strings should not be created as object in the section JS Strings.

### Number Objects

Normally, numbers are created as primitives: **var x = 123**

But numbers can also be created as objects using the new keyword: **var x = new Number\(123\)**

Learn why numbers should not be created as object in the section JS Numbers.

### Boolean Objects

Normally, booleans are created as primitives: **var x = false**

But booleans can also be created as objects using the new keyword: **var x = new Boolean\(false\)**

Learn why booleans should not be created as object in the chapter JS Booleans.


## JavaScript Object Prototypes (JavaScript Object Prototypes)

All JavaScript objects inherit properties and methods from a prototype.

### Prototype Inheritance

All JavaScript objects inherit properties and methods from a prototype:

  **Date** objects inherit from **Date.prototype**
  **Array** objects inherit from **Array.prototype**
  **Person** objects inherit from **Person.prototype**

The **Object.prototype** is on the top of the *prototype inheritance chain*:

Date objects, Array objects, and Person objects inherit from Object.prototype.

### Adding Properties and Methods to Objects

Sometimes you want to add new properties (or methods) to all existing objects of a given type.

Sometimes you want to add new properties (or methods) to an object constructor.

#### Using the prototype Property

The JavaScript prototype property allows you to add new properties to object constructors:

##### Exemplo

```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.nationality = "English";
```

The JavaScript prototype property also allows you to add new methods to objects constructors:

##### Exemplo
```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.name = function() {
  return this.firstName + " " + this.lastName;
};
```

    Only modify your own prototypes.
    Never modify the prototypes of standard JavaScript objects.

## JavaScript ES5 Object Methods (https://www.w3schools.com/js/js_object_es5.asp)

ECMAScript 5 added a lot of new Object Methods to JavaScript.

### ES5 New Object Methods

```javascript
// Adding or changing an object property
Object.defineProperty(object, property, descriptor)

// Adding or changing many object properties
Object.defineProperties(object, descriptors)

// Accessing Properties
Object.getOwnPropertyDescriptor(object, property)

// Returns all properties as an array
Object.getOwnPropertyNames(object)

// Returns enumerable properties as an array
Object.keys(object)

// Accessing the prototype
Object.getPrototypeOf(object)

// Prevents adding properties to an object
Object.preventExtensions(object)
// Returns true if properties can be added to an object
Object.isExtensible(object)

// Prevents changes of object properties (not values)
Object.seal(object)
// Returns true if object is sealed
Object.isSealed(object)

// Prevents any changes to an object
Object.freeze(object)
// Returns true if object is frozen
Object.isFrozen(object)
```

### Changing a Property Value

#### Syntax

```javascript
Object.defineProperty(object, property, {value : value})
```

This example changes a property value:

#### Exemplo

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "EN"
};

// Change a property
Object.defineProperty(person, "language", {value : "NO"});
```

### Changing Meta Data

ES5 allows the following property meta data to be changed:

```javascript
writable : true      // Property value can be changed
enumerable : true    // Property can be enumerated
configurable : true  // Property can be reconfigured
```

```javascript
writable : false     // Property value can not be changed
enumerable : false   // Property can be not enumerated
configurable : false // Property can be not reconfigured
```

ES5 allows getters and setters to be changed:

```javascript
// Defining a getter
get: function() { return language }
// Defining a setter
set: function(value) { language = value }
```

This example makes language read-only:

```javascript
Object.defineProperty(person, "language", {writable:false});
```

This example makes language not enumerable:

```javascript
Object.defineProperty(person, "language", {enumerable:false});
```

### Listing All Properties

This example list all properties of an object:

#### Exemplo

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "EN"
};

Object.defineProperty(person, "language", {enumerable:false});
Object.getOwnPropertyNames(person);  // Returns an array of properties
```

### Listing Enumerable Properties

This example list only the enumerable properties of an object:

#### Exemplo
```javascript
var person = {
  firstName: "John",
  lastName : "Doe"
  language : "EN"
};

Object.defineProperty(person, "language", {enumerable:false});
Object.keys(person);  // Returns an array of enumerable properties
```

### Adding a Property

This example adds a new property to an object:

#### Exemplo
```javascript
// Create an object:
var person = {
  firstName: "John",
  lastName : "Doe",
  language : "EN"
};

// Add a property
Object.defineProperty(person, "year", {value:"2008"});
```

### Adding Getters and Setters
The Object.defineProperty\(\) method can also be used to add Getters and Setters:

#### Exemplo
```javascript
//Create an object
var person = {firstName:"John", lastName:"Doe"};

// Define a getter
Object.defineProperty(person, "fullName", {
  get : function () {return this.firstName + " " + this.lastName;}
});
```

### A Counter Exemplo

#### Exemplo
```javascript
// Define object
var obj = {counter:0};

// Define setters
Object.defineProperty(obj, "reset", {
  get : function () {this.counter = 0;}
});
Object.defineProperty(obj, "increment", {
  get : function () {this.counter++;}
});
Object.defineProperty(obj, "decrement", {
  get : function () {this.counter--;}
});
Object.defineProperty(obj, "add", {
  set : function (value) {this.counter += value;}
});
Object.defineProperty(obj, "subtract", {
  set : function (i) {this.counter -= i;}
});

// Play with the counter:
obj.reset;
obj.add = 5;
obj.subtract = 1;
obj.increment;
obj.decrement;
```

## JavaScript Function Definitions (https://www.w3schools.com/js/js_function_definition.asp)

JavaScript functions are defined with the **function** keyword.

You can use a function *declaration* or a function *expression*.

### Function Declarations

Earlier in this tutorial, you learned that functions are declared with the following syntax:

```javascript
function functionName(parameters) {
  // code to be executed
}
```

Declared functions are not executed immediately. They are "saved for later use", and will be executed later, when they are invoked (called upon).

Exemplo

```javascript
function myFunction(a, b) {
  return a * b;
}
```

    Semicolons are used to separate executable JavaScript statements.
    Since a function declaration is not an executable statement,
    it is not common to end it with a semicolon.

### Function Expressions

A JavaScript function can also be defined using an expression.

A function expression can be stored in a variable:

Exemplo
```javascript
var x = function (a, b) {return a * b};
```

After a function expression has been stored in a variable, the variable can be used as a function:

Exemplo
```javascript
var x = function (a, b) {return a * b};
var z = x(4, 3);
```

The function above is actually an anonymous function (a function without a name).

Functions stored in variables do not need function names. They are always invoked (called) using the variable name.

    The function above ends with a semicolon because it is a part of an
    executable statement.

###

## JavaScript Function Parameters (https://www.w3schools.com/js/js_function_parameters.asp)


## JavaScript Function Invocation (https://www.w3schools.com/js/js_function_invocation.asp)


## JavaScript Function Call (https://www.w3schools.com/js/js_function_call.asp)


## JavaScript Function Apply (https://www.w3schools.com/js/js_function_apply.asp)


## JavaScript Closures (https://www.w3schools.com/js/js_function_closures.asp)


## JavaScript HTML DOM (https://www.w3schools.com/js/js_htmldom.asp)


## JavaScript - HTML DOM Methods (https://www.w3schools.com/js/js_htmldom_methods.asp)


## JavaScript HTML DOM Document (https://www.w3schools.com/js/js_htmldom_document.asp)


## JavaScript HTML DOM Elements (https://www.w3schools.com/js/js_htmldom_elements.asp)


## JavaScript HTML DOM - Changing HTML (https://www.w3schools.com/js/js_htmldom_html.asp)


## JavaScript HTML DOM - Changing CSS (https://www.w3schools.com/js/js_htmldom_css.asp)


## JavaScript HTML DOM Animation (https://www.w3schools.com/js/js_htmldom_animate.asp)


## JavaScript HTML DOM Events (https://www.w3schools.com/js/js_htmldom_events.asp)


## JavaScript HTML DOM EventListener (https://www.w3schools.com/js/js_htmldom_eventlistener.asp)


## JavaScript HTML DOM Navigation (https://www.w3schools.com/js/js_htmldom_navigation.asp)


## JavaScript HTML DOM Elements \(Nodes\) (https://www.w3schools.com/js/js_htmldom_nodes.asp)


## JavaScript HTML DOM Collections (https://www.w3schools.com/js/js_htmldom_collections.asp)


## JavaScript HTML DOM Node Lists (https://www.w3schools.com/js/js_htmldom_nodelist.asp)


## JavaScript Window - The Browser Object Model (https://www.w3schools.com/js/js_window.asp)


## JavaScript Window Screen (https://www.w3schools.com/js/js_window_screen.asp)


## JavaScript Window Location (https://www.w3schools.com/js/js_window_location.asp)


## JavaScript Window History (https://www.w3schools.com/js/js_window_history.asp)


## JavaScript Window Navigator (https://www.w3schools.com/js/js_window_navigator.asp)


## JavaScript Popup Boxes (https://www.w3schools.com/js/js_popup.asp)


## JavaScript Timing Events (https://www.w3schools.com/js/js_timing.asp)


## JavaScript Cookies (https://www.w3schools.com/js/js_cookies.asp)
