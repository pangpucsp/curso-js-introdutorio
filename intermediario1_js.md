# Fundamentos VI de JavaScript

Esta é a continuação de [Fundamentos V de JS](fundamentos5_js.md).

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

A instrução `with` não é permitida:

```javascript
"use strict";
with (Math){x = cos(2)}; // Isto causa erro
```

Por motivo de segurança, `eval()` não é permitida a criação de variáveis no
escopo a partir do qual ele está sendo chamado:

```javascript
"use strict";
eval ("var x = 2");
alert (x);             // Isto causará erro
```

A palavra-chave `this` em funções comporta-se diferentemente no modo estrito.

A palavra-chave `this` refere-se a um objeto que chamou a função, se o objeto
não for especificado, funções no modo estrito retornam `undefined` e funções
no modo normal retornam o objeto global `windows`.

Exemplo

```JavaScript
"use strict";
function myFunction() {
  alert(this); // alerta "undefined"
}
myFunction();
```

### Reserva para o Futuro!
Palavras chaves reservadas para futuras versões de JavaScript não podem ser
usadas como nome de variáveis no modo estrito.

<table>
<tr><td>implements</td><td>interface</td><td>let</td></tr>
<tr><td>package</td><td>private</td><td>protected</td></tr>
<tr><td>public</td><td>static</td><td>yield</td></tr>
</table>

    **Atenção!**
    A diretiva "use strict" só é reconhecida no início de um script ou
    uma função.

## A Palavra-Chave `this` no JavaScript (https://www.w3schools.com/js/js_this.asp)

Exemplo

```javascript
var pessoa = {
  nome: "José",
  sobrenome : "da Silva",
  id       : 5566,
  nomeCompleto : function() {
    return this.nome + " " + this.sobrenome;
  }
};
```

### O Que É o `this`?

A palavra-chave `this` do JavaScript refere-se ao objeto a que ela pertence.

Ela tem valores diferentes dependendo de onde ela está sendo usada:

  - Num método, o `this` refere-se ao **objeto proprietário**.
  - Sózinha, o `this` refere-se ao **objeto global**.
  - Numa função, o `this` refere-se ao **objeto global**.
  - Numa função, no modo estrito, o `this` é `undefined`.
  - Num **evento**, o `this` refere-se ao **elemento** que recebeu o evento.
  - Métodos como `call()` e `apply()` podem referenciar `this` a
    **qualquer objeto**.

#### `this` num Método

Num método de um objeto, o `this` refere-se ao *proprietário* do método.

No exemplo, no início desta seção, o `this` refere-se ao objeto `pessoa`.

O objeto `pessoa` é o proprietário do método `nomeCompleto`.

```javascript
nomeCompleto : function() {
  return this.nome + " " + this.sobrenome;
}
```

### O `this` Sózinho

Quando usado sózinho, o proprietário é o *objeto global*, então o `this`
refere-se ao objeto `Global`.

Num navegador, o objeto `Global` é o objeto `Window`.

Exemplo

```javascript
var x = this;
```

No modo modo estrito, quando usado sózinho, o `this` também refere-se ao
objeto `Global` o \[objeto Window\]:

Exemplo

```javascript
"use strict";
var x = this;
```

### O `this` numa Função \(Default\)

Numa função em JavaScript, o proprietário da função é a ligação *default*
do `this`.

Então, numa função, o `this` refere-se ao objeto `Global`, o \[objeto Window\].

Exemplo

```javascript
function myFunction() {
  return this;
}
```

### O `this` numa Função \(Strict\)

JavaScript no *modo estrito* não permite uma ligação *default*.

Logo, quando usado numa função, no modo estrito, o `this` é `undefined`.

Exemplo

```javascript
"use strict";
function myFunction() {
  return this;
}
```

### O `this` em Manipuladores de Eventos

Em manipuladores de eventos de HTML, o `this` refere-se ao elemento de HTML
que recebeu o evento:

Exemplo

```html
<button onclick="this.style.display='none'">
  Clique para Me Remover!
</button>
```

### Ligação de Mètodo com o Objeto

Nestes exemplos, o `this` é o objeto `pessoa` \(O objeto `pessoa` é o
 "proprietário" da função\):

Exemplo

```javascript
var pessoa = {
  nome  : "José",
  sobrenome   : "da Silva",
  id         : 5566,
  minhaFuncao : function() {
    return this;
  }
};
```

Exemplo

```javascript
var pessoa = {
  nome: "José",
  sobrenome : "da Silva",
  id       : 5566,
  nomeCompleto : function() {
    return this.nome + " " + this.sobrenome;
  }
};
```

Em outras palavras: `this.nome` significa a propriedade `nome` do objeto `pessoa`.

### Ligação da Função Explícita

Os métodos `call()` e o `apply()` são métodos predefinidos em JavaScript.

Ambos podem ser usados para chamar o método de um objeto com outro objeto como
argumento.

No exemplo abaixo, ao chamar `pessoa1.nomeCompleto` com `pessoa2` como
argumento, o `this` refere-se à `pessoa2`, apesar de usar um método da
`pessoa1`:

Exemplo

```javascript
var pessoa1 = {
  nomeCompleto: function() {
    return this.nome + " " + this.sobrenome;
  }
}
var pessoa2 = {
  nome:"José",
  sobrenome: "da Silva",
}
pessoa1.nomeCompleto.call(pessoa2);  // Retornará "José da Silva"
```

## O `let` JavaScript (https://www.w3schools.com/js/js_let.asp)

### ECMAScript 2015

A ES2015 introduziu duas novas palavras-chaves importantes em JavaScript:
let and const.

Estas duas palabras chaves fornecem **Escopo de Bloco** \(e constantes\)
em JavaScript.

Antes da ES2015, o JavaScript só tinha dois tipos de escopos: *Escopo Global*
e *Escopo de Função*.

### Escopo Global

Variáveis declaradas Globalmente \(fora de qualquer função\) têm Escopo Global.

Exemplo

```javascript
var marcaCarro = "Toyota";

// código aqui pode usar marcaCarro

function myFunction() {
  // código aqui também pode usar marcaCarro
}
```

Variáveis globais podem ser acessadas em qualquer lugar num programa
JavaScript.

### Escopo de Função

Variáveis declaradas **Locamente** \(dentro de uma função\) têm **Escopo de
Função**.

Exemplo

```javascript
// código aqui NÃO pode usar marcaCarro

function myFunction() {
  var marcaCarro = "Honda";
  // código aqui PODE usar marcaCarro
}

// código aqui NÃO pode usar marcaCarro
```

Variáveis locais só podem ser acessadas de dentro da função onde elas
foram declaradas.

### Escopo de Bloco em JavaScript

Variáveis declaradas com a palavra-chave **var** não podem ter Escopo de Bloco.

Variáveis declaradas dentro de um bloco \{\} podem ser acessadas de fora
do bloco.

Exemplo

```javascript
{
  var x = 2;
}
// x PODE ser usada aqui
```

Antes da ES2015, JavaScript não tinha **Escopo de Bloco**.

Variáveis declaradas com a palavra-chave `let` pode ter um *Escopo de Bloco*.

Varáveis declaradas com `let` dentro de um bloco \{\} não podem ser
acessadas de fora do bloco:

Exemplo

```javascript
{
  let x = 2;
}
// x NÃO pode ser acessada aqui
```

### Redeclaração de Variáveis

Redeclarar uma variável com a palavra-chave `var` pode impor alguns problemas.

Redeclarar uma variável dentro de um bloco também vai redeclará-la fora do
bloco:

Exemplo

```javascript
var x = 10;
// Aqui x vale 10
{
  var x = 2;
  // Aqui x vale 2
}
// Aqui x vale 2
```

Redeclarar uma variável com a palavra-chave `let` pode resolver este problema.

Redeclarar uma variável dentro de um bloco não redeclara a variável fora do
bloco:

Exemplo

```javascript
var x = 10;
// Aqui x vale 10
{
  let x = 2;
  // Aqui x vale 2
}
// Aqui x vale 10 de novo
```

### Escopo de *Loop*

O uso de `var` num *loop*:

Exemplo

```javascript
var i = 5;
for (var i = 0; i < 10; i++) {
  // algumas instruções
}
// Aqui i vale 10
```

Uso de `let` dentro de um *loop*:

Exemplo

```javascript
let i = 5;
for (let i = 0; i < 10; i++) {
  // algumas instruções
}
// Aqui i vale 5
```

No primeiro exemplo, uso de `var`, a variável declarada no *loop* redeclara
a variável de fora do *loop*.

No segundo exemplo, uso do `let`, a variável declarada no `loop` não redeclara
a variável de fora do *loop*.

Quando o `let` é usado para declarar a variável `i` dentro do *loop*, a
variável `i` só será visível de dentro do *loop*.

### Escopo de Função

Variáveis declaradas com `var` e `let` são bastante semelhantes quando
declaradas dentro de uma função.

Ambas terão um Escopo de Função:

```javascript
function minhaFuncao() {
  var marcaCarro = "VW";   // Escopo de Função
}
function minhaFuncao() {
  let marcaCarro = "Ford";   // Escopo de Função
}
```

### Escopo Global

Variáveis declaradas com `var` e `let` são quase similares quando são
declaradas fora de um bloco.

Ambos terão Escopo Global:

```javascript
var x = 2;       // Escopo Global
let x = 2;       // Escopo Global
```

### Variáveis Globais em HTML

Com JavaScript, o escopo global é o ambiente de JavaScript.

Em HTML, o escopo global é o objeto `window`.

Variáveis globais definidas com a palavra-chave `var` pertencem ao
objeto `window`:

Exemplo

```javascript
var marcaCarro = "Renault";
// código aqui pode usar window.marcaCarro
```

Variáveis globais definidas com a palavra-chave `let` não pertencem ao
objeto `window`:

Exemplo

```javascript
let marcaCarro = "Hyundai";
// código aqui NÃO pode usar window.marcaCarro
```

