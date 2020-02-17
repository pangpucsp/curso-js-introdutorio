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

> Se x = 3.14, você pode mudar o valor de x. Mas não pode mudar o valor de 3.14.

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
nomeCompleto | `function\(\) {return this.nome + " " + this.sobrenome;}`

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

Esta é a maneira mais fácil de criar um Objeto JavaScript.

Ao usar um objeto literal, você tanto define, quanto cria um objeto em uma
instrução.

Um objeto literal é uma lista de pares de `nome:valor` \(como `idade:50`\)
dentro de chaves, `{}`.

O exemplo a seguir cria um novo objeto JavaScript com 4 propriedades:

Exemplo

```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:50, corDosOlhos:"azul"};
```

Espaços e quebras de linhas não são importantes. A definição de um objeto pode
se espalhar por várias linhas:

Exemplo

```javascript
var pessoa = {
  nome: "José",
  sobrenome: "da Silva",
  idade: 50,
  corDosOlhos: "azul"
};
```

#### Uso da Palavra-Chave `new` em JavaScript

O exemplo a seguir também cria um novo objeto JavaScript com 4 propriedades:

Exemplo

```javascript
var pessoa = new Object();
pessoa.nome = "José";
pessoa.sobrenome = "da Silva";
pessoa.idade = 50;
pessoa.corDosOlhos = "azul";
```

> Os dois exemplos acima são exatamente os mesmos. Não há a necessidade de usar
> `new Object()`. Por simplicidade, legibilidade e velocidade de execução,
> use o primeiro \(o método de objeto literal\).

#### Objetos em JavaScript são Mutáveis

Objetos são mutáveis: Eles são acessados por referência, não por valor.

Se `pessoa` é um objeto, a instrução a seguir não criará uma cópia de `pessoa`:

```javascript
var x = pessoa;  // Isto não cria uma cópia de pessoa.
```

O objeto `x` não é uma cópia de `pessoa`. Ele é `pessoa`. Tanto `x`, quanto
`pessoa` são o mesmo objeto.

Qualquer mudança em `x` também mudará em `pessoa`, porque `x` e `pessoa` são
o mesmo objeto.

Exemplo
```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:50, corDosOlhos:"azul"}

var x = pessoa;
x.idade = 10;           // Isto irá mudar tanto x.idade, quanto pessoa.idade
```

> Observação: As variáveis em JavaScript não são mutáveis. Apenas os objetos
> em JavaScript.

## Propriedades de Objetos em JavaScript
<!--
 https://www.w3schools.com/js/js_object_properties.asp
 -->

Propriedades são a parte mais importante de qualquer objeto em JavaScript.

### Propriedades em JavaScript

Propriedades são os valores associados a um objeto JavaScript.

Um objeto JavaScript é uma coleção de propriedades não ordenadas.

Propriedades podem, em geral, serem modificadas, adicionadas e removidas, mas
algumas são de *apenas leitura*.

### Accesso a Propriedades em JavaScript

A sintaxe para acessar a propriedade de um objeto é:

```javascript
nomeDoObjeto.propriedade         // pessoa.idade
```

ou

```javascript
nomeDoObjeto["propriedade"]      // pessoa["idade"]
```

ou

```javascript
nomeDoObjeto[expressao]      // x = "idade"; pessoa[x]
```

A expressão deve calcular o nome de uma propriedade.

#### Exemplo 1

```javascript
pessoa.nome + " tem " + pessoa.idade + " anos.";
```

#### Exemplo 2

```javascript
pessoa["nome"] + " tem " + pessoa["idade"] + " anos.";
```

### Loop `for...in` em JavaScript

A instrução de repetição **`for...in`** permite percorrer as propriedades de um
objeto.

Syntaxe:

```javascript
for (variável in objeto) {
  // código a ser executado
}
```

O bloco de código dentro do *loop* `for...in` será executado uma vez para cada
propriedade.

Percorrendo as propriedades de um objeto:

Exemplo

```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:25};
txt = "";
for (x in pessoa) {
  txt += pessoa[x];
}
// tem-se: txt === "Joséda Silva25"
```

### Acrescentando Novas Propriedades

