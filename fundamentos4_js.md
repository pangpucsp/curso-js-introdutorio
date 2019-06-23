# Fundamentos IV de JavaScript

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

### Uma Função Aleatória Adequada

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
[Demo: if e else](ifelse_demo1.html)

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

Se nenhum *case* casar, o programa continua no rótulo *default*.

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

Malhas (de repetição, ou simplesmente, loops) podem executar um bloco de código
diversas vezes.

### Loops em JavaScript

Loops são muito úteis, se quiser rodar o mesmo código diversas vezes,
cada vez com um valor diferente em algumas variáveis.

Frequentemente, é o que ocorre no processamento de *arrays*:

No lugar de escrever:

```javascript
text += cars[0] + "<br>";
text += cars[1] + "<br>";
text += cars[2] + "<br>";
text += cars[3] + "<br>";
text += cars[4] + "<br>";
text += cars[5] + "<br>";
```

Você pode escrever:

```javascript
var i;
for (i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
}
```

### Diferentes Tipos de Loops

JavaScript dá suporte a diferentes tipos de *loops*:

  * *for* - repete um bloco de código um certo número de vezes;
  * *for/in* - repete para as propriedades de um objetos, ou para todos elementos de um *container*;
  * *while* - repete um bloco de código enquanto uma condição for verdadeira; e
  * *do/while* - também repete um bloco de código enquanto uma condição for verdadeira, a diferença é que o bloco executa pelo menos uma vez.

#### O Loop For

O loop for tem a seguinte sintaxe:

```javascript
for (instrução 1; instrução 2; instrução 3) {
  // bloco de código a ser executado, enquanto a condição for verdadeira
}
```

**instrução 1** é executada uma vez antes da execução do bloco de código.

**instrução 2** define a condição para a execução do bloco de código.

**instrução 3** é executada, toda vez, depois que o bloco de código for executado.

Exemplo: [Demo: for](for_demo1.html)

```javascript
for (i = 0; i < 5; i++) {
  texto += "O número é " + i + "<br>";
}
```

Do exemplo acima, pode-se ler:

Instrução 1 ajusta uma variável de controle do loop antes desse começar
\(var i = 0\).

Instrução 2 define a condição para o bloco de código executar \(i deve ser
menor do que 5\).

Instrução 3 aumenta o valor da variável de controle de 1 (i++) cada vez que
o bloco de código for executado \(lembre-se de que esse aumento só ocorre
depois da execução do bloco\).

##### Instrução 1

Em geral, usa-se a instrução 1 para inicializar uma variável usada no loop \(i = 0\).

Isto não acontece sempre, o JavaScript não se importa. A instrução 1 é opcional.

Você pode inicializar mais de uma variável na instrução 1 \(separadas por vírgula\):

Exemplo

```javascript
for (i = 0, len = carros.length, texto = ""; i < len; i++) {
  texto += carros[i] + "<br>";
}
```

E você pode omitir a instrução 1 \(quando, por exemplo, a inicialização é feita
fora do loop\):

Exemplo

```javascript
var i = 2;
var len = cars.length;
var texto = "";
for (; i < len; i++) {
  texto += carros[i] + "<br>";
}
```

##### Instrução 2

Often statement 2 is used to evaluate the condition of the initial variable.
Em geral, a instrução 2 é usada para calcular a condição \(estado\) de uma
variável de inicialização.


This is not always the case, JavaScript doesn't care. Statement 2 is also optional.

Isto nem sempre acontece, o JavaScript não se importa. A instrução 2 é opcional.

    Se omitir a instrução 2, você terá de realizar um *break* dentro do loop.
    Senão, o loop nunca vai terminar (dizemos que o programa entrou em loop).
    Isto pode quebrar seu navegador \(se não travar seu SO\).

##### Instrução 3

Em geral, a instrução 3 incrementa \(aumenta\) o valor de uma variável de
inicialização.

Isto nem sempre acontece, o JavaScript não se importa. A instrução 3, também,
é opcional.

A instrução 3 pode fazer qualquer coisa do tipo incremento negativo \(i--\),
incremento positivo \(i++\), i += 5, ou qualquer outra coisa.

    Um erro comum de programadores iniciantes é esquecer de mudar a variável
    de controle para terminar o loop.

A instrução 3 também pode ser omitida \(como quando você incrementa a variável
  de controle dentro do loop\):

Exemplo

```javascript
var i = 0;
var len = cars.length;
for (; i < len; ) {
  texto += carros[i] + "<br>";
  i++;
}
```

#### O Loop For/In

Em JavaScript a instruçao *for/in* faz o loop nas  propriedades de um objeto:

Exemplo

