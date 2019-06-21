returna# Fundamentos IV de JavaScript

Esta é a continuação de [Fundamentos III de JS](fundamento3_js.md).

## Objeto Math de JavaScript (https://www.w3schools.com/js/js_math.asp)

O objeto Math de JavaScript permite que você realize operações matemáticas com
números.

    Em outras linguagens orientadas a objetos, Math é chamada de classe.
    Como JavaScript é uma linguagem de prototipagem, é normal chamar Math
    de objeto.

```javascript
Math.PI;            // retorna 3.141592653589793
```

### Math.round\(\)

Math.round\(x\) retorna o valor de x arredondado para o inteiro mais próximo:

Exemplo

```javascript
Math.round(4.7);    // retorna 5
Math.round(4.4);    // retorna 4
```

### Math.pow\(\)

Math.pow\(x, y\) retorna o valor de x elevado à potência y:

Exemplo

```javascript
Math.pow(8, 2);      // retorna 64
```

### Math.sqrt\(\)

Math.sqrt\(x\) retorna a raíz quadrada de x:

Exemplo

```javascript
Math.sqrt(64);      // retorna 8
```

### Math.abs\(\)

Math.abs\(x\) retorna o valor absoluto (módulo) de x:

Exemplo

```javascript
Math.abs(-4.7);     // retorna 4.7
```

### Math.ceil\(\)

Math.ceil\(x\) retorna o valor de x arredondado para cima:

Exemplo

```javascript
Math.ceil(4.4);     // retorna 5
```

### Math.floor\(\)

Math.floor\(x\) retorna o valor de x arredondado para baixo:

Exemplo

```javascript
Math.floor(4.7);    // retorna 4
```

### Math.sin\(\)

Math.sin\(x\) retorna o seno \(um valor entre -1 e 1\) do ângulo x \(dado em radianos\).

    Se você quiser usar graus no lugar de radianos, você terá de converter
    graus em radianos:

    Ângulo em radianos = Ângulo em graus x PI / 180.

Exemplo

```javascript
Math.sin(90 * Math.PI / 180);     // retorna 1 (o seno de 90 graus)
```

### Math.cos\(\)

Math.cos\(x\) retorna o cosseno \(um valor entre -1 e 1\) do ângulo x \(dado em radianos\).

    Se você quiser usar graus no lugar de radianos, você terá de converter
    graus em radianos:

    Ângulo em radianos = Ângulo em graus x PI / 180.

Exemplo

```javascript
Math.cos(0 * Math.PI / 180);     // retorna 1 (o cosseno de 0 grau)
```


### Math.min\(\) e Math.max\(\)

Math.min\(\) e Math.max\(\) podem ser usados para achar o menor e o maior valor
de uma lista de argumentos:

Exemplo

```javascript
Math.min(0, 150, 30, 20, -8, -200);  // retorna -200
Math.max(0, 150, 30, 20, -8, -200);  // retorna 150
```

### Math.random\(\)

Math.random\(\) retorna um número aleatório entre 0 \(inclusive\) e 1
\(exclusive\), em notação matemática \[0,1\):

Exemplo

```javascript
Math.random();     // retorna um número aleatório
```

### Propriedades de Math \(Constantes\)

JavaScript fornece 8 constantes matemáticas que podem ser acessadas com o objeto
Math:

Exemplo

```javascript
Math.E        // retorna o número de Euler
Math.PI       // retorna o valor de PI
Math.SQRT2    // retorna a raíz quadarada de 2
Math.SQRT1_2  // retorna a raíz quadarada de 1/2
Math.LN2      // retorna o logaritmo natural de 2
Math.LN10     // retorna o logaritmo natural de 10
Math.LOG2E    // retorna o logaritno de E na base 2
Math.LOG10E   // retorna o logaritmo de E na base 10
```

### Construtor de Math

Diferente de outros objetos globais, o objeto Math não tem construtor.
Seus métodos e propriedades (constantes) são todos estáticos.