Você pode acrescentar novas propriedades a um objeto existente simplesmente
dando-lhe um valor.

Assumindo que o objeto `pessoa` já exista, você pode lhe dar uma nova
propriedade:

Exemplo

```javascript
pessoa.nationalidade = "Atlantiano";
```

> Você não pode usar palavras reservadas para nome de propriedades
  \(ou para métodos\). As regras para nomes do JavaScript se aplicam para
  os nomes das propriedades e dos métodos.

### Remoção de Propriedades

A palavra-chave **`delete`** remove uma propriedade de um objeto:

Exemplo

```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:50, corDosOlhos:"azul"};
delete pessoa.idade;   // ou delete pessoa["idade"];
```

A palavra-chave `delete` remove tanto o valor da propriedade, quanto a própria
propriedade.

Após a remoção, a propriedade não pode ser usada antes de ser acrescentada de
volta.

O operador `delete` foi projetado para ser usado em propriedades de objetos.
Ele não tem efeito em variáveis ou funções.

O operador `delete` não deve ser usado em propriedades pré-definidas de
JavaScript. Isto pode quebrar sua aplicação.

### Atributos de Propriedades

Todas as propriedades têm um nome e um valor.

O valor é uma dos atributos de uma propriedade.

Os outros atributos são: `enumerable`, `configurable` e `writable`.

Estes atributos definem como a propriedade pode ser acessada \(é legível?,
  é modificável?\).

Em JavaScript, todos os atributos podem ser lidos, mas apenas o atributo de
`value` pode ser modificado e apenas se a propriedade for `writeable`.

\( ECMAScript 5 tem métodos para ler e modificar todos os atributos de uma
  propriedade.\)

### Propriedades de Protótipos

Objetos em JavaScript herdam as propriedades de seu protótipo.

A palavra-chave `delete` não remove propriedades herdadas, mas se você remover
uma propriedade de um protótipo, a remoção afetará todos os objetos que herdaram
do protótipo.

## Métodos de Objetos em JavaScript
<!--
https://www.w3schools.com/js/js_object_methods.asp)
-->

#### Exemplo

```javascript
var pessoa = {
  nome         : "José",
  sobrenome    : "da Silva",
  id           : 5566,
  nomeCompleto : function() {
    return this.nome + " " + this.sobrenome;
  }
};
```

### A Palavra-Chave **`this`**

Na definição da função, **`this`** refere-se ao *proprietário* da função.

No exemplo acima, `this` é o objeto `pessoa` que *possui* a função
`nomeCompleto`.

Em outras palavras, `this.nome` significa a propriedade `nome` deste objeto.

### Métodos em JavaScript

Métodos em JavaScript são ações que são realizadas sobre os objetos.

Um método em JavaScript é uma propriedade contendo a definição de uma função.

Propriedade | Valor
---------|-------
nome | José
sobrenome | da Silva
idade | 50
corDosOlhos | azul
nomeCompleto | `function() { return this.nome + " " + this.sobrenome; }`

Métodos são funções armazenadas como propriedades de objetos.

### Métodos para Acessar Objetos

Você pode acessar um método objeto com a seguinte sintaxe:

```javascript
nomeDoObjeto.nomeDoMetodo()
```

Você descreve tipicamente `nomeCompleto()` como um método do objeto `pessoa` e
`nomeCompleto` como uma propriedade.

A propriedade `nomeCompleto` executa \(como uma função\) quando ela é invocada
com \(\).

O exemplo a seguir acessa o método `nomeCompleto()` de um objeto `pessoa`:

Exemplo

```javascript
nome = pessoa.nomeCompleto();
```

Se você acessar a propriedade `nomeCompleto`, sem \(\), a definição da função
será retornada:

Exemplo
```javascript
nome = pessoa.nomeCompleto;
```

### Uso de Métodos Internos

Este Exemplo usa o método `toUpperCase()` do objeto String, para converter um
texto para maiúsculas:

```javascript
var mensagem = "Alo Mundo!";
var x = mensagem.toUpperCase();
```

O valor de x, após a execução do código acima será:

  Alo Mundo!

### Acréscimo de um Método a um Objeto

Acrescentar um novo método a um objeto é fácil:

