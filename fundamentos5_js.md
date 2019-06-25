# Fundamentos V de JavaScript

Esta é a continuação de [Fundamentos IV de JS](fundamento4_js.md).

## Conversão de Tipos em JavaScript (https://www.w3schools.com/js/js_type_conversion.asp)

*Number\(\)* converte para um Number, *String\(\)* converte para uma String,
*Boolean\(\)* converte para um Boolean.

### Tipos de Dados em JavaScript

JavaScript tem 5 tipos de dados diferentes que podem conter valores:

  * *string* (texto)
  * *number* (número)
  * *boolean* (booleano, ou lógico)
  * *object* (objeto)
  * *function* (função)

Existem 3 tipos de objetos:

  * *Object* (Objeto)
  * *Date* (Data ou Horário)
  * *Array* (Vetor)

E dois tipos de dados que não podem conter valores:

  * *null* (vazio, nulo)
  * *undefined* (indefinido)

### O Operador typeof

Você pode usar o operador typeof para descobrir o tipo de dado de uma variável
em JavaScript.

Exemplo

```javascript
typeof "João"                 // Retorna "string"
typeof 3.14                   // Retorna "number"
typeof NaN                    // Retorna "number"
typeof false                  // Retorna "boolean"
typeof [1,2,3,4]              // Retorna "object"
typeof {name:'John', age:34}  // Retorna "object"
typeof new Date()             // Retorna "object"
typeof function () {}         // Retorna "function"
typeof myCar                  // Retorna "undefined" *
typeof null                   // Retorna "object"
```

Por favor, observe que:

  * O tipo de dado de *NaN* é number
  * O tipo de dado de um *array* é object
  * O tipo de dado de uma instância de *Date* é object
  * O tipo de dado de *null* é object
  * O tipo de dado de uma variável indefinida é *undefined*
  * O tipo de dado de uma variável que não teve um valor atribuido a ela é
  também *undefined*

    Você não pode usar typeof para determinar se um objeto de JavaScript é um
    array (ou uma data).

### O Tipo de Dados de typeof

O operador **typeof** não é uma variável. É um operador. Operadores como
\( + - * / \) não têm um tipo de dado.

Mas, o operador typeof sempre retorna uma string \(contendo o tipo do operando\).

### A Propriedade **constructor**

A propriedade *constructor* retorna a função construtora para todas as
variáveis de JavaScript. E pode ser usada para determinar o tipo de uma variável.

Exemplo

```javascript
"João".constructor                // Retorna function String()  {[native code]}
(3.14).constructor                // Retorna function Number()  {[native code]}
false.constructor                 // Retorna function Boolean() {[native code]}
[1,2,3,4].constructor             // Retorna function Array()   {[native code]}
{nome:'João',idade:34}.constructor  // Retorna function Object()  {[native code]}
new Date().constructor            // Retorna function Date()    {[native code]}
function () {}.constructor        // Retorna function Function(){[native code]}
```

Você pode checar a propriedade *constructor* para descobrir se um objeto é
um *Array* (contém a palavra "Array"):

Exemplo

```javascript
function isArray(myArray) {
  return myArray.constructor.toString().indexOf("Array") > -1;
}
```

Ou mais simples ainda, você pode checar se o objeto é uma função *Array*:

Exemplo

```javascript
function isArray(myArray) {
  return myArray.constructor === Array;
}
```

Você pode verificar a propridade constructor para descobrir se um objeto é
um *Date* (contém a palavra "Date"):

Exemplo

```javascript
function isDate(myDate) {
  return myDate.constructor.toString().indexOf("Date") > -1;
}
```

Ou mais simplesmente, você pode verificar se o objeto é uma função *Date*:

Exemplo

```javascript
function isDate(myDate) {
  return myDate.constructor === Date;
}
```

### Conversão de Tipo em JavaScript

Variáveis de JavaScript podem ser convertidos em uma nova variável e em um
novo tipo de dado:

  * Pelo uso de uma função do JavaScript
  * Automaticamente pelo próprio JavaScript

### Conversão de Números em Strings

O método global String\(\) pode converter convert números em strings.

Ele pode ser usado em qualquer tipo de números, literais, variáveis ou expressões:

Exemplo

```javascript
String(x)         // retorna uma string de uma variável x com um número
String(123)       // retorna uma string de um número literal 123
String(100 + 23)  // retorna uma string de um número de uma expressão
```

