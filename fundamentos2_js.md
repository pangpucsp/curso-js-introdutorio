# Fundamentos II de JavaScript

Esta é a continuação de [Fundamentos de JS](fundamento_js.md).

## Tipos de Dados em JavaScript [JS Data Types](https://www.w3schools.com/js/js_datatypes.asp)

Variáveis de JavaScript podem armazenar muitos tipos de dados: números, strings, objetos e mais:

```javascript
var comprimento = 16;                                    // Número
var ultimoNome = "Almeida";                              // String
var x = {primeiroNome:"João", ultimoNome:"Carvalho"};    // Objeto
```

### O Conceito de Tipos de Dados

Em programação, tipos de dados é um conceito importante.

Para ser capaz de trabalhar com as variáveis, é importante conhecer o tipo da valor armazenado na variável.

Sem tipo de dados, um computador não pode resolver com segurança a instrução:

```javascript
var x = 16 + "Volvo";
```

JavaScript calcula as expressões da esquerda para a direita. Sequências diferentes podem produzir resultados diferentes.
    Em computação, a ordem dos fatores é importante.

```javascript
var x = 16 + 4 + "Volvo";    // == "20Volvo" -- é diferente de
var y = "Volvo" + 16 + 4;    // == "Volvo164"
```

### Tipos em JavaScript São Dinâmicos

JavaScript tem tipos dinâmicos. Isto é, uma mesma variável pode ser usada para armazenar diferentes tipos de dados:

```javascript
var x;           // x é *undefined*
x = 5;           // x é um Number
x = "John";      // x é um String
```

### Strings em JavaScript

Um string \(ou um string de texto\) é uma sequência de caracteres como "John Doe".
    Observe que JavaScript não tem um tipo de dado carácter como outras linguagens.

Strings são escritas com aspas ou apóstrofes:

```javascript
var carName = "Volvo XC60";   // com aspas
var carName = 'Volvo XC60';   // com apóstrofes
var answer = "It's alright";             // apóstrofe dentro de aspas
var answer = "He is called 'Johnny'";    // apóstrofes dentro de aspas
var answer = 'He is called "Johnny"';    // aspas dentro de apóstrofes
```

### Números em JavaScript

JavaScript só tem um tipo de número \(number\).

Números podem ser escritos com ou sem parte decimal:

```javascript
var x1 = 34.00;     // número com parte decimal
var x2 = 34;        // número sem parte decimal
```

Números muito grandes ou próximos de zero podem ser escritos com notação científica:

```javascript
var y = 123e5;      // 12300000 | observe que o número inteiro após o e é o
var z = 123e-5;     // 0.00123  | expoente do 10 na notação científica
```

### Booleanos em JavaScript

Valores booleanos \(lógicos\) só podem ter dois valores: **true** ou **false**.

```javascript
var x = 5;
var y = 5;
var z = 6;
(x == y)       // retorna true
(x == z)       // retorna false
```

Booleanos são, em geral, usados para o teste condicional.

### Arrays em JavaScript são escritos com cochetes.

Itens de um array são separados por vírgulas.

O código a seguir declara \(cria\) um array chamado de carros, contendo três itens \(nomes dos carros\):

```javascript
var carros = ["Ford", "Kia", "BMW"];
```

Indices de um array começam com zero, isto é, o primeiro item é [0], o segundo is [1] e assim por diante.

### Objetos em JavaScript

Objetos em JavaScript são escritos com chaves.

Propriedades de objetos são escritas como pares nome:valor, separadas por vírgulas.

```javascript
var pessoa = {nome:"José", sobrenome:"Siva", idade:50, corDosOlhos:"azul"};
```

O objeto \(pessoa\) no exemplo acima tem 4 propriedades: nome, sobrenome, idade e corDosOlhos.

### O Operador **typeof**

Você pode usar o operador **typeof** do JavaScript para achar o tipo de uma variável no JavaScript.

O operador typeof retorna o tipo de uma variable (do valor em uma variável) ou uma expressão:

```javascript
typeof ""                  // retorna "string"
typeof "José"              // retorna "string"
typeof "José Silva"          // retorna "string"
```

### Undefined

Em JavaScript, uma variável sem um valor, tem o valor **undefined**. O tipo também é **undefined**.

```javascript
carro = undefined;        // Valor é undefined, tipo é undefined
```

### Valores Vazios

Um valor vazio não tem nada a ver com **undefined**.

Um string vazio tem um valor e um tipo válidos.

```javascript
var carro = "";              // O valor é "", o typeof é "string"
```

    Você pode considerar um bug no JavaScript que o typeof de null é um
    objeto (objet). Deveria ser null.