Exemplo

```javascript
pessoa.nomeC = function () {
  return this.nome + " " + this.sobrenome;
};
```

## Acessores de Objetos em JavaScript
<!--
https://www.w3schools.com/js/js_object_accessors.asp
-->

### Acessores em JavaScript \(*Getters* e *Setters*\)

ECMAScript 5 \(2009\) introduziu *Getter* e *Setters*.

*Getters* e *setters* permitem que você defina Acessores a Objetos
\(Propriedades Calculadas\).

#### *Getter* em JavaScript \(A Palavra-Chave `get`\)

O exemplo a seguir usa uma propriedade `lang` para obter o valor da propriedade
`lingua`.

Exemplo

```javascript
// Cria um objeto:
var pessoa = {
  nome: "José",
  sobrenome : "da Silva",
  lingua : "pt",
  get lang() {
    return this.lingua;
  }
};

// Mostra dados de um objeto com o uso de um getter:
document.getElementById("demo").innerHTML = pessoa.lang;
```

#### *Setter* em JavaScript \(A Palavra-Chave `set`\)

Este exemplo usa uma propriedade `lang` para ajustar o valor da propriedade
`lingua`.

Exemplo
```javascript
var pessoa = {
  nome      : "José",
  sobrenome : "da Silva",
  lingua   : "",
  set lang(lang) {
    this.lingua = lang;
  }
};

// Modifica a propriedade de um objeto com o uso de um setter:
pessoa.lang = "pt";

// Mostra dados de um objeto:
document.getElementById("demo").innerHTML = pessoa.lingua;
```

### Função ou *Getter* em JavaScript?

Qual a diferença entre estes dois exemplos?

Exemplo 1

```javascript
var pessoa = {
  nome         : "José",
  sobrenome    : "da Silva",
  nomeCompleto : function() {
    return this.nome + " " + this.sobrenome;
  }
};

// Mostra os dados de um objeto com o uso de um método:
document.getElementById("demo").innerHTML = pessoa.nomeCompleto();
```

Exemplo 2

```javascript
var pessoa = {
  nome      : "José",
  sobrenome : "da Silva",
  get nomeCompleto() {
    return this.nome + " " + this.sobrenome;
  }
};

// Exibe os dados do objeto com o uso de um getter:
document.getElementById("demo").innerHTML = pessoa.nomeCompleto;
```

Exemplo 1 acessa `nomeCompleto` como uma função: pessoa.nomeCompleto().

Exemplo 2 acessa `nomeCompleto` como uma propriedade: pessoa.nomeCompleto.

O segundo exemplo fornece uma sintaxe mais simples.

### Qualidade dos Dados

JavaScript pode assegurar uma qualidade de dados melhor ao usar *getters* e
*setters*.

Usar a propriedade `lang`, neste exemplo, retorna o valor da propriedade
`lingua` em maiúsculas:

#### Exemplo

```javascript
// Cria um objeto:
var pessoa = {
  nome      : "José",
  sobrenome : "da Silva",
  lingua    : "pt",
  get lang() {
    return this.lingua.toUpperCase();
  }
};

// Mostra os dados de um objeto com o uso de um getter:
document.getElementById("demo").innerHTML = pessoa.lang;
```

A propriedade `lang`, no exemplo a seguir, é usada para armazenar o valor em
maiúsculas da propriedade `lingua`.

#### Exemplo

```javascript
var pessoa = {
  nome      : "José",
  sobrenome : "da Silva",
  lingua    : "",
  set lang(lang) {
    this.lingua = lang.toUpperCase();
  }
};

// Modificação de propriedade de um objeto com um setter:
pessoa.lang = "pt";

// Exibe os dados do objeto:
document.getElementById("demo").innerHTML = pessoa.lingua;
```

### Por que usar Getters e Setters?

  * A sintaxe é mais simples
  * Permite sintaxe igual para propriedades e métodos
  * Pode assegurar uma qualidade melhor de dados
  * É útil para fazer as coisas atrás dos panos

Um Contra Exemplo

#### Exemplo