Todos os métodos e propriedades (constantes) podem ser usados sem a criação de
um objeto Math primeiro.

### Métodos do Objeto Math

| Method                 | Descrição |
|-----------------------|---------------------------------------------------|
| abs\(x\)               | Retorna o valor absoluto de x |
| acos\(x\)              | Retorna o arcocosseno de x, em radianos |
| asin\(x\)              | Retorna o arcoseno de x, em radianos |
| atan\(x\)              | Retorna o arcotangente de x como um número entre -PI/2 e PI/2 radianos |
| atan2\(y, x\)          | Retorna o arcotangente do quociente de seus argumentos |
| ceil\(x\)              | Retorna o valor de x arredondado para cima |
| cos\(x\)               | Retorna o cosseno de x (x em radianos) |
| exp\(x\)               | Retorna o valor de E elevado a x |
| floor\(x\)             | Retorna o valor de x arredondado para baixo |
| log\(x\)               | Retorna o logaritmo natural (base E) de x |
| max\(x, y, z, ..., n\) | Retorna o número de maior valor entre os argumentos |
| min\(x, y, z, ..., n\) | Retorna o menor valor entre os argumentos |
| pow\(x, y\)            | Retorna o valor de x elevado a y |
| random\(\)             | Retorna um número aleatório entre 0 e 1 |
| round\(x\)             | Retorna o valor de x arredondado para o inteiro mais próximo |
| sin\(x\)               | Retorna o seno de x (x em radianos) |
| sqrt\(x\)              | Retorna a raíz quadrada de x |
| tan\(x\)               | Retorna o valor da tangente do ângulo x (em radianos) |

## Random em JavaScript (https://www.w3schools.com/js/js_random.asp)

### Math.random\(\)

Math.random\(\) retorna um número aleatório entre 0 \(inclusive\)  e 1 \(exclusive\):

Exemplo

```javascript
Math.random();              // retorna um número aleatório
```

    Math.random() sempre retorna um número menor do que 1.
    Para retornar um número em (0,1], tente 1 Math.ramdon().

### Inteiros Aleatório em JavaScript

Math.random\(\) com Math.floor\(\) pode ser usado para retornar inteiros aleatórios.

Exemplo

```javascript
Math.floor(Math.random() * 10);     // retorna um inteiro aleatório de 0 a 9

Math.floor(Math.random() * 11);      // retorna um inteiro aleatório de 0 a 10

Math.floor(Math.random() * 10) + 1;  // retorna um inteiro aleatório de 1 a 10

Math.floor(Math.random() * 100) + 1; // retorna um inteiro aleatório de 1 a 100
```

### Uma Função Aleatória Própria

Como você pode ver dos exemplos acima, pode ser um boa idéia criar sua própria
função aleatória para gerar números aleatórios para todos os fins.

A função JavaScript abaixo sempre retorna um número aleatório entre min
(inclusive) e max (exclusive):

Exemplo

```javascript
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min) ) + min;
}
```

A função JavaScript abaixo sempre retorna um número aleatório entre min e max
\(ambos inclusive\):

Exemplo

```javascript
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

## Booleanos em JavaScript (https://www.w3schools.com/js/js_booleans.asp)

Um booleano em JavaScript representa um de dois valores: **true** ou **false**.

### Valores Booleanos

Frequentemente, em programação, você precisa de um tipo de dado que possa ter
apenas dois valores, como

  * SIM / NÃO
  * LIGA / DESLIGA
  * VERDADEIRO / FALSO

Para tanto, JavaScript tem um tipo de dado Boolean (Booleano, ou lógico). Ele só
pode assumir os valores **true** (verdade) ou **false** (falso).

### A Função Boolean\(\)

Você pode usar a função Boolean\(\) para descobrir se uma expressão
\(ou uma variável\) é verdadeira:

Exemplo

```javascript
Boolean(10 > 9)        // retorna true
```

Ou mais simples:

Exemplo

```javascript
(10 > 9)              // também retorna true
10 > 9                // também retorna true
```

### Comparações e Condições

A seção Comparações em JS dá uma sobrevoada nos operadores de comparação.

A seção Condições em JS dá uma obrevoada nas instruções de condição.

Eis alguns exemplos:

| Operador | Descrição      | Exemplo |
|----------|----------------|-----------------|
| ==       | igual a        | if (dia == "Monday") |
| \>       | maior do que   | if (salario > 9000) |
| <        | menor do que   | if (idade < 18) |

    O valor Booleano de uma expressão é a base para todas as comparações em
    JavaScript.

### Tudo que Tem um "Valor" é True

Exemplos

```javascript
100

