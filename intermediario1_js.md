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

### Ligação de Método com o Objeto

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

## ECMAScript 2015

A ES2015, também conhecido como ES6, introduziu duas novas palavras-chaves
importantes em JavaScript: `let` e `const`.

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

Redeclarar uma variável com `let`, no mesmo escopo, ou no mesmo bloco,
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

### Const em JavaScript (https://www.w3schools.com/js/js_const.asp)

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

A palavra-chave **const** é um pouco enganadora.

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

### Funções Usando [Flechas](https://www.w3schools.com/js/js_arrow_function.asp)

As funções usando flechas também foram introduzidas no ES6.

Funções usando flechas permitem que escrevamos funções com uma sintaxe mais
abreviada.

    Antes:
```javascript
hello = function() {
  return "Hello World!";
}
```

    Com Funções usando flechas:
```javascript
hello = () => {
  return "Hello World!";
}
```

Pode ser ainda mais curto! Se a função tem apenas uma instrução, e a
instrução retorna um valor, você pode eliminar as chaves e a palavra-chave
`return`:

    Arrow Functions Return Value by Default:
```javascript
hello = () => "Hello World!";
```

    Nota: Isto só funciona com funções de uma única instrução.

Se você tiver parâmetros, você pode passá-los dentro dos parenteses:

    Função com Flecha com Parâmetros:
```javascript
hello = (val) => "Hello " + val;
```

De fato, se você só tiver um parâmetro, você pode pular os parâmetros também:

    Arrow Function Without Parentheses:
```javascript
hello = val => "Hello " + val;
```

#### E o `this`?

A manipulação do `this` também é diferente nas funções com flechas em relação
às funções normais.

Resumindo, em funções com flechas, não há ligação com o `this`.

Nas funções normais, a palavra-chave `this` representa o objeto que chamou
a função, que poderia ser a `window`, o `document`, um botão ou outra coisa.

Com funções com flechas, a palavra-chave `this` sempre representa o objeto
que definiu a função com flecha.

Vejamos dois exemplos para entender a diferença.

Ambos chamam um método duas vezes, a primeira quando a página carrega e
uma outra vez quando um botão é acionado.

O primeiro exemplo usa uma função normal e o segundo usa uma função com flecha.

O resultado mostra que o primeiro exemplo retorna dois objetos diferentes
\(`window` e `button`\) e o segudo exemplo retorna o objeto `window` duas
vezes, porque o objeto `window` é o *proprietário* da função.

Exemplo
Numa função normal, o `this` representa o objeto que chama a função:

```javascript
//Função normal:
alo = function() {
  document.getElementById("demo").innerHTML += this;
}

//O objeto window chama a função:
window.addEventListener("load", alo);

//Um objeto button chama a função:
document.getElementById("btn").addEventListener("click", alo);
```

Exemplo
Numa função com flecha, o `this` representa o proprietário da função:

```javascript
//Função com Flecha:
alo = () => {
  document.getElementById("demo").innerHTML += this;
}

//O objeto window chama a função:
window.addEventListener("load", alo);

//Um objeto button chama a função:
document.getElementById("btn").addEventListener("click", alo);
```

Lembre-se dessas diferenças ao trabalhar com funções. Algumas vezes, o
comportamento das funções normais é o que você quer, se não for, use
funções com flechas.

### [Classes em JavaScript](https://www.w3schools.com/js/js_classes.asp)

ES6, conhecida como ECMAScript2015, também introduziu classes em JavaScript.

Uma classe é um tipo de função, mas, em vez de usar a palavra-chave `function`
para inicializá-la, usamos a palavra-chave `class` e as propriedades são
atribuídas dentro de um método `constructor()`.

#### Definição de Classes

Use a palavra-chave `class` cria uma classe e sempre adiciona um método
construtor.

O método construtor é chamado cada vez que um objeto da classe é instanciado.

Exemplo: Uma definição simples de uma classe chamada de "Carro":

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
}
```
Agora, você pode criar objetos usando a classe `Carro`:

Exemplo: Cria um objeto chamado de meuCarro baseado na classe `Carro`

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
}
meuCarro = new Carro("VW");
```

    Nota: O método `constructor()` é chamado automaticamente quando
    o objeto é inicializado.

#### Métodos

O método `constructor()` é especial, é nele que você inicializa as
propriedades, ele é chamado automaticamente quando uma classe é instanciada
e ele deve ter exatamente o nome `constructor`. De fato, se você não tiver
um método `constructor`, JavaScript adicionará um método `constructor`
invisível e vazio.

Você também está liberado para fazer seus próprios métodos,
a sintaxe deve ser familiar:

Exemplo: Cria um método chamado `presente`:

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  presente() {
    return "Eu tenho um " + this.marcaCarro;
  }
}

meuCarro = new Carro("VW");
document.getElementById("demo").innerHTML = meuCarro.presente();
```

Como você pode ver no exemplo acima, você chama o método referindo-se ao
nome do método do objeto seguido de parenteses \(os parâmetros, se houver,
  devem ir dentro dos parenteses\).

Exemplo
Envie um parâmetro ao método `presente()`:

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  presente(x) {
    return x + ", eu tenho um " + this.marcaCarro;
  }
}

meuCarro = new Carro("Ford");
document.getElementById("demo").innerHTML = meuCarro.presente("Alô");
```

