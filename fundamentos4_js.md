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

    Observe a diferença entre \(x==y\) e \(x===y\).
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
| !=         | diferente                         | x != 8    | true |
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
| \|\|     | ou        | \(x == 5 || y == 5\) é false |
| !        | negação   | !\(x == y\) é true |

### Conditional \(Ternary\) Operator

JavaScript also contains a conditional operator that assigns a value to a variable based on some condition.

Syntax

```javascript
variablename = (condition) ? value1:value2
```

Exemplo: (comp_demo1.html)

```javascript
var voteable = (age < 18) ? "Too young":"Old enough";
```

If the variable age is a value below 18, the value of the variable voteable will be "Too young", otherwise the value of voteable will be "Old enough".
Observe use of \(\) is not obrigatory in this case since conditional operator precedence is less than comparison operation but it is usual that condition be between \(\).

### Comparing Different Types

Comparing data of different types may give unexpected results.

When comparing a string with a number, JavaScript will convert the string to a number when doing the comparison. An empty string converts to 0. A non-numeric string converts to NaN which is always false.

Case        | Value
---------------------
2 < 12      | true
2 < "John"  | false
2 > "John"  | false
2 == "John" | false
"2" < "12"  | false
"2" > "12"  | true
"2" == "12" | false

When comparing two strings, "2" will be greater than "12", because \(alphabetically\) 1 is less than 2.

To secure a proper result, variables should be converted to the proper type before comparison:

```javascript
age = Number(age);
if (isNaN(age)) {
  voteable = "Input is not a number";
} else {
  voteable = (age < 18) ? "Too young" : "Old enough";
}
```

## JavaScript if else and else if (https://www.w3schools.com/js/js_if_else.asp)

Conditional statements are used to perform different actions based on different conditions.

### Conditional Statements

Very often when you write code, you want to perform different actions for different decisions.

You can use conditional statements in your code to do this.

In JavaScript we have the following conditional statements:

  * Use if to specify a block of code to be executed, if a specified condition is true
  * Use else to specify a block of code to be executed, if the same condition is false
  * Use else if to specify a new condition to test, if the first condition is false
  * Use switch to specify many alternative blocks of code to be executed

### The if Statement

Use the **if** statement to specify a block of JavaScript code to be executed if a condition is true.

Syntax

```javascript
if (condition) {
  //  block of code to be executed if the condition is true
}
```

Exemplo: Make a "Good day" greeting if the hour is less than 18:00:

```javascript
if (hour < 18) {
  greeting = "Good day";
}
```


The result of greeting will be:

  Good day

### The else Statement

Use the **else** statement to specify a block of code to be executed if the condition is false.

Syntax

```javascript
if (condition) {
  //  block of code to be executed if the condition is true
} else {
  //  block of code to be executed if the condition is false
}
```

Exemplo: If the hour is less than 18, create a "Good day" greeting, otherwise "Good evening": (ifelse_demo1.html)

```javascript
if (hour < 18) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

The result of greeting will be:

  Good day

### The else if Statement

Use the **else if** statement to specify a new condition if the first condition is false.

Syntax

```javascript
if (condition1) {
  //  block of code to be executed if condition1 is true
} else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
} else {
  //  block of code to be executed if the condition1 is false and condition2 is false
}
```

Exemplo: If time is less than 10:00, create a "Good morning" greeting, if not, but time is less than 20:00, create a "Good day" greeting, otherwise a "Good evening":

```javascript
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

The result of greeting will be:

  Good day

## JavaScript Switch Statement (https://www.w3schools.com/js/js_switch.asp)

The **switch** statement is used to perform different actions based on different conditions.

### The JavaScript Switch Statement

Use the switch statement to select one of many code blocks to be executed.

Syntax

```javascript
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

This is how it works:

The switch expression is evaluated once.
The value of the expression is compared with the values of each case.
If there is a match, the associated block of code is executed.

Exemplo: The getDay\(\) method returna the weekday as a number between 0 and 6.

\(Sunday=0, Monday=1, Tuesday=2 ..\)

This Exemplo uses the weekday number to calculate the weekday name:

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
}
```

The result of day will be:

  Monday

### The break Keyword

When JavaScript reaches a **break** keyword, it breaks out of the switch block.

This will stop the execution of more code and case testing inside the block.

When a match is found, and the job is done, it's time for a break. There is no need for more testing.

    A break can save a lot of execution time because it "ignores" the execution of all the rest of the code in the switch block.

It is not necessary to break the last case in a switch block. The block breaks (ends) there anyway.

### The default Keyword

The **default** keyword specifies the code to run if there is no case match:

Exemplo: The getDay\(\) method returna the weekday as a number between 0 and 6.

If today is neither Saturday \(6\) nor Sunday \(0\), write a default message:

```javascript
switch (new Date().getDay()) {
  case 6:
    text = "Today is Saturday";
    break;
  case 0:
    text = "Today is Sunday";
    break;
  default:
    text = "Looking forward to the Weekend";
}
```

The result of text will be:

  Looking forward to the Weekend

The default case does not have to be the last case in a switch block:

Exemplo

```javascript
switch (new Date().getDay()) {
  default:
    text = "Looking forward to the Weekend";
    break;
  case 6:
    text = "Today is Saturday";
    break;
  case 0:
    text = "Today is Sunday";
}
```

    If default is not the last case in the switch block, remember to end the default case with a break.

### Common Code Blocks

Sometimes you will want different switch cases to use the same code.

In this Exemplo case 4 and 5 share the same code block, and 0 and 6 share another code block:

Exemplo

```javascript
switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Soon it is Weekend";
    break;
  case 0:
  case 6:
    text = "It is Weekend";
    break;
  default:
    text = "Looking forward to the Weekend";
}
```

### Switching Details

If multiple cases matches a case value, the first case is selected.

If no matching cases are found, the program continues to the default label.

If no default label is found, the program continues to the statement(s) after the switch.

### Strict Comparison

Switch cases use strict comparison \(===\).

The values must be of the same type to match.

A strict comparison can only be true if the operands are of the same type.

In this Exemplo there will be no match for x:

Exemplo

```javascript
var x = "0";
switch (x) {
  case 0:
    text = "Off";
    break;
  case 1:
    text = "On";
    break;
  default:
    text = "No value found";
}
```

## JavaScript For Loop (https://www.w3schools.com/js/js_loop_for.asp)

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