3.14

-15

"Hello"

"false"

7 + 1 + 3.14
```

### Qualquer Coisa sem um "Valor" é False

O valor Booleano de 0 \(zero\) é false:

```javascript
var x = 0;
Boolean(x);       // returna false

var x = -0;
Boolean(x);       // returna false

var x = "";
Boolean(x);       // returna false

var x;
Boolean(x);       // returna false

var x = null;
Boolean(x);       // returna false

var x = false;
Boolean(x);       // returna false

// O valor Booleano de NaN (Not-a-Number, não-é-um-número) é false:
var x = 10 / "H";
Boolean(x);       // returna false
```

### Booleanos Podem Ser Objects

Normalmente, booleanos em JavaScript são valores primitivos criados de literais:

```javascript
var x = false;
```

Mas booleanos podem também ser definedos como objetos com a palavra-chave new:

```javascript
var y = new Boolean(false);

```

Exemplo
```javascript
var x = false;
var y = new Boolean(false);

// typeof x returna boolean
// typeof y returna object
```

    Não crie objetos Boolean. Isto reduz a velocidade do processamento.

A palavra-chave new complica o código. Isto pode produzir alguns resultados
inesperados:

Ao usar o operador ==, booleanos iguais são iguais:

Exemplo
```javascript
var x = false;             
var y = new Boolean(false);

// (x == y) é true porque x e y têm valores iguais
```

Ao uso o operador ===, booleanos iguais não são iguais, porque  operador ===
espera igualdade tanot de tipo, quanto de valor.

Exemplo
```javascript
var x = false;             
var y = new Boolean(false);

// (x === y) é false porque x e y têm tipos diferentes
```

Ou pior ainda. Objetos não podem ser comparados:

Exemplo
```javascript
var x = new Boolean(false);             
var y = new Boolean(false);