O método *toString\(\)* de *Number* faz a mesma coisa.

Exemplo

```javascript
x.toString()
(123).toString()
(100 + 23).toString()
```

Na seção Métodos de Number, você outros métodos que podem converter um número
numa string:

| Método            | Descrição |
|-------------------|------------------------------------|
| toExponential\(\) | Retorna uma string, com um número arredondado e escrito em notação científica. |
| toFixed\(\)       | Retorna uma string, com um número arredondado e escrito com um número especificado de dígitos decimais. |
| toPrecision\(\)   | Retorna uma string, com um número escrito com um comprimento especificado. |

### Conversão de Booleanos em Strings

O método global String\(\) pode converter booleanos em strings.

```javascript
String(false)      // retorna "false"
String(true)       // retorna "true"
```

O método toString() de Boolean faz a mesma coisa.

```javascript
false.toString()   // retorna "false"
true.toString()    // retorna "true"
```

### Conversão de Dates em Strings

O método global String() pode converter dates em strings.

```javascript
String(Date())  // retorna "Mon Jun 24 2019 00:35:08 GMT-0300 (Horário Padrão de Brasília)"
```

O método toString() de Date faz a mesma coisa.

Exemplo
```javascript
Date().toString()  // retorna "Mon Jun 24 2019 00:35:08 GMT-0300 (Horário Padrão de Brasília)"
```

Na seção Métodos de Date, você encontra outros métodos que podem ser usados
para converter dates em  strings.

### Conversão de Strings em Números

O método global Number\(\) pode converter strings em números.

Strings contendo números \(como "3.14"\) converte em numbers \(como 3.14\).

A string vazia converte em 0.

Qualquer outra coisa converte em NaN \(Not a Number, Não é um Número\).

```javascript
Number("3.14")    // retorna 3.14
Number(" ")       // retorna 0
Number("")        // retorna 0
Number("99 88")   // retorna NaN
```

Na seção de Métodos de Números, você encontra mais métodos que podem ser usados
para converter strings em números.

### O Operador + Unário

O operador + unário pode ser usado para converter uma variável num  número:

Exemplo
```javascript
var y = "5";      // y é uma string
var x = + y;      // x é um número
```

Se a variável não puder ser convertida, ela ainda assim será um número, mas
seu valor será NaN (Not a Number, Não Número):

Exemplo
```javascript
var y = "John";   // y é uma string
var x = + y;      // x é um número (NaN)
```

### Conversão de Booleanos em Números

O método global Number\(\) também pode converter booleanos em números.

```javascript
Number(false)     // retorna 0
Number(true)      // retorna 1
```

### Conversão de Dates em Números

O método Number\(\) pode ser usado para converter dates em números.

```javascript
d = new Date();
Number(d)          // retorna 1404568027739
```

O método getTime\(\) de Date obtém o mesmo resultado.

### Conversão Automática de Tipos

Quando o JavaScript tenta *operar* com um tipo *errado* de dados,
ele tentará converter o valor para o tipo *certo*.

O resultado, nem sempre, é o esperado:

```javascript
5 + null    // retorna 5         porque null é convertido em 0
"5" + null  // retorna "5null"   porque null é convertido em "null"
"5" + 2     // retorna "52"      porque 2 é convertiido em "2"
"5" - 2     // retorna 3         porque "5" é convertido em 5
"5" * "2"   // retorna 10        porque "5" e "2" são convertidos em 5 e 2
"5" + "2"   // retorna "52"      porque não há necessidade de conversão
```

### Conversão Automatica para String

JavaScript chama automaticamente a função toString\(\) da variável quando
você tenta "imprimir" um objeto ou uma variável:

```javascript
document.getElementById("demo").innerHTML = myVar;

// se myVar = {name:"Fjohn"}  // toString converte para "[object Object]"
// se myVar = [1,2,3,4]       // toString converte para "1,2,3,4"
// se myVar = new Date()      
// toString converte para "Tue Jun 25 2019 00:25:30 GMT-0300 (Horário Padrão de Brasília)"
```

Números e booleanos também são convertidos, mas isto não é muito visível:

```javascript
// se myVar = 123             // toString converte para "123"
// se myVar = true            // toString converte para "true"
// se myVar = false           // toString converte para "false"
```

### Tabela de Conversão de Tipo do JavaScript

Esta tabela mostra o resultado da conversão de diferente valores de JavaScript
para Número, String e Booleano:

| Valor Original | Convertido para to Number | Convertido para String | Convertido para Boolean |
|----------------|---------------------------|------------------------|--------------|
| false          | 0                   | "false"             | false |
| true           | 1                   | "true"              | true |
| 0              | 0                   | "0"                 | false |
| 1              | 1                   | "1"                 | true |
| "0"            | 0                   | "0"                 | true |
| "000"          | 0                   | "000"               | true |
| "1"            | 1                   | "1"                 | true |
| NaN            | NaN                 | "NaN"               | false |
| Infinity       | Infinity            | "Infinity"          | true |
| -Infinity      | -Infinity           | "-Infinity"         | true |
| ""             | 0                   | ""                  | false |
| "20"           | 20                  | "20"                | true |
| "vinte"        | NaN                 | "vinte"            | true |
| [ ]            | 0                   | ""                  | true |
| [20]           | 20                  | "20"                | true |
| [10,20]        | NaN                 | "10,20"             | true |
| ["vinte"]      | NaN                 | "vinte"            | true |
| ["dez","cinco"] | NaN                 | "dez,cinco"          | true |
| function(){}   | NaN                 | "function(){}"      | true |
| { }            | NaN                 | "[object Object]"   | true |
| null           | 0                   | "null"              | false |
| undefined      | NaN                 | "undefined"         | false |

## Operações em Bits no JavaScript (https://www.w3schools.com/js/js_bitwise.asp)

### Operadores de Bits em JavaScript

| Operador | Nome | Descrição |
|----------|------|---------------------------------------------------|
| &        | E  | Coloca cada bit em 1 se ambos os bits forem 1 |
| \|       | OU   | Coloca cada bit em 1 se um dos dois bits for 1 |
| ^        | XOR  | Coloca cada bit em 1 se apenas um dos dois bits for 1 |
| ~        | Não  | Inverte todos os bits |
| <<       | Deslocamento para esquerda completando com zero | Deslocamento para a esquerda preenchendo com zeros da direita e desprezando os bits saindo à esquerda |
| \>>      | Deslocamento para a direita com sinal | Deslocamento para a direita inserindo cópias do bit mais a esquerda (sinal) a esquerda e desprezando os bits saindo à direita |
| \>>>     | Deslocamento para direita completando com zero | Deslocamento para a direita preenchendo com zeros da esquerda e desprezando os bits saindo à direita |

Exemplos

| Operação | Resultado | Mesmo que      | Resultado |
|----------|-----------|----------------|---|
| 5 & 1    | 1         | 0101 & 0001    |  0001 |
| 5 \| 1   | 5         | 0101 \| 0001   |  0101 |
| ~ 5      | 10        |  ~0101         |  1010 |
| 5 << 1   | 10        | 0101 << 1      |  1010 |
| 5 ^ 1    | 4         | 0101 ^ 0001    |  0100 |
| 5 >> 1   | 2         | 0101 >> 1      |  0010 |
| 5 >>> 1  | 2         | 0101 >>> 1     |  0010 |

### JavaScript Usa Operandos de 32 bits