### Diferenças entre Undefined e Null

Undefined e null são iguais em valor, mas diferentes no tipo:

```javascript
typeof undefined           // undefined
typeof null                // object

null === undefined         // false
null == undefined          // true
```

### Dados Primitivos

Um valor de dados primitivo é um valor de dados simples único sem propriedades e métodos adicionais.

O operador typeof pode retornar um dos seguintes tipos primitivos:

* string
* number
* boolean
* undefined

```javascript
typeof "José"              // retorna "string"
typeof 3.14                // retorna "number"
typeof true                // retorna "boolean"
typeof false               // retorna "boolean"
typeof x                   // retorna "undefined" (se x não tem nenhum valor)
```

### Dados Complexos

O operador typeof pode retornar um dos dois tipos complexos:

* function
* object

O operador typeof retorna object para ambos objetos: **arrays** e **null**.

O operador typeof não retorna object para funções.

```javascript
typeof {name:'John', age:34} // retorna "object"
typeof [1,2,3,4]             // retorna "object" (não "array")
typeof null                  // retorna "object"
typeof function myFunc(){}   // retorna "function"
```

    O operador typeof retorna "object" para arrays porque em JavaScript arrays
    são objetos.

## Funções em JavaScript (https://www.w3schools.com/js/js_functions.asp)

Uma função JavaScript é um bloco de código projetado para realizar uma tearefa particular.

Uma função JavaScript é executada quando *algo* a invoca \(a chama\).

```javascript
function myFunction(p1, p2) {
  return p1 * p2;    // A function retorna o produto de p1 com p2
}
```

### Sintaxe da Função em JavaScript

Uma função em JavaScript é definida com a palavra-chavee **function**, seguida de um nome, seguido por \(\).

Nomes de função pode conter letras, dígitos, sinais de subscrito e dollar \(mesmas regras para nomesde variáveis\).

Os parenteses podem incluir nomes de variáveis esparadas por vírgulas:
**\(parametro1, parametro2, ...\)**

O código a ser executado pela função é colocado dentro de chaves: \{\}, \(ele é chamado de corpo da função\)

```javascript
function nome(parametro1, parametro2, parametro3) {
  // código a ser executado
}
```

**Parâmetros** de função são listados dentro dos parenteses \(\) na definição da função.

Valores de **argumentos** são os **valores** recebidos pela função quando ela é invocada.

Dentro das funções, os argumentos \(os parâmetros\) comportam-se como variáveis locais.

    Uma Function (função) é o mesmo que Procedure (procedimento) ou uma
    Subroutine (subrotina), de outras linguagens de programação.

### Invocação de Funções

O código dentro da função será executado quando "algo" invoca \(chama\) a função:

  * Quando um evento ocorre \(p.e.x, um usuário clica um botão\)
  * Quando é invocada \(called\) por um código de JavaScript
  * Automaticamente \(auto invocação\)

### Retorno da Função

Quando o JavaScript encontra uma **instrução return**, a função para de executar.

Se a função foi invocada por uma instrução, o JavaScript retorna para executar o código após a instrução de invocação.

Funções sempre calculam o valor de retorno. O **valor de retorno** é "retornado" para o "chamador".

Exemplo: Calcular a soma de dois números e retorná-lo.

```javascript
var x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```

### Para que Funções?

  * Você pode reutilisar o código: Defina o código uma vez e use ele muitas vezes.
  * Você pode usar o mesmo código muitas vezes com diferentes argumentos, para produzir resultados diferentes.

Exemplo: Converta Fahrenheit em Celsius: [Demo: função1](funct_demo1.html)

```javascript
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius(77);
```

### O Operador \(\) Invoca a Função
Do exemplo acima, toCelsius refere-se ao objeto função e toCelsius() refere-se ao resultado da applicação da função.

Acessar uma função sem \(\) retorna a definição da função em vez do resultado da função: [Demo: função2](funct_demo2.html)

```javascript
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius;
```

### Funções Usadas como Valores de Variáveis

As funções podem ser usadas do mesmo jeito que você usa variáveis, em todos os tipos de fórmulas, atribuições e cálculos.

```javascript
var texto = "A temperatura é " + toCelsius(77) + " Celsius";
```

### Variáveis Locais

Variáveis declaradas dentro de uma função de JavaScript tornam-se **LOCAIS** à função.

Variáveis locais só podem ser acessadas de dentro da função.

```javascript
// código aqui NÃO pode usar marcaCarro

function myFunction() {
  var marcaCarro = "Ford";
  // código aqui PODE usar marcaCarro
}

// código aqui NÃO pode usar marcaCarro
```