// (x == y) é false porque objetos não podem ser comparados
```

    Observe a diferença entre (x==y) e (x===y).
    Comparar dois objetos JavaScript sempre retorna false.

## Operadores de Comparação e Lógicos em JavaScript (https://www.w3schools.com/js/js_comparisons.asp)

Operadores de comparação e lógicos são usados para testar por **true** ou **false**.

### Operadores de Comparação

Operadores de comparação são usados em instruções lógicas para determinar a
igualdade ou a diferença entre variáveis e valores.

Dado que x = 5 (x recebe o valor 5), a tabela abaixo explica os operadores de
comparação:

| Operador   | Descrição                         | Comparação | Retorna |
|------------|-----------------------------------|------------|-----------|
| ==         | igual a                           | x == 8    | false |
|            |                                   | x == 5    | true |
|            |                                   | x == "5"  | true |
| ===        | mesmo valor e mesmo tipo          | x === 5   | true |
|            |                                   | x === "5" | false |
| !=         | diferente de                      | x != 8    | true |
| !==        | valor ou tipo diferente           | x !== 5   | false |
|            |                                   | x !== "5" | true |
|            |                                   | x !== 8   | true |
| \>         | maior do que                      | x > 8     | false |
| <          | menor do que                      | x < 8     | true |
| \>=        | maior ou igual a                  | x >= 8    | false |
| <=         | menor ou igual a                  | x <= 8    | true |

### Como Usar

Operadores de comparação podem ser usados em instruções condicionais para
comparar valores e realizar uma ação de acordo com o resultado:

```javascript
if (idade < 18) texto = "Muito jovem";
```

### Operadores Lógicos

Operadores lógicos são usados para determinar a lógica entre variáveis e valores.

Dado que x = 6 e y = 3, a tabela abaixo explica os operadores lógicos:

| Operador | Descrição | Exemplo |
|----------|-----------|-------------------|
| &&       | e         | \(x < 10 && y > 1\) é true |
| \|\|     | ou        | \(x == 5 \|\| y == 5\) é false |
| !        | negação   | !\(x == y\) é true |

### Operador Ternário Condicional

JavaScript também possui um operador condicional cujo cálculo resulta num
valor determinado por alguma condição.

Sintaxe

```javascript
nomedevariavel = (condição) ? valor1:valor2
```

Exemplo: (comp_demo1.html)

```javascript
var votante = (idade < 18) ? "Jovem demais":"Velho o suficiente";
```

Se a variável *idade* tiver valor menor do que 18, o valor da variável
*votante* será *"Jovem demais"*, senão, será *"Velho o suficiente"*.

Observe que o uso dos parenteses, \(\), não é obrigatório no caso, já que a
precedência do operador condicional é menor do que as operações condicionais e
lógicas. Mas, em respeito ao C, C++ e Java, normalmente a condição fica entre
\(\).

### Compração de Tipos Diferentes

A comparação de dados de tipos diferentes pode dar resultados inesperados.

Ao comparar uma string com um número, JavaScript converte a string num número
para realizar a comparação. Uma string vazia \(""\) converte em 0. Uma string
não numérica converte para NaN que sempre tem o valor Booleano false.

| Caso        | Valor |
|-------------|-------|
| 2 < 12      | true |
| 2 < "John"  | false |
| 2 > "John"  | false |
| 2 == "John" | false |
| "2" < "12"  | false |
| "2" > "12"  | true |
| "2" == "12" | false |

Ao comparar dois string, "2" é maior do que "12", porque *alfabeticamente* 1
é menor do que 2.

Para assegurar um resultado apropriado, variáveis devem ser convertidas num
tipo adequado antes da comparação:

```javascript
idade = Number(idade);
if (isNaN(idade)) {
  votante = "Entrada não é um número";
} else {
  votante = (idade < 18) ? "Jovem demais" : "Velho o suficiente";
}
```

## if else e else if em JavaScript [(se senão em JS)](https://www.w3schools.com/js/js_if_else.asp)

Instruções condicionais podem ser usadas para realizar diferentes ações
dependendo de diferentes condições.

### Instruções Condicionais

Frequentemente, quando você escreve código, você quer realizar diferentes ações
para diferentes decisões.

Você pode usar instruções condicionais no seu código para isto.

No JavaScript temos as seguintes instruções condicionais:

  * Use *if* para especificar um bloco de código para ser executado, se a
  condição especificada for verdadeira, *true*;
  * Use *else* para especificar um bloco de código a ser executado, se a
  mesma condição for false, *false*;
  * Use *else if* para especificar uma nova condição de teste, se a primeira
  condição for falsa; e
  * Use *switch* para especificar várias alternativas de blocos de código a
  serem executadas.

### A Instrução if

Use a instrução **if** para especificar um bloco de código JavaScript a ser
executado se a condição for verdadeira.

Sintaxe

```javascript
if (condição) {
  //  bloco de código a executar se a condição for verdadeira
}
```

Exemplo: Faça uma saudação de "Bom dia" se a hora for menor do que 18:00:

```javascript
if (hora < 18) {
  saudacao = "Bom dia";
}
```

O resultado da saudação será:

  Bom dia

### A Instrução else

Use a instrução **else** para especificar um bloco de código a ser executado
se a condição for falsa.

Sintaxe

```javascript
if (condição) {
  //  bloco de código a ser executado se a condição for verdadeira
} else {
  //  bloco de código a ser executado se a condição for falsa
}
```

Exemplo: Se a hora for menor do que 18, saudacao é "Bom dia", senão "Boa noite":
[Demo: if e else] (ifelse_demo1.html)

```javascript
if (hora < 18) {
  saudacao = "Bom dia";
} else {
  saudacao = "Boa noite";
}
```

O resultado de saudacao será:

  Bom dia

### A Instrução else if

Use a instrução **else if** para especificar uma nova condição se a primeira
for falsa.

Sintaxe

```javascript
if (condição1) {
  //  bloco de código a ser executado se a condição1 for verdadeira
} else if (condição2) {
  //  bloco de código a ser executado se a condição1 for falsa
  // e a condição2 for verdadeira
} else {
  //  bloco de código a ser executado se a condição1 for falsa e
  // a condição2 for falsa
}
```

Exemplo: Se horario for menor do que 10:00, crie uma saudacao "Boa manhã",
se não, mas horário for menor do que 20:00, crie a saudacao "Bom dia",
senão um "Boa noite":

```javascript
if (horario < 10) {
  saudacao = "Boa manhã";
} else if (horario < 20) {
  saudacao = "Bom dia";
} else {
  saudacao = "Boa noite";
}
```

O resultado da saudacao será:

  Bom dia

## Instrução switch no JavaScript (https://www.w3schools.com/js/js_switch.asp)

A instrução **switch** é usada para realizar diferentes ações baseada em
diferentes condições.

### A Instrução switch JavaScript

Use a instrução switch para selecionar um de muitos blocos de código a serem
executados.

Syntax

```javascript
switch(expressão) {
  case x:
    // bloco de código a ser executado caso a expressão seja x
    break;
  case y:
    // bloco de código a ser executado caso a expressão seja y
    break;
  default:
    // bloco de código a ser executado caso a expressão tenha um valor
    // diferente de dos cases
}
```

Eis como isto funciona:

A expressão do switch é calculada uma vez.
O valor da expressão é comparado com os valores de cada *case*.
Se há um casamento (valores iguais), o bloco associado é executado.

Exemplo: O método getDay\(\) retorna o dia da semana como um número de 0 a 6.

\(Domingo=0, Segunda=1, Terça=2 ..\)

Este exemplo usa o número do dia da semana para calcular o nome do dia da semana:

```javascript
switch (new Date().getDay()) {
  case 0:
    day = "Domingo";
    break;
  case 1:
    day = "Segunda-feira";
    break;
  case 2:
     day = "Terça-feira";
    break;
  case 3:
    day = "Quarta-feira";
    break;
  case 4:
    day = "Quinta-feira";
    break;
  case 5:
    day = "Sexta-feira";
    break;
  case 6:
    day = "Sábado";
}
```

O resultado do dia poderia ser:

  Segunda-feira

### A Palavra-Chave break

Quando o JavaScript chega numa palavra-chave **break**, ele sai do bloco do
*switch*.

Isto para a execução do restante do código dentro do switch.

Quando um casamento é encontrado e o trabalho estiver feito, é hora de um
*break*. Não há a necessidade de continuar testando e executando o restante do código.

    Um break pode economizar um monte de tempo de execução, porque
    ele ignora a execução de todo o restante do código do bloco do switch.

Não é necessário usar um *break* no último *case* do bloco do *switch*.
O bloco vai terminar de qualquer maneira.

### A Palavra-Chave default

A palavra-chave **default** especifica o código a rodar se não houver nenhum
casamento com um *case*:

Exemplo: Usemos de novo o método getDay\(\).

Se hoje não for nem Sábado\(6\), nem Domingo\(0\), escreva a mensagem a *default*:

```javascript
switch (new Date().getDay()) {
  case 6:
    texto = "Hoje é Sábado";
    break;
  case 0:
    texto = "Hoje é Domingo";
    break;
  default:
    texto = "Esperando o Fim-de-Semana";
}
```

O resultado de texto pode ser:

  Esperando o Fim-de-Semana

O caso *default* não precisa ser o último *case* do bloco do *switch*:

Exemplo

```javascript
switch (new Date().getDay()) {
  default:
    texto = "Esperando o Fim-de-Semana";
    break;
  case 6:
    texto = "Hoje é Sábado";
    break;
  case 0:
    texto = "Hoje é Domingo";
}
```

    Se default não for o último case no bloco do switch, lembre-se de terminar
    o caso default com um break.

### Blocos de Código em Comum

Algumas vezes, você quer que diferentes *case* do switch usem um mesmo código.

Neste exemplo, case 4 e 5 compartilham o mesmo bloco de códigos e
0 e 6 compatilham um outro bloco:

Exemplo

```javascript
switch (new Date().getDay()) {
  case 4:
  case 5:
    texto = "Quase Fim-De-Semana";
    break;
  case 0:
  case 6:
    texto = "É Fim-De-Semana";
    break;
  default:
    texto = "Esperando o Fim-De-Semana";
}
```

### Detalhes do Switch

Se múltiplos *case*  casam com um valor de *case*, o primeiro *case* é
selecionado.

Se nenhum case casar, o programa continua no rótulo *default*.

Se não houver rótulo *default*, o programa continua na intrução após o *switch*.

### Comparação Estrita

Cases do *switch* usam comparação estrita \(===\).

Os valores devem ser de um mesmo tipo para haver o casamento.

Uma comparação estrita pode apenas ser verdadeira se os operandos são do mesmo
tipo.

Neste exemplo, não haverá nenhum casamento para o x:

Exemplo

```javascript
var x = "0";
switch (x) {
  case 0:
    texto = "Desliga";
    break;
  case 1:
    texto = "Liga";
    break;
  default:
    texto = "Nenhum valor encontrado";
}
```

## Malha \(*loop*\) for em JavaScript (https://www.w3schools.com/js/js_loop_for.asp)

Loops can execute a block of code a number of times.

### JavaScript Loops

Loops are handy, if you want to run the same code over and over again, each time with a different value.

Often this is the case when working with arrays:

Instead of writing:

```javascript
text += cars[0] + "<br>";
text += cars[1] + "<br>";
text += cars[2] + "<br>";
text += cars[3] + "<br>";
text += cars[4] + "<br>";
text += cars[5] + "<br>";
```

You can write:

```javascript
var i;
for (i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
}
```

### Different Kinds of Loops

JavaScript supports different kinds of loops:

  * for - loops through a block of code a number of times
  * for/in - loops through the properties of an object
  * while - loops through a block of code while a specified condition is true
  * do/while - also loops through a block of code while a specified condition is true

#### The For Loop

The for loop has the following syntax:

```javascript
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