```javascript
var obj = {
  contador : 0,
  get reset() {
    this.contador = 0;
  },
  get incremente() {
    this.contador++;
  },
  get decremente() {
    this.contador--;
  },
  set some(valor) {
    this.contador += valor;
  },
  set subtraia(valor) {
    this.counter -= valor;
  }
};

// Uso do contador:
obj.reset;
obj.some = 5;
obj.subtraia = 1;
obj.incremente;
obj.decremente;
```

### `Object.defineProperty()`

O método `Object.defineProperty()` pode ser usado para adicionar *Getters* e
*Setters*:

#### Exemplo

```javascript
// Defina o objeto
var obj = {contador : 0};

// Define setters
Object.defineProperty(obj, "reset", {
  get : function () {this.contador = 0;}
});
Object.defineProperty(obj, "incremente", {
  get : function () {this.contador++;}
});
Object.defineProperty(obj, "decremente", {
  get : function () {this.contador--;}
});
Object.defineProperty(obj, "some", {
  set : function (valor) {this.contador += valor;}
});
Object.defineProperty(obj, "subtraia", {
  set : function (valor) {this.contador -= valor;}
});

// Uso do contador:
obj.reset;
obj.some = 5;
obj.subtraia = 1;
obj.incremente;
obj.decremente;
```

## Construtores de Objetos em JavaScript
<!--
https://www.w3schools.com/js/js_object_constructors.asp
-->

#### Exemplo

```javascript
function Pessoa(nome, sobre, idade, olho) {
  this.nome = nome;
  this.sobrenome = sobre;
  this.idade = idade;
  this.corDosOlhos = olho;
}
```

> É considerado uma prática boa o nome de um construtor começar com uma letra
> maiúscula.

### Tipo Objeto \(Gabarito\) \(Classe\)

Os exemplos das seções anteriores são limitados. Eles criam apenas um objeto.

Algumas vezes precisamos de um *gabarito* para criar muitos objetos do mesmo
*tipo*.

A maneira de criar um *tipo objeto* é usar uma **função construtora de
Objetos**.

No exemplo acima, a função `Pessoa()` é uma função construtora de objetos.

Objetos do mesmo tipo são criados chamando a função construtora com a
palavra-chave **new**:

```javascript
var meuPai = new Pessoa("José", "da Silva", 50, "azul");
var minhaMae = new Pessoa("Maria", "de Carvalho", 48, "verde");
```

### A Palavra-Chave **this**

Em JavaScript, a coisa chamada **this** é o objeto que *possui* o código.

O valor do `this`, quando usado dentro da definição de um objeto, é o próprio
objeto.

Num construtor, `this` não tem valor. Ele é um substituto para o novo objeto.
O valor do `this` torna-se o novo objeto quando o novo objeto for criado.

> Observe que `this` não é uma variável. É uma palavra-chave. Você não pode
> mudar o valor do `this`.

### Acréscimo de uma Propriedade a um Objeto

O acréscimo de uma propriedade a um objeto existente é simples:

#### Exemplo

```javascript
meuPai.nacionalidade = "Português";
```

A propriedade será acrescentada a `meuPai`. Não a `minhaMae`. \(Nem a nenhum
  outro objeto\).

### Acréscimo de uma Propriedade a um Construtor

Você não pode acrescentar uma nova propriedade a um construtor de objetos do
mesmo modo que você o faz com um objeto existente:

#### Exemplo Errado

```javascript
Pessoa.nacionalidade = "Português";
```

Para acrescentar uma propriedade a um construtor, você precisa acrescentá-la na
função construtora:

Exemplo

```javascript
function Pessoa(nome, sobre, idade, olho) {
  this.nome = nome;
  this.sobrenome = sobre;
  this.idade = idade;
  this.corDosOlhos = olho;
  this.nacionalidade = "Português";
}
```

Desta maneira, propriedades de objetos podem ter valores padrões.

### Acréscimo de um Método a um Construtor

Sua função construtora também pode definir métodos:

#### Exemplo

```javascript
function Pessoa(nome, sobre, idade, olho) {
  this.nome = nome;
  this.sobrenome = sobre;
  this.idade = idade;
  this.corDosOlhos = olho;
  this.nomeC = function() {return this.nome + " " + this.sobrenome;};
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