```javascript
var pessoa = {pnome:"João", sname:"Silva", idade:25};

var texto = "";
var x;
for (x in person) {
  texto += pessoa[x];
}
```

## Loop while em JavaScript (https://www.w3schools.com/js/js_loop_while.asp)

Loops podem executar um bloco de código enquanto uma condição for verdadeira.

### O Loop while

O loop while repete um bloco de código enquanto um dada condição for verdadeira.

Sintaxe

```javascript
while (condição) {
  // bloco de código a ser executada
}
```

No próximo exemplo, o código no bloco do loop irá executar repetidamente
enquanto a variável \(i\) for menor do que 10:

Exemplo

```javascript
while (i < 10) {
  texto += "O número é " + i;
  i++;
}
```

    Se você esquecer de incrementar a variável usada na condição,
    o loop nunca terminará. Isto quebrará o navegador.

### O Loop do/while

O loop do/while é uma variante do loop while. Este loop executará o bloco de
código uma vez, antes de verificar se a condição é verdadeira,
então repetirá o loop enquanto a condição for verdadeira.

Sintaxe

```javascript
do {
  // bloco de código a ser executado
}
while (condição);
```

O exemplo abaixo usa um loop do/while. O loop sempre executará uma vez pelo
menos, mesmo se inicialmente a condição for falsa, porque o bloco de código é
executado antes a condição for testada:

Exemplo

```javascript
do {
  texto += "O número é " + i;
  i++;
}
while (i < 10);
```

    Não esqueça de incrementar a variável usada na condição,
    senão o loop nunca terminará!

### Comparação entre o for e while

Se você leu a seção anterior, a respeito do loop *for*, você perceberá que um
loop *while* é semelhante ao loop *for*, com as instruções 1 e 3 omitidas.

O loop neste exemplo usa um loop *for* para coletar os nomes de carros do
*array* carros:

Exemplo

```javascript
var carros = ["BMW", "Volvo", "Saab", "Ford", "VW", "Toyota"];
var i = 0;
var texto = "";

for (;carros[i];) {
  texto += carros[i] + "<br>";
  i++;
}
```

O loop no próximo exemplo usa um loop *while* para coletar os nomes de carros do
*array* carros:

Exemplo

```javascript
var carros = ["BMW", "Volvo", "Saab", "Ford", "VW", "Toyota"];
var i = 0;
var texto = "";

while (carros[i]) {
  texto += carros[i] + "<br>";
  i++;
}
```

## Break e Continue em JavaScript (https://www.w3schools.com/js/js_break.asp)

A instrução **break**, já vista no *switch*, "salta para fora" de um loop.

A instrução **continue** "salta para a" próxima iteração do loop.

### A Instrução Break

Você já viu a instrução numa outra seção desta página. Ele foi usado para
"saltar para fora" de uma instrução switch\(\).

A instrução *break* pode também ser usada para saltar fora de um loop.  

A instrução *break* quebra o loop e continua a execução no código que vem após
o loop \(se houver\):

Exemplo

```javascript
for (i = 0; i < 10; i++) {
  if (i === 3) { break; }
  texto += "O número é " + i + "<br>";
}
```

### A Instrução Continue

A instrução *continue* quebra uma iteração \(no loop\), se condição
especificada ocorre \(for verdadeira\), e continua com a próxima iteração do loop.

Este exemplo pula os múktiplos de 3:

Exemplo

```javascript
for (i = 0; i < 10; i++) {
  if (i % 3 == 0) { continue; }
  texto += "O número é " + i + "<br>";
}
```

### Rótulos em JavaScript

Para por rótulos em instruções de JavaScript, você deve preceder as instruções
com o nome do rótulo e um dois pontos\(:\):

```javascript
rótulo:
instruções
```

As instruções *break* e *continue* são as únicas instruções em JavaScript que
podem *saltar para fora* de um bloco de códigos.

Syntax:

```javascript
break rótulo;

continue rótulo;
```

A instrução **continue** \(com ou sem uma referência a um rótulo\) só pode ser
usada para *saltar* uma iteração de loop.

A instrução **break**, sem uma referência a um rótulo, só pode ser usada para
*saltar fora* de um loop ou de um *switch*.

Com a referência a um rótulo, a instrução *break* pode ser usada para saltar
fora de qualquer bloco de código:

Exemplo

```javascript
var carros = ["BMW", "Volvo", "Saab", "Ford", "VW", "Toyota"];
lista: {
  texto += carros[0] + "<br>";
  texto += carros[1] + "<br>";
  break lista;
  texto += carros[2] + "<br>";
  texto += carros[3] + "<br>";
}
```

    Um bloco de código é um bloco de código entre chaves, \{ e \}.

[Próxima unidade](fundamentos5_js.md)