Como variáveis locais só podem ser reconhecidas dentro de funções, variáveis com o mesmo nome podem ser usadas em diferentes funções.

    O JavaScript não exige que as variáveis sejam declaradas antes de serem
    usadas. Evite fazer isto. Como será visto mais para frente, as variáveis
    não declaradas, são, implitamente, globais e podem provocar erros muito
    sutis.

Variáveis locais são criadas quando uma função começa a executar e removidas quando a função termina.

## Objetos em JavaScript (https://www.w3schools.com/js/js_objects.asp)

### Objetos na Vida Real: Propriedades e Métodos

Na vida real, um carro é um **objeto**.

Um carro tem *propriedades* como peso e cor e *métodos* como avançar e parar.

Todos os carros têm as mesmas propriedades, mas os valores diferem de carro para carro.

Todos carros têm os mesmos métodos, mas os métodos são executados em momentos diferentes.

### Objetos em JavaScript

Você já aprendeu que variáveis em JavaScript são depósitos de valores de dados.

O código a seguir atribui um único valor \(Fiat\) para uma variável chamada de carro:

```javascript
var carro = "Fiat";
```

Objetos são variáveis, também. Mas objetos podem ter muitos valores.

Este código atribui muitos valores \(Fiat, 500, white\) a uma variável chamada de carro:

```javascript
var carro = {marca:"Fiat", modelo:"500", cor:"white"};
```

Os valores estão escritos como pares nome:valor (nome e valor separados por uma vírgula).

    JavaScript objects are containers for named values called properties or methods.

### Definição de Objeto

Você define (e cria) um objeto JavaScript com um *objeto literal*:

```javascript
var pessoa = {nome:"Maria", sobrenome:"Carvalho", idade:50, corDeOlhos:"Azul"};
```

### Propriedades de Objetos

Os pares nome:valor em objetos de JavaScript são chamados de propriedades:

Propriedade  | Valor Propriedade
----------|----------------
nome | Maria
sobrenome  | Carvalho
idade       | 50
corDeOlhos  | azul

## Acesso à Propriedade de Objetos

Você pode acessar propriedades de objetos de duas maneiras:

```javascript
nomeDoObjeto.nomePropriedade
```

ou

```javascript
nomeDoObjeto["nomePropriedade"]
```

### Métodos de Objetos

Objetos podem ter também métodos.

Métodos são ações que podem ser realizadas sobre objetos.

Métodos são armazenados em propriedades como definições de funções.

Propriedade  | Valor Propriedade
-------------|-------------
nome | Maria
sobrenome  | Carvalho
idade       | 50
corDeOlhos  | azul
nomeCompleto  | function() {return this.nome + " " + this.sobrenome;}

    Um método é uma função armazenada como uma propriedade.

```javascript
var pessoa = {
  nome: "Maria",
  sobrenome : "Carvalho",
  idade     : 50,
  nomeCompleto : function() {
    return this.nome + " " + this.sobrenome;
  }
};
```

### A Palavra-Chave **this**

Na definição de uma função, **this** refere-se ao "proprietário" da função.

No exemplo acima, **this** é o objeto *pessoa* que "possui" a função  nomeCompleto.

Ou seja, this.nome significa a propriedade *nome* deste objeto.

### Acesso de Métodos de Objeto

Você acessa um método de objeto com a seguinte sintaxe:

```javascript
nomeObjeto.nomeMetodo()
```

Exemplo: [Demo: objeto](obj_demo1.html)

### **NÃO** Declare Strings, Números e Booleanos como Objetos!

Quando uma variável JavaScript é declarada com a palavra-chave "new", a variável é  criada como um objeto:

```javascript
var x = new String();        // declara x como um objeto String
var y = new Number();        // declara y como um objeto Number
var z = new Boolean();       // declara z como um objeto Boolean
```

    Evite objetos String, Number e Boolean.
    Eles complicam seu código e retardam a execução.

## Eventos de JavaScript (https://www.w3schools.com/js/js_events.asp)

Eventos HTML são "coisas" que acontecem com elementos de HTML.

Quando o JavaScript é usado em páginas de HTML, o JavaScript pode "reagi" a estes eventos.

### Eventos de HTML

Um evento de HTML pode ser alguma coisa que o navegador faz, ou alguma coisa que o usuário faz.

Eis alguns exemplos de eventos de HTML:

  * Uma página web em HTML acabou de ser carregada;
  * Um campo de entrada de HTML mudou; e
  * Um botão de HTML foi acionado.

Em geral, quando um evento acontece, você pode querer fazer alguma coisa.