JavaScript armazena números na representação de ponto flutuante de 64 bits
\([IEEE 754](https://pt.wikipedia.org/wiki/IEEE_754)\), mas todas as operações
com bits são realizadas em números binários de 32 bits.

Antes que uma operação de bits seja realizada, o JavaScript converte os números
para inteiros de 32 bits com sinal.

Após a operação de bits ser realizada, o resultado volta a ser convertido para
números de 64 bits em ponto flutuante do JavaScript.

    Os exemplos acima usaram números binários de 4 bits sem sinal.
    Por causa disto: ~ 5 retorna 10.

    Como JavaScript usa inteiros de 32 bits com sinal,
    ele não retorna 10. Ele retorna -6.

    00000000000000000000000000000101 (5)

    11111111111111111111111111111010 (~5 = -6)

    Um inteiro com sinal usa o bits mais a esquerda (o mais significativo)
    como um bit de sinal. No caso, o JavaScript, como todas as linguagens de
    programação, usa a representação de inteiros em complemento de 2.

### E de Bits

Quando uma operação de E é realizada em dois bits, ela retorna 1 se ambos os
bits forem 1.

Exemplo de operações de E com bits, 1 bit com outro bit:

| Operação | Resultado |
|----------|---------|
| 0 & 0     | 0 |
| 0 & 1     | 0 |
| 1 & 0     | 0 |
| 1 & 1     | 1 |

Exemplo com palavras de 4 bits:

| Operação   | Resultado |
|------------|--------|
| 1111 & 0000 | 0000 |
| 1111 & 0001 | 0000 |
| 1111 & 0010 | 0010 |
| 1111 & 0100 | 0100 |

### Ou de Bits

Quando uma operação Ou de bits é realizada em dois bits, ela retorna 1 se um
dos bits for um:

Exemplo com um bit:

| Operação |  Resultado |
|----------|---------|
| 0 \| 0    |  0 |
| 0 \| 1    |  1 |
| 1 \| 0    |  1 |
| 1 \| 1    |  1 |

Exemplo com 4 bits:

| Operação    |  Resultado |
|-------------|---------|
| 1111 \| 0000 |  1111 |
| 1111 \| 0001 |  1111 |
| 1111 \| 0010 |  1111 |
| 1111 \| 0100 |  1111 |

### XOu (ou-exclusivo) de Bits

Quando uma operação de XOu é realizada em dois bits, ela retorna 1 se os dois
bits tiverem valores diferentes:

Exemplo com um bit:

| Operação | Resultado |
|-----------|-------|
| 0 ^ 0     | 0 |
| 0 ^ 1     | 1 |
| 1 ^ 0     | 1 |
| 1 ^ 1     | 0 |

Exemplo com 4 bits:

| operação   | Resultado |
|------------|--------|
| 1111 ^ 0000 | 1111 |
| 1111 ^ 0001 | 1110 |
| 1111 ^ 0010 | 1101 |
| 1111 ^ 0100 | 1011 |

### E de Bits no JavaScript \(&\)

Operação E de bits retorna 1 apenas se ambos os bits forem 1:

| Decimal | Binário |
|---------|------------------------------------|
| 5       | 00000000000000000000000000000101 |
| 1       | 00000000000000000000000000000001 |
| 5 & 1   | 00000000000000000000000000000001 \(1\) |

Exemplo

```javascript
var x = 5 & 1;
```

### OU de Bits no JavaScript \(\|\)

A operação de Ou de bits retorna 1 se um dos bits for 1:

| Decimal | Binário |
|---------|--------------------------------------|
| 5       | 00000000000000000000000000000101 |
| 1       | 00000000000000000000000000000001 |
| 5 \| 1  | 00000000000000000000000000000101 \(5\) |

Exemplo

```javascript
var x = 5 | 1;
```

### XOu de Bits no JavaScript \(^\)

A operação XOu de bits retorna 1 se os bits forem diferentes:

| Decimal | Binário |
|---------|--------------------------------------|
| 5       | 00000000000000000000000000000101 |
| 1       | 00000000000000000000000000000001 |
| 5 ^ 1   | 00000000000000000000000000000100 (4) |

Exemplo

```javascript
var x = 5 ^ 1;
```

### Não (ou Negação) de Bits no JavaScript \(~\)

| Decimal | Binário |
|---------|-----------------------------------|
| 5       | 00000000000000000000000000000101 |
| ~5      | 11111111111111111111111111111010 (-6) |

Exemplo

```javascript
var x = ~5;
```

### Deslocamento para a Esquerda de Bits (com Preenchimento de Zeros) no JavaScript \(<<\)

Este é um deslocamento para a esquerda com preenchimento de zeros.
Um ou mais bits são "empurrados" da direita para a esquerda e os mais a
esquerda são descartados:

| Decimal | Binário |
|---------|--------------------------------------|
| 5       | 00000000000000000000000000000101 |
| 5 << 1  | 00000000000000000000000000001010 (10) |

Exemplo

```javascript
var x = 5 << 1;
```

### Deslocamento de Bits para a Direita \(com Conservação de Sinal\) noJavaScript \(>>\)

Este é um deslcamento para a direita com conservação de sinal.
Cópias do bits mais a esquerda (o mais significativo) são *empurradas* para a
direita e os bits mais a direita são descartados:

| Decimal  | Binário |
|----------|---------------------------------------|
| -5       | 11111111111111111111111111111011 |
| -5 >> 1  | 11111111111111111111111111111101 (-3) |

Exemplo

```javascript
var x = -5 >> 1;
```

### Deslocamento para a Direita (com Preenchimento de Zeros) no JavaScript \(>>>\)

Este é um deslocamento para a direita com preenchimento de zeros.
Um ou mais bits são *empurrados* para a direita, os mais a direita *caem fora*:

| Decimal  | Binário |
|----------|--------------------------------------|
| 5        | 00000000000000000000000000000101 |
| 5 >>> 1  | 00000000000000000000000000000010 (2) |

Exemplo

```javascript
var x = 5 >>> 1;
```

### Números Binários

Números binários com apenas um bit em 1 são fáceis de entender:

|  Representação Binária             |  Valor Decimal |
|------------------------------------|-----|
| 00000000000000000000000000000001  |  1 |
| 00000000000000000000000000000010  |  2 |
| 00000000000000000000000000000100  |  4 |
| 00000000000000000000000000001000  |  8 |
| 00000000000000000000000000010000  |  16 |
| 00000000000000000000000000100000  |  32 |
| 00000000000000000000000001000000  |  64 |

Colocando mais alguns bits em 1 revela os padrões binários:

|  Representação Binária             |  Valor Decimal |
|------------------------------------|---------------------|
| 00000000000000000000000000000101  |  5 \(4 + 1\) |
| 00000000000000000000000000001101  |  13 \(8 + 4 + 1\) |
| 00000000000000000000000000101101  |  45 \(32 + 8 + 4 + 1\) |

Números binários em JavaScript são armazenados no formato de complemento de dois.

Isto significa que um número negativo é a negação (inversão) de todos os bits
mais 1:

| Representação Binária             |  Valor Decimal |
|-----------------------------------|----------------|
| 00000000000000000000000000000101  |  5 |
| 11111111111111111111111111111011  |  -5 |
| 00000000000000000000000000000110  |  6 |
| 11111111111111111111111111111010  |  -6 |
| 00000000000000000000000000101000  |  40 |
| 11111111111111111111111111011000  |  -40 |

### Conersão de Decimal para Binário

Exemplo

```javascript
function dec2bin(dec){
  return (dec >>> 0).toString(2);
}
```

### Conversão Binário para Decimal

Exemplo

```javascript
function bin2dec(bin){
  return parseInt(bin, 2).toString(10);
}
```

## Expressões Regulares em JavaScript (https://www.w3schools.com/js/js_regexp.asp)

Uma expressão regular é uma sequência de caracteres que forma um padrão de busca.

O padrão de busca pode ser usado para busca textual e operações de substituição
de texto.

### o Que É uma Expressão regular?

Uma expressão regular é uma sequência de caracteres que formam um padrão de busca.

Quando você busca dados num texto, você usa um padrão de busca para descrever o
que você está buscando.

Uma expressão regular pode ter um único caracter, ou um padrão mais complicado.

Expressões regulares podem ser usadas para realizar todos os tipos de Operações
de busca e substituição de texto.

Syntax

```javascript
/padrão/modificadores;
```

Exemplo

```javascript
var patt = /pang/i;
```

Exemplo explicado:

**/pang/i**  é uma expressão regular.

**pang**  é um padrão \(a ser usado na busca\).

**i**  é um modificador \(modifica a busca para ignorar maiúsculas e minúsculas\).

### Uso de Métodos de String

No JavaScript, expressões regulares são frequentemente usadas com dois métodos
de strings: *search\(\)* e *replace\(\)*.

O método *search\(\)* usa uma expressão para buscar um casamento e retorna a
posição do casamento.

O método replace\(\) retorna uma string modificada onde o padrão é substituido.

#### Uso de search\(\) com uma String

O método *search\(\)* busca uma string com um certo valor e retorna a posição
onde a encontra:

Exemplo: Uso de uma string para procurar por "pang" numa string:

```javascript
var str = "Conheça as páginas do Pang!";
var n = str.search("Pang");
```

#### Uso do search\(\) Com uma Expressão Regular

Exemplo: Uso de uma expressão regular para fazer uma busca insensível a
maiúsculas  por "pang" numa string:

```javascript
var str = "Conheça as páginas do Pang!";
var n = str.search(/pang/i);
```

O resultado em *n* será:

  22

#### Uso do replace() Com uma String

O método replace\(\) substitui um dado valor por um outro numa string:

```javascript
var str = "Visite as páginas do Totó!";
var res = str.replace("Totó", "Pang");
```

#### Uso do replace() Com uma Expressão Regular

Exemplo: Uso de uma expressão regular insensível a maiúsculas para substituir
Totó por Pang numa string:

```javascript
var str = "Visite as páginas do Totó!";
var res = str.replace(/totó/i, "Pang");
```

The result in res will be:

  Visite as páginas do Pang!

#### Você reparou?

    Argumentos de expressões regulares (no lugar de argumentos de string)
    podem ser usadas nos métodos acima.
    Expressões regulares podem fazer suas buscas muito mais poderosas
    (insensibilidade a maiúsculas, por exemplo).

#### Modificadores de Expresão Regular

Modificadores podem ser usadas para fazer buscas insensíveis e globais:

| Modificador |  Descrição |
|-------------|-------------------------------------------------------|
| i        |  Faz um casamento insensível a maiúsculas |
| g        |  Faz um casamento global \(encontra todos os casamentos não parando no primeiro\) |
| m        |  Faz casamentos em múltiplas linhas |

### Padrões de Expressão Regular

Cochetes são usados para buscar uma faixa de caracteres:

| Expressão | Descrição |
|-----------|----------------------------------------------|
| [abc]      | Procure qualquer um dos caracteres que estão entre cochetes |
| [0-9]      | Procure por qualquer dígito no intervalo de 0 a 9 |
| (x\|y)     | Procure por qualquer uma das alternativas separadas por \| |

Metacaracteres são caracteres com um significado especial:

| Metacaracter | Descrição |
|--------------|---------------------------------------------------------------|
| \d            | Encontre um dígito |
| \s            | Encontre um caracter espaço (em branco) |
| \b            | Encontre um casamento no início ou fim de uma palavra |
| \uxxxx        | Encontre o caracter em Unicode especificado pelo número hexadecimal xxxx |

Quantificadores definem quantidades:

| Quantificador | Descrição |
|---------------|---------------------------------------------------------|
| n+         | Casa com qualquer string que contenha pelo menos um *n* |
| n*         | Casa com qualquer string que contenha zero ou mais ocorrências *n* |
| n?         | Casa com qualquer string que contenha zero ou uma ocorrência de *n* |

### Uso do Objeto RegExp

Em JavaScript, o objeto RegExp é um objeto de expressão regular com propriedades
e métodos pré-definidos.

#### Uso de test\(\)

O método test\(\) é um método de uma expressão RegExp.

Ele procura numa string um padrão e retorna true ou false, dependendo do resultado.

O exemplo a seguir busca numa o caracter "e":

Exemplo

```javascript
var patt = /e/;
patt.test("As melhores coisas da vida são gratuitas!");
```

Como há um "e" na string, saída do código acima será:

  true

Você não tem de colocar a expressão regular expression numa variável antes.
As duas linhas acima podem ser abreviadas numa:

```javascript
/e/.test("As melhores coisas da vida são gratuitas!");
```

#### Uso do exec\(\)

O método exec\(\) é um método de expressão expression.

Ele procura numa string um padrão especificado e retorna o texto encontrado como object.

Se nenhum casamento é encontrado, ele retorna o objeto \(null\).

A seguir temos um exemplo que busca numa string o caracter "e":

Exemplo

```javascript
/e/.exec("As melhores coisas da vida são gratuitas!");
```

## Erros no JavaScript - Lance e Tente Pegar [Throw and Try to Catch](https://www.w3schools.com/js/js_errors.asp)

A instrução **try** permite que você verifique se um bloco de códigos tem erros.

A instrução **catch** permite que você manipule \(processe\) o erro.

A instrução **throw** permite que você sinalize seus prórpios erros.

A instrução **finally** permite que você execute código, depois de tentar e
 pegar (*try* e *catch*), independente de se houve ou não erro.

### Erros Acontecem!

Ao executar código JavaScript, diferentes erros podem ocorrer.

Erros podem ser erro de codificação do programador, ou devidos a entradas
erradas ou coisas imprevistas.

Exemplo: Neste exemplo, escrevemos um alerta como adddlert para deliberadamente
produzir um erro: [Demo: try](try_demo1.html)

```javascript
<p id="demo"></p>

<script>
try {
  adddlert("Bem vindo, Amigo!");
}
catch(err) {
  document.getElementById("demo").innerHTML = err.message;
}
</script>
```

    JavaScript pega adddlert como um erro e executa o código do catch
    que processa o erro.

### try e catch do JavaScript

A instrução *try* permite que você defina um bloco de código que verifica se
erros ocorrem durante a execução.

A instrução *catch* permite permite que você defina um bloco de código para ser
executado se um erro ocorrer no bloco *try*.

As instruções **try** e **catch** de JavaScript estão sendo em pares:

```javascript
try {
  Bloco de código a tentar
}
catch(err) {
  Bloco de código que processa o erro
}
```

### JavaScript Lança Erros

Quando um erro ocorre, o JavaScript normalmente para a execução e gera uma
mensagem de erro.

O termo técnico para isto é: JavaScript lançará uma exceção \(throw an error\).

    JavaScript, na verdade, criará um objeto Error com duas propriedades:
    name (nome) e message (mensagem).

### A Instrução throw

A instrução *throw* permite que você crie seu próprio objeto de erro.

Tecnicamente, você pode lançar uma exceção (throw an error).

Uma exceção pode ser uma String, um Number, um Boolean ou um Object de JavaScript:

```javascript
throw "Muito grande";    // lança um texto
throw 500;          // lança um número
```

Se você usar *throw* junto com *try* e *catch*, você pode controlar o fluxo do
programa e gera mensagens de erro personalizadas.

### Exemplo de validação de Entrada

Este exemplo examina uma entrada. Se o valor estiver errado, uma exceção
\(err\) é lançada.

A exceção \(err\) é capturada pela instrução catch e uma menasagem de erro
personalizada é apresentada: [Demo: Valida Entrada](inVal_demo1.html)

```html
<!DOCTYPE html>
<html>
<body>

<p>Por favor, insira 5 e 10:</p>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">Teste de Entrada</button>
<p id="p01"></p>

<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "vazio";
    if(isNaN(x)) throw "não é um número";
    x = Number(x);
    if(x < 5) throw "muito pequeno";
    if(x > 10) throw "grande demais";
  }
  catch(err) {
    message.innerHTML = "A Entrada Foi " + err;
  }
}
</script>

</body>
</html>
```

### Validação de HTML

O código acima é apenas um exemplo.

Navegadores modernos, em geral, usam uma combinação de JavaScript e validação
embutida no HTML 5. O código HTML abaixo usa os atributos de HTML com regras
pré definidas de validação:

```html
<input id="demo" type="number" min="5" max="10" step="1">
```

### A Instrução finally

A instrução *finally* permite que você execute código, após o *try* e *catch*,
independente da existência ou não de erros:

Sintaxe

```javascript
try {
  Bloco de código a tentar
}
catch(err) {
  Bloco de código que processa erros
}
finally {
  Bloce de código que executa independente de ter ou não acontecido erro
}
```

Exemplo

```javascript
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "está vazio";
    if(isNaN(x)) throw "não é um número";
    x = Number(x);
    if(x > 10) throw "é muito grande";
    if(x < 5) throw "é muito pequeno";
  }
  catch(err) {
    message.innerHTML = "Erro: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}
```

### O Objeto Error

JavaScript tem um objeto interno *error* que fornece informações sobre o erro
quando um erro ocorre.

O objeto *error* provê duas propriedades úteiss: name e message.

#### Propriedades do Objeto Error

Property | Description
---------|------------------------------------------------------
name     | Sets or retorna an error name
message  | Sets or retorna an error message \(a string\)

#### Error Name Values

Six different values can be returned by the error name property:

Error Name     | Description
---------------|-----------------------------------------------
EvalError      | An error has occurred in the eval\(\) function
RangeError     | A number "out of range" has occurred
ReferenceError | An illegal reference has occurred
SyntaxError    | A syntax error has occurred
TypeError      | A type error has occurred
URIError       | An error in encodeURI\(\) has occurred

##### Eval Error

An EvalError indicates an error in the eval\(\) function.

Newer versions of JavaScript do not throw EvalError. Use SyntaxError instead.

##### Range Error

A RangeError is thrown if you use a number that is outside the range of legal values.

For example: You cannot set the number of significant digits of a number to 500.

```javascript
var num = 1;
try {
  num.toPrecision(500);   // A number cannot have 500 significant digits
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### A ReferenceError is thrown if you use \(reference\) a variable that has not been declared:

Exemplo

```javascript
var x;
try {
  x = y + 1;   // y cannot be referenced (used)
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### Syntax Error

A SyntaxError is thrown if you try to evaluate code with a syntax error.

Exemplo

```javascript
try {
  eval("alert('Hello)");   // Missing ' will produce an error
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### Type Error

A TypeError is thrown if you use a value that is outside the range of expected types:

Exemplo

```javascript
var num = 1;
try {
  num.toUpperCase();   // You cannot convert a number to upper case
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

##### URI \(Uniform Resource Identifier\) Error

A URIError is thrown if you use illegal characters in a URI function:

Exemplo

```javascript
try {
  decodeURI("%%%");   // You cannot URI decode percent signs
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}
```

### on-Standard Error Object Properties

Mozilla and Microsoft defines some non-standard error object properties:

fileName \(Mozilla\)
lineNumber \(Mozilla\)
columnNumber \(Mozilla\)
stack \(Mozilla\)
description \(Microsoft\)
number \(Microsoft\)

Do not use these properties in public web sites. They will not work in all browsers.

## JavaScript Scope (https://www.w3schools.com/js/js_scope.asp)

Scope determines the accessibility (visibility) of variables.

### JavaScript Function Scope

In JavaScript there are two types of scope:

  * Local scope
  * Global scope

JavaScript has function scope: Each function creates a new scope.

Scope determines the accessibility (visibility) of these variables.

Variables defined inside a function are not accessible (visible) from outside the function.

### Local JavaScript Variables

Variables declared within a JavaScript function, become **LOCAL** to the function.

Local variables have Function scope: They can only be accessed from within the function.

Exemplo

```javascript
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";

  // code here CAN use carName

}
```

Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.

### Global JavaScript Variables

A variable declared outside a function, becomes **GLOBAL**.

A global variable has global scope: All scripts and functions on a web page can access it.

Exemplo

```javascript
var carName = "Volvo";

// code here can use carName

function myFunction() {

  // code here can also use carName

}
```

### JavaScript Variables

In JavaScript, objects and functions are also variables.

    Scope determines the accessibility of variables, objects, and functions from different parts of the code.

### Automatically Global

If you assign a value to a variable that has not been declared, it will automatically become a **GLOBAL** variable.

This code example will declare a global variable carName, even if the value is assigned inside a function.

Exemplo

```javascript
myFunction();

// code here can use carName

function myFunction() {
  carName = "Volvo";
}
```

### Strict Mode

All modern browsers support running JavaScript in "Strict Mode".

You will learn more about how to use strict mode in a later section of this tutorial.

    Global variables are not created automatically in "Strict Mode".

### Global Variables in HTML

With JavaScript, the global scope is the complete JavaScript environment.

In HTML, the global scope is the window object. All global variables belong to the window object.

Exemplo

```javascript
var carName = "Volvo";

// code here can use window.carName
```

### Warning

    Do NOT create global variables unless you intend to.

    Your global variables (or functions) can overwrite window variables (or functions).
    Any function, including the window object, can overwrite your global variables and functions.

### The Lifetime of JavaScript Variables

The lifetime of a JavaScript variable starts when it is declared.

Local variables are deleted when the function is completed.

In a web browser, global variables are deleted when you close the browser window (or tab), but remain available to new pages loaded into the same window.

### Function Arguments

Function arguments (parameters) work as local variables inside functions.

## JavaScript Hoisting (https://www.w3schools.com/js/js_hoisting.asp)

Hoisting is JavaScript's default behavior of moving declarations to the top.

### JavaScript Declarations are Hoisted

In JavaScript, a variable can be declared after it has been used.

In other words; a variable can be used before it has been declared.

Exemplo 1 gives the same result as Exemplo 2:

Exemplo 1

```javascript
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element

var x; // Declare x
```

Exemplo 2

```javascript
var x; // Declare x
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element
```

To understand this, you have to understand the term "hoisting".

Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope \(to the top of the current script or the current function\).

### The **let** and **const** Keywords

Variables and constants declared with let or const are not hoisted!

### JavaScript Initializations are Not Hoisted

JavaScript only hoists declarations, not initializations.

Exemplo 1 does not give the same result as Exemplo 2:

Exemplo 1

```javascript
var x = 5; // Initialize x
var y = 7; // Initialize y

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y
```

Exemplo 2

```javascript
var x = 5; // Initialize x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

var y = 7; // Initialize y
```

Does it make sense that y is undefined in the last example?

This is because only the declaration (var y), not the initialization (=7) is hoisted to the top.

Because of hoisting, y has been declared before it is used, but because initializations are not hoisted, the value of y is undefined.

Exemplo 2 is the same as writing:

Exemplo

```javascript
var x = 5; // Initialize x
var y;     // Declare y

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

y = 7;    // Assign 7 to y
```

[Próxima unidade](intermediario1_js.md)