### Redeclaração

Redeclarar uma variável JavaScript com `var` é permitida em qualquer lugar
num programa:

Exemplo

```javascript
var x = 2;

// Agora x vale 2

var x = 3;

// Agora x vale 3
```

Redeclarar uma variável `var` com `let`, no mesmo escopo, ou no mesmo bloco,
não é permitido:

Exemplo
```javascript
var x = 2;       // Permitido
let x = 3;       // Não permitido

{
  var x = 4;   // Permitido
  let x = 5   // Não permitido
}
```

Redelarar uma variável com `let`, no mesmo escopo, ou no mesmo bloco,
não é permitido:

Exemplo
```javascript
let x = 2;       // Permitido
let x = 3;       // Não permitido

{
  let x = 4;   // Permitido
  let x = 5;   // Não permitido
}
```

Redeclarar uma variável `let` com `var`, no mesmo escopo, ou no mesmo bloco,
não é permitido:

Exemplo
```javascript
let x = 2;       // Permitido
var x = 3;       // Não permitido

{
  let x = 4;   // Permitido
  var x = 5;   // Não permitido
}
```

Redeclarar uma variável com `let`, num outro escopo, ou num outro bloco,
é permitido:

Exemplo
```javascript
let x = 2;       // Permitido

{
  let x = 3;   // Permitido
}

{
  let x = 4;   // Permitido
}
```

### Promoção

Variáveis definidas com `var` são promovidas para o topo.

Você pode usar uma variável antes dela ser declarada:

Exemplo

```javascript
// Você PODE usar marcaCarro aqui
var marcaCarro;
```

Variáveis definidas com `let` não são promovidas para o topo.

Usar uma variável `let` antes dela ser declarada resultará em `ReferenceError`.

A variável está numa *zona morta temporal* do início do bloco até que
ela seja declarada.

Exemplo

```javascript
// Você NÃO pode usar marcaCarro aqui
let marcaCarro;
```

## Const em JavaScript (https://www.w3schools.com/js/js_const.asp)

### ECMAScript 2015

A ES2015 introduziu duas novas palavras-chaves importantes no JavaScript:
`let` e `const`.

Variáveis definidas com `const` comportam-se como variáveis `let`, exceto
por elas não poderem receber novas atribuições:

Exemplo

```javascript
const PI = 3.141592653589793;
PI = 3.14;      // Isto produzirá um erro
PI = PI + 10;   // Isto também produzirá um erro
```

### Escopo de Bloco

Declarar uma variável com `const` é similar ao `let` quanto ao escopo de bloco.

O `x` declarado no bloco, neste exemplo, não é o mesmo que o `x`
declarado fora do bloco:

Exemplo

```javascript
var x = 10;
// Aqui x vale 10
{
  const x = 2;
  // Aqui x vale 2
}
// Aqui x vale 10
```

### Atribuída quando Declarada

Variáveis `const` em JavaScript devem ser atribuídas quando elas são declaradas:

#### Incorreto

```javascript
const PI;
PI = 3.14159265359;
```

#### Correto

```javascript
const PI = 3.14159265359;
```

### Não São Constantes Reais

A palavra-chave **const** é uma pouco enganadora.

Ela NÃO define um valor constante. Ela define uma referência constante a
um valor.

Por causa disto, não podemos mudar valores primitivos constantes, mas
podemos mudar as propriedades de objetos "constantes".

### Valores Primitivos

Se atribuimos um valor primitivo a uma constante, não podemos mudar o valor
primitivo.

Exemplo

```javascript
const PI = 3.141592653589793;
PI = 3.14;      // Isto produzirá um erro
PI = PI + 10;   // Isto também produzirá um erro
```

### Objetos Constantes Podem Mudar

Você pode mudar as propriedades de um objeto constante:

Exemplo

```javascript
// Você pode criar um objeto constante:
const carro = {tipo:"Fiat", modelo:"uno", cor:"branco"};

// Você pode mudar uma propriedade:
carro.cor = "vermelho";

// Você pode adicionar uma propriedade:
carro.dono = "Abel";
```

Porém, você NÃO pode reatribuir um objeto constante:

Exemplo

```javascript
const carro = {tipo:"Fiat", modelo:"uno", cor:"branco"};
carro = {tipo:"Citroen", modelo:"C3", cor:"vermelho"};    // ERRO
```

### Arrays Contantes Podem Mudar

Você pode mudar os elementos de um *array* constante:

Exemplo

```javascript
// Você pode criar um array constante:
const carros = ["Mercedes", "Ford", "Hyundai"];

// Você pode mudar um elemento:
carros[0] = "Toyota";

// Você pode adicionar um elemento:
carros.push("Audi");
```

### Promoção

Variáveis definidas com `const` não são promovidas para o topo.

Uma variável `const` não pode ser usada antes dela ser declarada:

Exemplo

```javascript
marcaCarro = "Volvo";    // Você NÃO pode usar marcaCarro
const marcaCarro = "BMW";
```

[Próxima unidade](intermediario2_js.md)