JavaScript permite que você execute código quando eventos são detectados.

HTML permite que atributos de manipuladores de eventos, com código de JavaScript, sejam adicionados a elementos de HTML.

Com apóstrofes:

```html
<element evento='algum JavaScript'>
```

Com aspas:

```html
<element evento="algum JavaScript">
```

No exemplo a seguir, um atributo *onclick* \(com código\), é adicionado ao elemento botão: [Demo: evento](ev_demo1.html)

```html
<button onclick="document.getElementById('demo').innerHTML =
 Date()">Que hora são?</button>
```

    Código JavaScript em geral tem várias linhas.
    O usual é atributos de eventos chamarem funções: [Demo: evento2](ev.demo2.html)

```javascript
<button onclick="displayDate()">Que horas são?</button>
```

### Eventos HTML Comuns

Eis uma lista de alguns eventos HTML comuns:

Evento      | Descrição
------------|---------------------------------------------------------
onchange    | Um elemento HTML mudou
onclick     | O usuário clicou num elemento de HTML
onmouseover | O usuário moveu o mouse sobre um elemento de HTML
onmouseout  | O usuário moveu o mouse para fora de um elemento de HTML
onkeydown   | O usuário acionou uma tecla do teclado
onload      | O navegador acabou de carregar uma página

Uma lista completa de eventos de HTML pode ser encontradad em [Eventos de HTML](https://www.w3schools.com/jsref/dom_obj_event.asp)

### O Que o JavaScript Pode Fazer?

Manipuladores de eventos podem ser usados para manipular e verificar entradas e ações dos usuários e do navegador:

  * Coisas que devem ser feitas toda vez que uma página é carregada;
  * Coisas que devem ser feitas quando uma página é fechada;
  * Ação que deve ser realizada quando um usuário clica um botão;
  * Conteúdo que deve ser verificado quando um usuário fornece dados de entrada; e
  * Mais ...

Muitos métodos diferentes podem ser usados para deixar o JavaScript trabalhar com os eventos:

  * atributos de eventos de HTML pode executar código JavaScript diretamente;
  * atributos de eventos de HTML podem chamar funções de JavaScript;
  * você pode atribuir suas próprias funções manipuladoras de eventos a elementos de HTML;
  * você pode evitar que eventos sejam enviados ou manipulados; e
  * Mais ...

## Strings em JavaScript (https://www.w3schools.com/js/js_strings.asp)

### Strings de JavaScript

Um string de JavaScript composto por zero ou mais caracteres entre aspas, ou apóstrofes.

```javascript
var x = "John Doe";
```

### Comprimento da String

O comprimento de uma string é encontrado na propriedade comprimento interna da string:

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

### Caracteres Especiais

Porque strings devem ser escritas entre aspas, JavaScript não vai entender a string abaixo:

```javascript
var x = "Somos os "Guerreiros" do sul.";
```

A string será truncada em "Somos os ".

A solução para evitar este problema é usar o carácter barra invertida \(\\\),  carácter de escape.

O carácter de escape, \(\\\), faz que caracteres especiaispossam ser usados como caracteres de string:

Código | Resultado | Descrição
-----|--------|-------------
\\'  | '      | Apóstrofe
\\"  | "      | Aspas
\\\\ | \\     | Barra invertida

A sequência \\"  insere uma aspas numa string:

```javascript
var x = "Somos os \"Gerreiros\" do sul.";
```

Outras seis sequências de escape que são válidas em JavaScript:

Código | Resultado
--------------------------
\\b  | Retorno de um espaço
\\f  | Salto de Folha
\\n  | Linha Nova
\\r  | Retorno do Carro
\\t	 | Tabulador Horizontal
\\v  | Tabulador Vertical

    Estes 6 caracteres de escape foram originalmente projetados para teletipos,
    telegrafos e máquinas de FAX. Eles não têm sentido no HTML.

### Quebra de Linhas Longas de Código

Para melhor legibilidade, programadores, em geral, evitam linhas de código mais longas que 80 caracteres.

Se uma instrução JavaScript não cabe numa linha, o melhor lugar para quebrá-la é depois de um operador:

```javascript
document.getElementById("demo").innerHTML =
"Alo Teresinha!";
```

Você também pode quebrar uma linha de código usando uma barra invertida antes de saltar a linha:

```javascript
document.getElementById("demo").innerHTML = "Alo \
Teresinha!";
```

    O método da \\ não é o método preferido. É melhor evitá-lo,
    alguns navegadores podem não entender espaços após o \.

Uma maneira mais segura é quebrar a string e concatenar as partes:

```javascript
document.getElementById("demo").innerHTML = "Alo " +
"Teresinha!";
```

You **cannot break up** a code line with a backslash:

```javascript
document.getElementById("demo").innerHTML = \
"Hello Dolly!";
```

### Strings Can be Objects

Normally, JavaScript strings are primitive values, created from literals:

**var firstName = "John";**

But strings can also be defined as objects with the keyword new:

**var firstName = new String("John");**

```javascript
var x = "John";
var y = new String("John");

// typeof x will return string
// typeof y will return object
```

    Don't create strings as objects. It slows down execution speed.
    The new keyword complicates the code. This can produce some unexpected results:

```javascript
var x = "John";             
var y = new String("John");

// (x == y) is true because x and y have equal values
// (x === y) is false because x and y have different types (string and object)
```

When using the === operator, equal strings are not equal, because the === operator expects equality in both type and value.


Or even worse. Objects cannot be compared:

```javascript
var x = new String("John");             
var y = new String("John");

// (x == y) is false because x and y are different objects
// (x === y) is false because x and y are different objects
```

## JavaScript String Methods (https://www.w3schools.com/js/js_string_methods.asp)

## String Methods and Properties

Primitive values, like "John Doe", cannot have properties or methods \(because they are not objects\).

But with JavaScript, methods and properties are also available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

### String Length

The length property returns the length of a string:

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

### Finding a String in a String

The indexOf\(\) method returns the index of \(the position of\) the first occurrence of a specified text in a string: (str_demo1.html)

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
```

The lastIndexOf() method returns the index of the last occurrence of a specified text in a string:

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.lastIndexOf("locate");
```

Both indexOf\(\), and lastIndexOf\(\) return -1 if the text is not found.

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.lastIndexOf("John");
```

Both methods accept a second parameter as the starting position for the search: (str_demo3.html)

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate",15);
```

### Searching for a String in a String

The search\(\) method searches a string for a specified value and returns the position of the match:

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.search("locate");
```

The two methods, indexOf\(\) and search\(\), *are equal*?

They accept the same arguments \(parameters\), and return the same value?

The two methods are NOT equal. These are the differences:

  * The search\(\) method cannot take a second start position argument.
  * The indexOf\(\) method cannot take powerful search values \(regular expressions\).

### Extracting String Parts
There are 3 methods for extracting a part of a string:

  - slice\(start, end\)
  - substring\(start, end\)
  - substr\(start, length\)

#### The slice\(\) Method

slice\(\) extracts a part of a string and returns the extracted part in a new string.

The method takes 2 parameters: the start position, and the end position \(end not included\).

Example: (str_demo2.html)

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.slice(7, 13);
```

If a parameter is negative, the position is counted from the end of the string. (str_demo4.html)

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.slice(-12, -6);
```

If you omit the second parameter, the method will slice out the rest of the string:

```javascript
var res = str.slice(7);  // same as (in this case): var res = str.slice(-12);
```

    Negative positions do not work in Internet Explorer 8 and earlier.

#### The substring\(\) Method

**substring\(\)** is similar to slice\(\).

The difference is that substring() cannot accept negative indexes.

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.substring(7, 13);
```

#### The substr\(\) Method

**substr\(\)** is similar to slice\(\).

The difference is that the second parameter specifies the length of the extracted part.

```javascript
var str = "Apple, Banana, Kiwi";
var res = str.substr(7, 6);
```

If you omit the second parameter, substr() will slice out the rest of the string.

#### Replacing String Content

The replace() method replaces a specified value with another value in a string:

```javascript
str = "Please visit Microsoft!";
var n = str.replace("Microsoft", "W3Schools");
```

    The replace\(\) method does not change the string it is called on. It returns a new string.

To replace case insensitive, use a regular expression with an /i flag \(insensitive\):

```javascript
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3Schools");
```

    Note that regular expressions are written without quotes.

To replace all matches, use a regular expression with a /g flag \(global match\):

```javascript
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3Schools");
```

#### Converting to Upper and Lower Case

A string is converted to upper case with toUpperCase\(\):

```javascript
var text1 = "Hello World!";       // String
var text2 = text1.toUpperCase();  // text2 is text1 converted to upper
```

A string is converted to lower case with toLowerCase():

```javascript
var text1 = "Hello World!";       // String
var text2 = text1.toLowerCase();  // text2 is text1 converted to lower
```

#### The concat\(\) Method

concat\(\) joins two or more strings:

```javascript
var text1 = "Hello";
var text2 = "World";
var text3 = text1.concat(" ", text2);
```

The concat() method can be used instead of the plus operator. These two lines do the same:

```javascript
var text = "Hello" + " " + "World!";
var text = "Hello".concat(" ", "World!");
```

    All string methods return a new string. They don't modify the original string.
    Formally said: Strings are immutable: Strings cannot be changed, only replaced.

#### String.trim\(\)

String.trim\(\) removes whitespace from both sides of a string.

```javascript
var str = "       Hello World!        ";
alert(str.trim());
```

    String.trim() is not supported in Internet Explorer 8 or lower.

If you need to support IE 8, you can use String.replace with a regular expression instead:

```javascript
var str = "       Hello World!        ";
alert(str.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, ''));
```

### Extracting String Characters

There are 3 methods for extracting string characters:

  * charAt\(position\)
  * charCodeAt(position)
  * Property access \[ \]

#### The charAt\(\) Method

The charAt\(\) method returns the character at a specified index \(position\) in a string:

```javascript
var str = "HELLO WORLD";
str.charAt(0);            // returns H
```

#### The charCodeAt\(\) Method

The charCodeAt\(\) method returns the unicode of the character at a specified index in a string:

The method returns a UTF-16 code \(an integer between 0 and 65535\).

```javascript
var str = "HELLO WORLD";

str.charCodeAt(0);         // returns 72
```

#### Property Access

ECMAScript 5 \(2009\) allows property access \[ \] on strings:

```javascript
var str = "HELLO WORLD";
str[0];                   // returns H
```

    Property access might be a little unpredictable:

    * It does not work in Internet Explorer 7 or earlier
    * It makes strings look like arrays (but they are not)
    * If no character is found, [ ] returns undefined, while charAt() returns an empty string.
    * It is read only. str[0] = "A" gives no error (but does not work!)

    If you want to work with a string as an array, you can convert it to an array.

#### Converting a String to an Array

A string can be converted to an array with the split() method:

```javascript
var txt = "a,b,c,d,e";   // String
txt.split(",");          // Split on commas
txt.split(" ");          // Split on spaces
txt.split("|");          // Split on pipe
```

If the separator is "", the returned array will be an array of single characters:

```javascript
var txt = "Hello";       // String
txt.split("");           // Split in characters
```

For a complete reference on JavaScript strings see (https://www.w3schools.com/jsref/jsref_obj_string.asp).

## JavaScript Numbers (https://www.w3schools.com/js/js_numbers.asp)

JavaScript has only one type of number. Numbers can be written with or without decimals.

```javascript
var x = 3.14;    // A number with decimals
var y = 3;       // A number without decimals
```

### JavaScript Numbers are Always 64-bit Floating Point

Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc.

JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.

This format stores numbers in 64 bits, where the number (the fraction) is stored in bits 0 to 51, the exponent in bits 52 to 62, and the sign in bit 63:

Value (aka Fraction/Mantissa) | Exponent          | Sign
--------------------------------------------------------------
52 bits (0 - 51)              | 11 bits (52 - 62) | 1 bit (63)

### Precision

Integers (numbers without a period or exponent notation) are accurate up to 15 digits.

```javascript
var x = 999999999999999;   // x will be 999999999999999
var y = 9999999999999999;  // y will be 10000000000000000
```

The maximum number of decimals is 17, but floating point arithmetic is not always 100% accurate:

```javascript
var x = 0.2 + 0.1;         // x will be 0.30000000000000004
```

To solve the problem above, it helps to multiply and divide:

```javascript
var x = (0.2 * 10 + 0.1 * 10) / 10;       // x will be 0.3
```

### Adding Numbers and Strings

    WARNING !!
    JavaScript uses the \+ operator for both addition and concatenation.
    Numbers are added. Strings are concatenated.

If you add two numbers, the result will be a number, if you add two strings, the result will be string:

```javascript
var x = 10;
var y = 20;
var z = x + y;           // z will be 30 (a number)
var x = 10;
var y = "20";
var z = x + y;           // z will be 1020 (a string)
```

A common mistake is to expect this result to be 102030:

```javascript
var x = 10;
var y = 20;
var z = "30";
var result = x + y + z;  // z will be "3030"
```

### Numeric Strings

JavaScript strings can have numeric content:

```javascript
var x = 100;         // x is a number

var y = "100";       // y is a string
```

JavaScript will try to convert strings to numbers in all numeric operations:

This will work:

```javascript
var x = "100";
var y = "10";
var z = x / y;       // z will be 10
```

This will also work:

```javascript
var x = "100";
var y = "10";
var z = x * y;       // z will be 1000
```

But this will not work:

```javascript
var x = "100";
var y = "10";
var z = x + y;       // z will not be 110 (It will be 10010)
```

    In the last example JavaScript uses the + operator to concatenate the strings.

### NaN - Not a Number

**NaN** is a JavaScript reserved word indicating that a number is not a legal number.

Trying to do arithmetic with a non-numeric string will result in NaN (Not a Number):

```javascript
var x = 100 / "Apple";  // x will be NaN (Not a Number)
```
However, if the string contains a numeric value , the result will be a number:

```javascript
var x = 100 / "10";     // x will be 10
```

You can use the global JavaScript function isNaN() to find out if a value is a number:

```javascript
var x = 100 / "Apple";
isNaN(x);               // returns true because x is Not a Number
```

Watch out for NaN. If you use NaN in a mathematical operation, the result will also be NaN:

```javascript
var x = NaN;
var y = 5;
var z = x + y;         // z will be NaN
```

Or the result might be a concatenation:

```javascript
var x = NaN;
var y = "5";
var z = x + y;         // z will be NaN5
```

NaN is a number: typeof NaN returns number:

```javascript
typeof NaN;            // returns "number"
```

### Infinity

Infinity \(or -Infinity\) is the value JavaScript will return if you calculate a number outside the largest possible number.

```javascript
var myNumber = 2;
while (myNumber != Infinity) {          // Execute until Infinity
  myNumber = myNumber * myNumber;
}
```

### Division by 0 \(zero\) also generates Infinity:

```javascript
var x =  2 / 0;          // x will be Infinity
var y = -2 / 0;          // y will be -Infinity
```

Infinity is a number: typeof Infinity returns number.

```javascript
typeof Infinity;        // returns "number"
```

### Hexadecimal

JavaScript interprets numeric constants as hexadecimal if they are preceded by 0x.

```javascript
var x = 0xFF;           // x will be 255
```

    Never write a number with a leading zero (like 07).
    Some JavaScript versions interpret numbers as octal if they are written with a leading zero.

By default, JavaScript displays numbers as base 10 decimals.

But you can use the toString() method to output numbers from base 2 to base 36.

Hexadecimal is base 16. Decimal is base 10. Octal is base 8. Binary is base 2.

```javascript
var myNumber = 32;
myNumber.toString(10);  // returns 32
myNumber.toString(32);  // returns 10
myNumber.toString(16);  // returns 20
myNumber.toString(8);   // returns 40
myNumber.toString(2);   // returns 100000
```

### Numbers Can be Objects

Normally JavaScript numbers are primitive values created from literals:

```javascript
var x = 123;
```

But numbers can also be defined as objects with the keyword new:

```javascript
var y = new Number(123);
```

```javascript
var x = 123;
var y = new Number(123);

// typeof x returns number
// typeof y returns object
```

    Do not create Number objects. It slows down execution speed.
    The new keyword complicates the code. This can produce some unexpected results:

When using the == operator, equal numbers are equal:

```javascript
var x = 500;             
var y = new Number(500);

// (x == y) is true because x and y have equal values
// (x === y) is false because x and y have different types
```

When using the === operator, equal numbers are not equal, because the === operator expects equality in both type and value.

## JavaScript Number Methods (https://www.w3schools.com/js/js_number_methods.asp)

### Number Methods and Properties
Primitive values (like 3.14 or 2014), cannot have properties and methods (because they are not objects).

But with JavaScript, methods and properties are also available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

### The toString\(\) Method

toString\(\) returns a number as a string.

All number methods can be used on any type of numbers \(literals, variables, or expressions\):

```javascript
var x = 123;
x.toString();            // returns 123 from variable x
(123).toString();        // returns 123 from literal 123
(100 + 23).toString();   // returns 123 from expression 100 + 23
```

### The toExponential\(\) Method

toExponential\(\) returns a string, with a number rounded and written using exponential notation.

A parameter defines the number of characters behind the decimal point:

```javascript
var x = 9.656;
x.toExponential(2);     // returns 9.66e+0
x.toExponential(4);     // returns 9.6560e+0
x.toExponential(6);     // returns 9.656000e+0
```

The parameter is optional. If you don't specify it, JavaScript will not round the number.

### The toFixed\(\) Method

toFixed\(\) returns a string, with the number written with a specified number of decimals:

```javascript
var x = 9.656;
x.toFixed(0);           // returns 10
x.toFixed(2);           // returns 9.66
x.toFixed(4);           // returns 9.6560
x.toFixed(6);           // returns 9.656000
```

    toFixed(2) is perfect for working with money.

### The toPrecision\(\) Method
toPrecision\(\) returns a string, with a number written with a specified length:

```javascript
var x = 9.656;
x.toPrecision();        // returns 9.656
x.toPrecision(2);       // returns 9.7
x.toPrecision(4);       // returns 9.656
x.toPrecision(6);       // returns 9.65600
```

### The valueOf\(\) Method

valueOf\(\) returns a number as a number.

```javascript
var x = 123;
x.valueOf();            // returns 123 from variable x
(123).valueOf();        // returns 123 from literal 123
(100 + 23).valueOf();   // returns 123 from expression 100 + 23
```

In JavaScript, a number can be a primitive value \(typeof = number\) or an object \(typeof = object\).

The valueOf\(\) method is used internally in JavaScript to convert Number objects to primitive values.

There is no reason to use it in your code.

    All JavaScript data types have a valueOf() and a toString() method.

### Converting Variables to Numbers

There are 3 JavaScript methods that can be used to convert variables to numbers:

  * The Number\(\) method
  * The parseInt\(\) method
  * The parseFloat\(\) method

These methods are not number methods, but global JavaScript methods.

### Global JavaScript Methods

JavaScript global methods can be used on all JavaScript data types.

These are the most relevant methods, when working with numbers:

Method          | Description
--------------------------------------------------------------------------
Number\(\)      | Returns a number, converted from its argument.
parseFloat\(\)  | Parses its argument and returns a floating point number
parseInt\(\)    | Parses its argument and returns an integer

#### The Number\(\) Method

Number\(\) can be used to convert JavaScript variables to numbers:

```javascript
Number(true);          // returns 1
Number(false);         // returns 0
Number("10");          // returns 10
Number("  10");        // returns 10
Number("10  ");        // returns 10
Number(" 10  ");       // returns 10
Number("10.33");       // returns 10.33
Number("10,33");       // returns NaN
Number("10 33");       // returns NaN
Number("John");        // returns NaN
```

    If the number cannot be converted, NaN (Not a Number) is returned.

#### The Number\(\) Method Used on Dates

Number\(\) can also convert a date to a number:

```javascript
Number(new Date("2017-09-30"));    // returns 1506729600000
```

    The Number() method above returns the number of milliseconds since 1.1.1970.

#### The parseInt\(\) Method

parseInt\(\) parses a string and returns a whole number. Spaces are allowed. Only the first number is returned:

```javascript
parseInt("10");         // returns 10
parseInt("10.33");      // returns 10
parseInt("10 20 30");   // returns 10
parseInt("10 years");   // returns 10
parseInt("years 10");   // returns NaN
```

If the number cannot be converted, NaN (Not a Number) is returned.

#### The parseFloat\(\) Method

parseFloat\(\) parses a string and returns a number. Spaces are allowed. Only the first number is returned:

```javascript
parseFloat("10");        // returns 10
parseFloat("10.33");     // returns 10.33
parseFloat("10 20 30");  // returns 10
parseFloat("10 years");  // returns 10
parseFloat("years 10");  // returns NaN
```

### Number Properties

Property           | Description
-------------------------------------------------------------------------------
MAX_VALUE          | Returns the largest number possible in JavaScript
MIN_VALUE          | Returns the smallest number possible in JavaScript
POSITIVE_INFINITY  | Represents infinity (returned on overflow)
NEGATIVE_INFINITY  | Represents negative infinity (returned on overflow)
NaN                | Represents a "Not-a-Number" value

#### JavaScript MIN_VALUE and MAX_VALUE

Example: (num_demo1.html)

```javascript
var x = Number.MAX_VALUE;
var y = Number.MIN_VALUE;
```

#### JavaScript POSITIVE_INFINITY

```javascript
var x = Number.POSITIVE_INFINITY;
```

POSITIVE_INFINITY is returned on overflow:

```javascript
var x = 1 / 0;
```

#### JavaScript NEGATIVE_INFINITY

```javascript
var x = Number.NEGATIVE_INFINITY;
// NEGATIVE_INFINITY is returned on overflow:
var y = -1 / 0;
```

#### JavaScript NaN - Not a Number

```javascript
var x = Number.NaN;
// Trying to do arithmetic with a non-numeric string will result in NaN (Not a Number):
var x = 100 / "Apple";  // x will be NaN (Not a Number)
```

#### Number Properties Cannot be Used on Variables

Number properties belongs to the JavaScript's number object wrapper called Number.

These properties can only be accessed as Number.MAX_VALUE.

Using myNumber.MAX_VALUE, where myNumber is a variable, expression, or value, will return undefined:

```javascript
var x = 6;
var y = x.MAX_VALUE;    // y becomes undefined
```

A complete reference to JavaScript numbers can be seen on (https://www.w3schools.com/jsref/jsref_obj_number.asp).