**Statement 1** is executed \(one time\) before the execution of the code block.

**Statement 2** defines the condition for executing the code block.

**Statement 3** is executed \(every time\) after the code block has been executed.

Exemplo: (for_demo1.html)

```javascript
for (i = 0; i < 5; i++) {
  text += "The number is " + i + "<br>";
}
```

From the Exemplo above, you can read:

Statement 1 sets a variable before the loop starts (var i = 0).

Statement 2 defines the condition for the loop to run (i must be less than 5).

Statement 3 increases a value (i++) each time the code block in the loop has been executed.

##### Statement 1

Normally you will use statement 1 to initialize the variable used in the loop \(i = 0\).

This is not always the case, JavaScript doesn't care. Statement 1 is optional.

You can initiate many values in statement 1 \(separated by comma\):

Exemplo

```javascript
for (i = 0, len = cars.length, text = ""; i < len; i++) {
  text += cars[i] + "<br>";
}
```

And you can omit statement 1 (like when your values are set before the loop starts):

Exemplo

```javascript
var i = 2;
var len = cars.length;
var text = "";
for (; i < len; i++) {
  text += cars[i] + "<br>";
}
```

##### Statement 2

Often statement 2 is used to evaluate the condition of the initial variable.

This is not always the case, JavaScript doesn't care. Statement 2 is also optional.