#### Métodos Estáticos

Métodos estáticos são definidos na própria classe e não no protótipo.

Isto significa que você *não pode chamar* um método estático com o objeto
\(`meuCarro`\), mas com a classe \(`Carro`\):

Exemplo: Cria um método estático e chama ele com a classe.

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  static alo() {
    return "Alô!!";
  }
}

meuCarro = new Carro("Ford");

// Chama 'alo()' com a classe Carro:
document.getElementById("demo").innerHTML = Carro.alo();

// e não com o objeto 'meuCarro':
// document.getElementById("demo").innerHTML = meuCarro.alo();
// isto lançaria um erro.
```

Se você quiser usar o objeto `meuCarro` dentro do método estático,
você pode enviá-lo como um parâmetro:

Exemplo: Envie `meuCarro` como um parâmetro:

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  static alo(x) {
    return "Alô " + x.marcaCarro;
  }
}

meuCarro = new Carro("Ford");

document.getElementById("demo").innerHTML = Carro.alo(meuCarro);
```

#### Herança

Para criar uma hierarquia de classes, use a palavra-chave `extends`.

Uma classe craida com herança de classes herda todos os métodos de uma
outra classe:

Exemplo: Cria uma classe com o nome `Modelo` que herdará os métodos da
classe `Carro`
```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  presente() {
    return 'Eu tenho um ' + this.marcaCarro;
  }
}

class Modelo extends Carro {
  constructor(marca, mod) {
    super(marca);
    this.modelo = mod;
  }
  mostra() {
    return this.presente() + ', é um ' + this.modelo;
  }
}

meuCarro = new Modelo("Honda", "Civic");
document.getElementById("demo").innerHTML = meuCarro.mostra();
```

O método `super()` refere-se à classe mãe.

Ao chamar o método `super()` no método `constructor`, chamamos o método
`constructor` da mãe e obtemos acesso às propriedades e métodos da mãe.

#### Getters and Setters

Classes também permitem que você use `getters` e `setters`
\(leitores e modificadores de propriedades\).

Pode ser inteligente usar `getters` e `setters` para as suas propriedades,
especialmente se você quiser fazer algo especial com o valor antes de
retorná-los, ou antes de modificá-los.

Para adicionar `getters` e `setters` na classe, use as palavras-chaves
`get` e `set`.

Exemplo: Cria um `getter` e um `setter` para a propriedade `marcaCarro`:

```javascript
class Carro {
  constructor(marca) {
    this.marcaCarro = marca;
  }
  get marcac() {
    return this.marcaCarro;
  }
  set marcac(x) {
    this.marcaCarro = x;
  }
}

meuCarro = new Carro("Honda");

document.getElementById("demo").innerHTML = meuCarro.marcac;
```

    Nota: mesmo se o getter é um método, você não usa parênteses quando quiser
    obter o valor da propriedade.

O nome dos métodos `getter/setter` não pode ser o mesmo da propriedade,
no caso `marcaCarro`.

Muitos programadores usam um carácter sublinhado \_ antes do nome da
propriedade para separar os `getter/setter` da propriedade:

Exemplo: Você pode usar o carácter sublinhado para separar os getter/setter
da propriedade

```javascript
class Carro {
  constructor(marca) {
    this._marcaCarro = marca;
  }
  get marcaCarro() {
    return this._marcaCarro;
  }
  set marcaCarro(x) {
    this._marcaCarro = x;
  }
}

meuCarro = new Carro("Honda");

document.getElementById("demo").innerHTML = meuCarro.marcaCarro;
```

Para usar um `setter`, use a mesma sintaxe de quando você usa para modificar
o valor de uma propriedade, parênteses:

Exemplo: Usa um `setter` para mudar o valor de marcaCarro para "Toyota".

```javascript
class Carro {
  constructor(marca) {
    this._marcaCarro = marca;
  }
  get marcaCarro() {
    return this._marcaCarro;
  }
  set marcaCarro(x) {
    this._marcaCarro = x;
  }
}

meuCarro = new Carro("Fiat");
meuCarro.marcaCarro = "Honda";
document.getElementById("demo").innerHTML = meuCarro.marcaCarro;
```

#### Promoção

Diferente de funções e outras declarações de JavaScript, declarações de classes
não são promovidas.

Isto significa que você precisa declarar uma classe antes de poder usá-la:

Exemplo
```javascript
// Você ainda não pode usar a classe.
// meuCarro = new Carro("Ford")
// Isto iria lançar um erro.

class Carro {
  constructor(marca) {
    this.meuCarro = marca;
  }
}

// Agora você pode usar a classe:
meuCarro = new Carro("Ford");
```

    Nota: Para outras declarações, como funções, você NÃO terá um error
    se tentar usá-lo antes de declará-lo. Porque o comportamento padrão das
    declarações é a promoção (move a declaração para o topo).

#### "use strict"

A sintaxe nas classes devem ser escritas no *modo estrito*.

Você terá um `error` se não seguir as regras do *modo estrito*.

Exemplo: No *modo estrito*, você terá um erro se usar uma variável sem
declará-la:

```javascript
class Carro {
  constructor(marca) {
    i = 0;  // lança um erro quando um Carro for instanciado
    this.marcaCarro = marca;
  }
}
var meuCarro = new Carro("Ford");
```

[Próxima unidade](intermediario2_js.md)
