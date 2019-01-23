# Fundamentos de JavaScript

Este texto é baseado no [W3CSchools javascript tutorial](https://www.w3schools.com/js/).

  JavaScript é a linguagem de programação para HTML e a Web.

## Introdução \([JS Tutorial](https://www.w3schools.com/js/)\)

Recomenda-se que os códigos de JavaScript oferecidos neste texto sejam testados usando a console do navegador Chrome. Para ter acesso a esta console, com o foco do mouse no navegador, acione F12 no seu teclado. A tela atual será dividida em duas metades e na segunda metade, a da direita, temos as ferramentas de desenvolvimento WEB embutidas no navegador Chrome. Selecione a aba console e insira após o prompt \(> \) as instruções Javascript dadas neste texto.

Alguns dos exemplos de código JavaScript podem precisar de adaptações para serem executados na console do navegador Chrome.

Exemplo [first.html](first.html)

```html
<!DOCTYPE html>
<html>
<body>

<h2>Meu Primeiro JavaScript</h2>

<button type="button"
onclick="document.getElementById('demo').innerHTML = Date()">
Acione-me para ver a Data e o Horário atual.</button>

<p id="demo"></p>

</body>
</html>
```

### Por que aprender JavaScript?

JavaScript é uma das 3 linguagens que todo desenvolvedor web deve aprender:

   1. **HTML** para definir o conteúdo das páginas web;

   2. **CSS** para especificar o layout, a aparência, das páginas web; e

   3. **JavaScript** para programar o comportamento das páginas web.

Referências:
[Javascript reference](https://www.w3schools.com/jsref/default.asp)

### JavaScript Pode Mudar o Conteúdo do HTML

Demo: [intro_demo1.html](intro_demo1.html)
```javascript
document.getElementById("demo").innerHTML = "Alo JavaScript!";
```

**Strings** em JS podem ser definidas com aspas \("\) ou apóstrofes \('\):

Demo:
```javascript
document.getElementById('demo').innerHTML = 'Alo JavaScript!'; // é o mesmo que
document.getElementById("demo").innerHTML = "Alo JavaScript!";
```

### JavaScript Pode Mudar os Valores de Atributos do HTML

Demo: [Demo 2: mudança de valor de atributo](intro_demo2.html)

```html
<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Acenda a luz</button>

<img id="myImage" src="pic_bulboff.gif" style="width:100px">

<button onclick="document.getElementById('myImage').src='pic_bulboff.gif'">Apague a luz</button>
```
### JavaScript Pode Mudar Estilos do HTML \(CSS\)

Demo: [Demo 3: mudança de estilo](intro_demo3.html)

```javascript
document.getElementById("demo").style.fontSize = "35px";
```

### JavaScript Pode Esconder Elementos do HTML

Demo: [Demo 4: escondendo elemento](intro_demo4.html)

```javascript
document.getElementById("demo").style.display = "none";
```

### JavaScript Pode Mostrar Elementos do HTML

Demo: [Demo 5: mostrando elementos escondidos](intro_demo5.html)

```javascript
document.getElementById('demo').style.display = 'block';
```

## Onde Fica o JavaScript ? \([Where To](https://www.w3schools.com/js/js_whereto.asp)\)

### O Tag <script>

Em HTML, o código JavaScript deve ser inserido entre as tags <script> e </script>.

Exemplo: [Demo](where_demo1.html)

```html
<script>
document.getElementById("demo").innerHTML = "Meu Prmeiro JavaScript";
</script>
```

### Funções e Eventos de JavaScript

Uma função JavaScript é um bloco de código JavaScript que pode ser executado quando ele é *chamado*.

Por exemplo, uma função é chamada quando um evento ocorre, como quando um usuário aciona um botão.

### JavaScript no \<head\> ou no \<body\>

Você pode colocar tantos scripts quantos você quiser num documento HTML.

Scripts podem ser colocados na seção de \<body\>, ou na seção de \<head\> de uma página HTML, ou em ambas.

#### JavaScript no \<head\>

Exemplo: [Demo: JS no head](where_demo2.html)
```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Parágrafo Mudou.";
}
</script>
</head>
<body>

<h1>Uma Página HTML</h1>
<p id="demo">Um Parágrafo.</p>
<button type="button" onclick="myFunction()">Teste</button>

</body>
</html>
```

#### JavaScript no \<body\>

Example: [Demo: JS no body](where_demo3.html)
```html
<!DOCTYPE html>
<html>
<body>

<h1>Uma Página HTML</h1>
<p id="demo">Um Parágrafo.</p>
<button type="button" onclick="myFunction()">Teste</button>

<script>
function myFunction() {
 document.getElementById("demo").innerHTML = "Parágrafo Mudou.";
};
</script>

</body>
</html>
```

    Colocar scripts no final do elemento <body> melhora a velocidade para exibir
    a página, pois a compilação do script retarda a exibição.

### JavaScript Externo

Scripts podem ser colocados em arquivos externos, também: [arquivo JS externo](myScript1.js)

```javascript
function myFunction() {
 document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```

E carregados em arquivos HTML com: [Demo: JS em outro arquivo](where_demo4.html)

```html
<script src="myScript.js"></script>
```

    Scripts externos não podem conter tags <script>.

#### Vantagens de JavaScript Externo

  * Separa HTML do código JS;
  * Torna HTML e JavaScript mais fáceis de serem lidos e simplificar a manutenção deles;
  * Arquivos JavaScript em caches podem acelerar o carregamento da página.

#### Referências externas

Os arquivos de JavaScript podem está em outros sites \(servidores\).

Exemplo: [Demo: JS em link externo](where_demo5.html)

```html
<script src="https://www.w3schools.com/js/myScript.js"></script>
```

## Saída do JS  (https://www.w3schools.com/js/js_output.asp)

### Possibilidade de Exibição das Saídas do JavaScript

JavaScript pode "exibir" os dados de saída de diferentes maneiras:

  * Escrevendo num elemento do HTML, usando innerHTML.
  * Escrevendo na saída do HTML usando document.write\(\).
  * Escrevendo numa caixa de alerta, usando window.alert\(\).
  * Escrevendo na console do navegador, usando console.log\(\).

#### Uso do innerHTML

Para acessar um elemento do HTML, JavaScript pode usar o método document.getElementById\(id\).

Exemplo: [Demo: innerHTML](output_demo1.html)

```html
<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>
```

#### Uso do document.write\(\)

Exemplo: [Demo: document.write\(\)](output_demo2.html)

```html
<script>
document.write(5 + 6);
</script>
```

    Ao usar document.write() depois que um documento HTML foi carregado,
    irá apagar todo o conteúdo do documento HTML [Demo: document.write\(\)](output_demo3.html).
    O método document.write() deve ser usado apenas para testes.

#### Uso do window.alert\(\)

Exemplo: [Demo: window.alert\(\)](output_demo4.html)

```html
<script>
window.alert(5 + 6);
</script>
```

#### Uso do console.log\(\)

Para fins de depuração \(debugging\), você pode usar o método console.log\(\) para exibir dados.

Exemplo: [Demo: uso do console.log](output_demo5.html)

```html
<script>
console.log(5 + 6);
</script>
```

## Instruções de JavaScript (https://www.w3schools.com/js/js_statements.asp)

Exemplo: (stmt_demo1.html)

```javascript
var x, y, z;    // Instrução 1
x = 5;          // Instrução 2
y = 6;          // Instrução 3
z = x + y;      // Instrução 4
```

### Programas JavaScript

Um programa JavaScript é uma lista de instruções de programação.

    Em HTML, programas JavaScript são executados pelo navegador web.

### Instruções JavaScript

Instruções em JavaScript são compostas de:

Valores, Operadores, Expressões, Palavras-Chaves, e Comentários.

A maioria dos programas em JavaScript são compostos por muitos instruções de  JavaScript.

As instruções são executadas, uma-a-uma, na mesma ordem em elas estão escritas.

#### Ponto-e-vírgula ;

Ponto-e-vírgula\(;\) separa as instruções de JavaScript.

Quando separadas por ponto-e-vírgula, várias instruções numa única linha são permitidas:

```javascript
a = 5; b = 6; c = a + b;
```

   Na web, você pode encontrar exemplos sem ponto-e-vírgula.
   Terminar instruções com ponto-e-vírgula não é *obrigatório*,
   mas é altamente recomendado.

#### Espaço em Branco no JavaScript

JavaScript ignora múltiplos espaços entre os elementos da linguagem, óbvio que espaço no meio de um elemento não pode. Você pode adicionar espaços entre os elementos para tornar o texto mais compreensível.

Uma prática recomendada é separar os operadores \( = + - \* / \) com espaços:

```javascript
var x = y + z;
```

#### Comprimento da Linha e Quebra de Linha em JavaScript

Para uma melhor ligibilidade, os programadores, em geral, evitam linhas de código com mais de 80 caractéres.

Se uma instrução de JavaScript não cabe numa linha, o melhor lugar para quebrá-la é após um operador:

```javascript
document.getElementById("demo").innerHTML =
"Alo Maria!";
```

#### Blocos de código em JavaScript

Instruções de JavaScript podem ser agrupadas em blocos de código dentro de chaves {...}.

Exemplo:

```javascript
function myFunction() {
    document.getElementById("demo1").innerHTML = "Alo Maria!";
    document.getElementById("demo2").innerHTML = "Tudo bem?";
}
```

#### Palavras-chaves em JavaScript

As instruções de JavaScript, em geral, começam com uma palavra-chave para identificar a ação de JavaScript a ser realizada.
A tabela abaixo fornece alguns exemplos de aplicações das palavras-chaves em JavaScript.

Palavra-Chave  | Descrição
---------------|----------------------------------------------------------------
break          | Termina a execução de um **switch** ou de uma malha de repetição
continue       | Salta para o início da malha de repetição e começa a executar a partir dali
debugger       | Para a execução do programa em JavaScript e chama \(se disponível\) a função de depuração
do ... while   | Executa um bloco de instruções e  repete o bloco, enquanto uma condição for verdadeira
for            | Marca um bloco de instruções para ser executado enquanto uma condição for verdadeira
function       | Declara uma função
if ... else    | Seleciona um bloco de instruções para ser executado ou outro, dependendo do valor de uma condição
return         | Termina uma função
switch         | Seleciona um bloco de instruções para ser executado, dependendo de diferentes casos
try ... catch  | Implementa a manipulação de erros para um bloco de instruções
var            | Declara uma variável

Por exemplo, a palavra-chave **var** diz para o navegador para criar variáveis:

```javascript
var x, y;
x = 5 + 6;
y = x * 10;
```

    Palavras-chaves em JavaScript são palavras reservadas.
    Palavras reservadas não podem ser usadas como nomes de variáveis.

## Sintaxe do JS (https://www.w3schools.com/js/js_syntax.asp)

### Valores em JavaScript

A sintaxe do JavaScript define dois tipos de valores: Valores fixos e valores variáveis.
Valores fixos são chamados de **literais**. Valores variáveis são chamados de **variáveis**.

#### Literais em JavaScript

**Números** são escritos com ou sem parte decimal \(valor depois da vírgula\):

```javascript
10.50

1001
```

    Observe que no lugar da vírgula para separar a parte decimal da parte inteira, JS usa . \(ponto\).

**Strings** são textos, escritos entre aspas \( " \) ou apóstrofes \( ' \):

```javascript
"José da Silva"

'José da Silva'
```

#### Variáveis de JavaScript

Numa linguagem de programação, variáveis são usadas para armazenar valores dos dados.

JavaScript usa a palavra-chave **var** para declarar variáveis.

Um sinal de igual \( = \) é usado para atribuir valores às variáveis.

### Operadores em JavaScript

JavaScript usa operadores aritméticos \( + - \*  / \) para calcular valores:

```javascript
(5 + 6) * 10
```

JavaScript usa um operador de atribuição \( = \) para atribuir valores a variáveis:

```javascript
var x, y;
x = 5;
y = 6;
```

### Expressões em JavaScript

Uma expressão é uma combinação de valores, variáveis e operadores que calculam num valor.

A computação é chamada de cálculo \(*The computation is called an evaluation*\).

Os valores podem ser de vários tipos, tais como números ou strings.

Por exemplo, "José" + " " + "da" + " " + "Silva", é calculado como "José da Silva":

```javascript
"José" + " " + "da" + " " + "Silva"
```

### Comentários em JavaScript

Texto depois de // até o final da linha ou entre /\* e \*/ é tratado como **comentário**.
Isto é, do ponto de vista do código, ele não existe. Ele serve para tornar o código mais compreensível para alguém que o leia.

### Identificadores em JavaScript

Identificadores são nomes.

Em JavaScript, identificadores são usados para dar nome a variáveis \(e palavras-chaves e funções e rótulos\).

Em JavaScript, o primeiro caracter deve ser uma letra, ou um sublinhado (\_), ou um dolar ($).

### JavaScript é Sensível à Diferença entre Maiúsculas e Minúsculas

Todos os identificadores de JavaScript identifiers diferenciam maiúsculas de minúsculas.

### JavaScript a nomenclatura em Camelo

A notação camelo é usada quando um identificador é composto por mais de uma palavra, neste caso as palavras não podem ser separadas por um espaço \(o que caracterizaria dois identificadores e não um\). Na notação camelo, a primeira letra de cada palavra é escrita em maiúsculo e as outras em minúsculo.

Camelo com minúscula:

Programadores de JavaScript tendem a usar identificadores em notação camelo com a primeira palavra em minúsculo:

primeiroNome, ultimoNome, masterCard, interCidade.

### Conjunto de Caracteres do JavaScript

JavaScript usa o conjunto de caracteres Unicode. Veja (https://www.w3schools.com/charsets/ref_html_utf8.asp) para uma referência mais completa sobre unicode.

## Comentários em JS (https://www.w3schools.com/js/js_comments.asp)

### Comentários Numa Linha

Comentários numa linha começam com //.

### Comentários em Múltiplas Linhas

Comentários em múltiplas linhas começam com /\* e terminam com \*/.

Qualquer texto entre /\* e \*/ será ignorado pelo JavaScript.

    Em geral, usa-se comentários de uma linha.
    Blocos de comentários são geralmente usados para documentação formal.

### Uso de Comentários para Evitar Execução

Comente uma ou mais linhas de código que você não deseja executar na fase de teste do código. Isto evita ter de reescrever se precisar inserí-las de novo. Esta é uma maneira de testar diferentes possibilidades de códigos sem ter de reescrever muita coisa.

## Variáveis de JavaScript

Variáveis de JavaScript são reservatórios para armazenar valores dos dados.

### Parece Muito com Álgebra

No exemplo abaixo, preco1, preco2 e total são variáveis:

```javascript
var preco1 = 5;
var preco2 = 6;
var total = preco1 + preco2;
```

### Identificadores de JavaScript

Todas as **variáveis** em JavaScript devem ser identificadas por **nomes únicos**. Estes nomes únicos são chamados de **identificadores**.

As regras gerais para a escolha de nomes para variáveis \(identificadores únicos\) são:

  * Os nomes devem ser  compostos por letras, dígitos, sublinhados e dolars;
  * Os nomes devem começar com uma letra, um $ ou um \_;
  * Os nomes diferenciam maiúsculas de minúsculas \(a e A são variáveis diferentes); e
  * Palavras reservadas não podem ser usadas como nomes de variáveis.

### O Operador de Atribuição

Em JavaScript, o sinal de igual \(=\) é um operador de *atribuição*, não um operador de igualdade.

    O operador de comparação "igual a" é escrito \(==\), ou \(===\) em JavaScript.

### Tipos de Dados em JavaScript

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