If statement 2 returna true, the loop will start over again, if it returna false, the loop will end.

    If you omit statement 2, you must provide a break inside the loop. Otherwise the loop will never end. This will crash your browser.

##### Statement 3

Often statement 3 increments the value of the initial variable.

This is not always the case, JavaScript doesn't care, and statement 3 is optional.

Statement 3 can do anything like negative increment (i--), positive increment (i = i + 15), or anything else.

Statement 3 can also be omitted (like when you increment your values inside the loop):

Exemplo

```javascript
var i = 0;
var len = cars.length;
for (; i < len; ) {
  text += cars[i] + "<br>";
  i++;
}
```

#### The For/In Loop

The JavaScript for/in statement loops through the properties of an object:

Exemplo

```javascript
var person = {fname:"John", lname:"Doe", age:25};

var text = "";
var x;
for (x in person) {
  text += person[x];
}
```

## JavaScript While Loop (https://www.w3schools.com/js/js_loop_while.asp)

Loops can execute a block of code as long as a specified condition is true.

### The While Loop

The while loop loops through a block of code as long as a specified condition is true.

Syntax

```javascript
while (condition) {
  // code block to be executed
}
```

In the following Exemplo, the code in the loop will run, over and over again, as long as a variable \(i\) is less than 10:

Exemplo

```javascript
while (i < 10) {
  text += "The number is " + i;
  i++;
}
```

    If you forget to increase the variable used in the condition, the loop will never end. This will crash your browser.

### The Do/While Loop

The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

Syntax

```javascript
do {
  // code block to be executed
}
while (condition);
```

The Exemplo below uses a do/while loop. The loop will always be executed at least once, even if the condition is false, because the code block is executed before the condition is tested:

Exemplo

```javascript
do {
  text += "The number is " + i;
  i++;
}
while (i < 10);
```

    Do not forget to increase the variable used in the condition, otherwise the loop will never end!

### Comparing For and While

If you have read the previous chapter, about the for loop, you will discover that a while loop is much the same as a for loop, with statement 1 and statement 3 omitted.

The loop in this Exemplo uses a for loop to collect the car names from the cars array:

Exemplo

```javascript
var cars = ["BMW", "Volvo", "Saab", "Ford"];
var i = 0;
var text = "";

for (;cars[i];) {
  text += cars[i] + "<br>";
  i++;
}
```

The loop in next Exemplo uses a while loop to collect the car names from the cars array:

Exemplo

```javascript
var cars = ["BMW", "Volvo", "Saab", "Ford"];
var i = 0;
var text = "";

while (cars[i]) {
  text += cars[i] + "<br>";
  i++;
}
```

## JavaScript Break and Continue (https://www.w3schools.com/js/js_break.asp)

The **break** statement "jumps out" of a loop.

The **continue** statement "jumps over" one iteration in the loop.

### The Break Statement

You have already seen the break statement used in an earlier chapter of this tutorial. It was used to "jump out" of a switch\(\) statement.

The break statement can also be used to jump out of a loop.  

The break statement breaks the loop and continues executing the code after the loop \(if any\):

Exemplo

```javascript
for (i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}
```

### The Continue Statement

The continue statement breaks one iteration \(in the loop\), if a specified condition occurs, and continues with the next iteration in the loop.

This Exemplo skips the value of 3:

Exemplo

```javascript
for (i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}
```

### JavaScript Labels

To label JavaScript statements you precede the statements with a label name and a colon:

```javascript
label:
statements
```

The break and the continue statements are the only JavaScript statements that can "jump out of" a code block.

Syntax:

```javascript
break labelname;

continue labelname;
```

The **continue** statement \(with or without a label reference\) can only be used to skip one loop iteration.

The **break** statement, without a label reference, can only be used to jump out of a loop or a switch.

With a label reference, the break statement can be used to jump out of any code block:

Exemplo

```javascript
var cars = ["BMW", "Volvo", "Saab", "Ford"];
list: {
  text += cars[0] + "<br>";
  text += cars[1] + "<br>";
  break list;
  text += cars[2] + "<br>";
  text += cars[3] + "<br>";
}
```

    A code block is a block of code between \{ and \}.
