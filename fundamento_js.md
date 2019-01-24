# Fundamentos de JavaScript

Este texto é baseado no [W3Schools javascript tutorial](https://www.w3schools.com/js/).

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

Exemplo: [Demo: JS no body](where_demo3.html)
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

## Saída do JS \([JS Output](https://www.w3schools.com/js/js_output.asp)\)

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

    Usar document.write() depois que um documento HTML foi carregado,
    irá apagar todo o conteúdo do documento HTML.
    O método document.write() deve ser usado apenas para testes.

Exemplo:  [Demo: document.write()](output_demo3.html)

#### Uso do window.alert\(\)

Exemplo: [Demo: window.alert\(\)](output_demo4.html)

```html
<script>
window.alert(5 + 6);
</script>
```

#### Uso do console.log\(\)

Para fins de depuração \(debugging\), você pode usar o método console.log\(\) para exibir dados.

Exemplo: [Demo: uso do console.log\(\)](output_demo5.html)

```html
<script>
console.log(5 + 6);
</script>
```

## Instruções de JavaScript \([JS statements](https://www.w3schools.com/js/js_statements.asp)\)

Exemplo: [Demo: programa JS num HTML](stmt_demo1.html)

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

A maioria dos programas em JavaScript são compostos por muitas instruções de  JavaScript.

As instruções são executadas, uma-a-uma, na mesma ordem em que elas estão escritas.

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
var            | Declara \(cria\) uma, ou várias variáveis

Por exemplo, a palavra-chave **var** diz para o navegador para criar variáveis:

```javascript
var x, y;
x = 5 + 6;
y = x * 10;
```

    Palavras-chaves em JavaScript são palavras reservadas.
    Palavras reservadas não podem ser usadas como nomes de variáveis.

## Sintaxe do JS \([JS Syntax](https://www.w3schools.com/js/js_syntax.asp)\)

### Valores em JavaScript

A sintaxe do JavaScript define dois tipos de valores: Valores fixos e valores variáveis.
Valores fixos são chamados de **literais**. Valores variáveis são chamados de **variáveis**.

#### Literais em JavaScript

**Números** são escritos com ou sem parte decimal \(valor depois da vírgula\):

```javascript
10.50

1001
```

    Observe que no lugar da vírgula para separar a parte decimal da parte inteira, JS usa . (ponto).

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

Em JavaScript, o primeiro caracter deve ser uma letra, um sublinhado \(\_\), ou um dolar \($\).

### JavaScript é Sensível à Diferença entre Maiúsculas e Minúsculas

Todos os identificadores de JavaScript diferenciam maiúsculas de minúsculas.

### JavaScript usa nomes em notação Camelo

A notação camelo é usada quando um identificador é composto por mais de uma palavra, neste caso, as palavras não podem ser separadas por um espaço \(o que caracterizaria dois identificadores e não um\). Na notação camelo, a primeira letra de cada palavra é escrita em maiúsculo e as outras em minúsculo.

Camelo com minúscula:

Programadores de JavaScript tendem a usar identificadores em notação camelo com a primeira letra da primeira palavra em minúsculo:

primeiroNome, ultimoNome, masterCard, interCidade, corFavorita.

### Conjunto de Caracteres do JavaScript

JavaScript usa o conjunto de caracteres Unicode. Veja [Referência UTF8 na W3Schools](https://www.w3schools.com/charsets/ref_html_utf8.asp) para uma referência mais completa sobre unicode.

## Comentários em JS \([JS Comments](https://www.w3schools.com/js/js_comments.asp)\)

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
  * Os nomes diferenciam maiúsculas de minúsculas \(a e A são variáveis diferentes\); e
  * Palavras reservadas não podem ser usadas como nomes de variáveis.

### O Operador de Atribuição

Em JavaScript, o sinal de igual \(=\) é um operador de *atribuição*, não um operador de igualdade.

    O operador de comparação "igual a" é escrito ==, ou === em JavaScript.
    O segundo comparador, só dar verdadeiro se o valor e o tipo dos operandos for igual.

### Tipos de Dados em JavaScript

Variáveis de JavaScript podem armazenar números, como 100, e texto, como "José da Silva".

Em programação, valores textuais são chamados de *strings*.

JavaScript pode trabalhar com vários tipos de dados, mas, por enquanto, só se preocupe com números e strings.

Strings são escritos entre aspas ou apóstrofes. Números são escritos diretamente. Números entre aspas são strings.

### Declarando \(Criando\) Variáveis JavaScript

A criação de uma variável em JavaScript é chamada de *declaração* de uma variável.

Você declara uma variável JavaScript com a palavra-chave **var**:

```javascript
var marcaCarro;
```

Depois da declaração, a variável não tem nenhum valor. \(Tecnicamente seu valor é **undefined**\)

    É uma boa prática de programação declarar todas as variáveis no início de um script.
    Um programa JavaScript é, frequentemente, chamado de script.

    Em JavaScript, a declaração das variáveis não é obrigatória, mas é fortemente recomendada.

### Uma Instrução, Muitas Variáveis

Inicie a instrução com **var** e separe as variáveis com vírgulas:

```javascript
var pessoa = "José da Silva", marcaCarro = "Volvo", preco = 200;
```

Uma declaração pode se espalhar por várias linhas:

```javascript
var pessoa = "José da Silva",
marcaCarro = "Volvo",
preco = 200;
```

### Valor = undefined

Uma variável declarada sem um valor terá o valor **undefined**.

### Redeclaração de Variáveis JavaScript

Se você redeclarar uma variável JavaScript, ela não perderá seu valor. [Redeclaração.](var_demo1.html)

### Aritmética no JavaScript

Como na álgebra, você pode fazer contas (aritmética) com as variáveis de JavaScript, usando operadores como + e \*:

```javascript
var x = 5 + 2 * 3;
```

Você também pode adicionar strings, mas as strings serão concatenadas:

```javascript
var x = "José" + " " + "Maria";
```

Tente isto também:

```javascript
var x = "5" + 2 + 3;
```

    Se você colocar aspas em torno de um número, ele será considerado um string
    e os próximos números da adição serão *convertidos* em strings, também.

Teste na Console para ver o resultado de:

```javascript
var x = 2 + 3 + "5";
```

## Operadores no JavaScript \([JS Operators](https://www.w3schools.com/js/js_operators.asp)\)

O operador de atribuição \(=\) atribui um valor a uma variável, isto é, o valor é armazenado na variável.

O operador de adição \(+\) adiciona números e concatena strings.

### Operadores Aritméticos em JavaScript

Operadores aritméticos são usados para realizar aritmética com números:

Operador  | Descrição
----------|-----------------------------------
\+        | Adição
\-        | Subtração
\*        | Multiplicação
\*\*      | Exponenciação (ES6)
/         | Divisão
%         | Módulo (Resto da Divisão)
++        | Incremento
--        | Decremento

### Operadores de atribuição do JavaScript

Operador | Exemplo | O mesmo que
---------|---------|------------
=        | x = y   | x = y
+=       | x += y  | x = x + y
-=       | x -= y  | x = x - y
\*=      | x \*= y | x = x * y
/=       | x /= y  | x = x / y
%=       | x %= y  | x = x % y

### Operadores de Strings no JavaScript

O operador + também pode ser usado para "adicionar" \(concatenar\) strings.

O operador de atribuição += pode ser usado para concatenar uma string com o valor atual de uma variável.

    Se você adicionar um número a uma string, o resultado é uma string!

### Operadores de Comparação em JavaScript

Operador | Descrição
---------|------------------------------------
==       | Igual a
===      | valor igual e tipo igual
!=       | diferente
!==      | valor diferente ou tipo diferente
\>       | maior que
<        | menor que
\>=      | maior ou igual a
<=       | menor ou igual a
?        | operador ternário

## Operadores Lógicos em JavaScript

Operador | Descrição
---------|--------------------
&&       | e lógico
\|\|     | ou lógico
!        | negação lógica

### Operadores de Tipo do JavaScript

Operador   | Descrição
-----------|-------------------------------------------------
typeof     | Returna uma string com o tipo do valor na variável
instanceof | Returna true \(verdadeiro\) se um objeto é uma instância de um tipo de objeto

### Operadores de Bits no JavaScript

Os números em JavaScript são representado por pontos flutuantes, mas quando estas operações são realizadas, os valores em ponto flutuante são convertidos para inteiros de 32 bits antes da operação bit-a-bit. Depois da operação, o número é reconvertido para ponto flutuante.

Operador | Descrição   | Exemplo   | O mesmo que | Resultado | Decimal
---------|-------------|-----------|-------------|-----------|----------
&        | E           | 5 & 1     | 0101 & 0001 | 0001   | 1
\|       | OU          | 5 \| 1    | 0101 \| 0001 | 0101   | 5
~        | NÃO         | ~ 5       | ~0101       | 1010   | 10
^        | XOU         | 5 ^ 1     | 0101 ^ 0001 | 0100 | 4
<<       | Deslocamento para a esquerda | 5 << 1 | 0101 << 1 | 1010 | 10
\>>      | Deslocamento para a direta com sinal | 5 >> 1 | 0101 >> 1 | 0010 | 2
\>>>     | Deslocamento para a direita com zeros | 5 >>> 1 | 0101 >>> 1 | 0010 | 2

### Operações Aritméticas

Um operação aritmética opera tipicamente em dois números.

Os dois números podem ser literais ou valores de variáveis:

```javascript
var a = 6;
var x = 100 + 50;
var y = (100 + 50) * a;
```

### Operadores e Operandos

Os números \(numa operação aritmética\) são chamados de **operandos**.

A operação \(a ser realizada entre os dois operandos\) é definida por um **operador**.

Operando | Operador | Operando
--------|----------|---------
100     | +        | 50

    Em aritmética, a divisão de dois inteiros produz um quociente e um resto.
    Em matemática, o resultado de uma operação módulo é o resto da divisão aritmética.

### Precedência de Operadores

A precedência de operadores descreve a ordem em que as operações são realizadas numa expressão aritmética.

```javascript
var x = 100 + 50 * 3;
```

Multiplicação (\*) e divisão (/) têm precedência maior do que adição (+) e subtração (-).

E (como nas aulas de matemática) a precedência muda com o uso de parenteses:

```javascript
var x = (100 + 50) * 3;
```

Quando muitas operações têm a mesma precedência (como adição e subtração), elas são calculadas da esquerda para a direita:

```javascript
var x = 100 + 50 - 3;
```

### Valores de Precedência dos Operadores em JavaScript

Valor | Operador    | Descrição                 | Exemplo
------|-------------|---------------------------|-------------
20    | \( \)       | Agrupamento de Expressão  | \(3 + 4\)
  |   |   |  
19    | .           | Membro                    | pessoa.nome
19    | \[\]        | Membro                    | pessoa\["nome"\]
19    | \(\)        | Chamada de função         | myFunction\(\)
19    | new         | Criação                   | new Date()
  |   |   |  
17    | ++          | Incremento pós-fixado     | i++
17    | --          | Decremento pós-fixado     | i--
  |   |   |  
16    | ++          | Incremento pré-fixado     | ++i
16    | --          | Decremento pré-fixado     | --i
16    | !           | Negação lógica            | !\(x==y\)
16    | typeof      | Tipo                      | typeof x
  |   |   |  
15    | \*\*        | Exponenciação (ES7)       | 10 \*\* 2
  |   |   |  
14    | \*          | Multiplicação             | 10 \* 5
14    | /           | Divisão                   | 10 / 5
14    | %           | Resto da divisão          | 10 % 5
  |   |   |  
13    | +           | Adição                    | 10 + 5
13    | -           | Subtração                 | 10 - 5
  |   |   |  
12    | <<          | Deslocamento esquerda     | x << 2
12    | \>\>        | Deslocamento direita      | x \>\> 2
12    | \>\>\>      | Deslocamento direita (sem sinal)    | x \>\>\> 2
  |   |   |  
11    | <           | Menor que                 | x < y
11    | <=          | Menor ou igual a          | x <= y
11    | \>          | Maior que                 | x \> y
11    | \>=         | Maior ou igual a          | x \>= y
11    | in          | Propriedade do Objeto     | "PI" in Math
11    | instanceof  | Instância do Objeto       | instanceof Array
  |   |   |  
10    | ==          | Igual a                   | x == y
10    | ===         | Igual estrito             | x === y
10    | !=          | Diferente                 | x != y
10    | !==         | Diferente estrito         | x !== y
  |   |   |  
9     | &           | E bit-a-bit               | x & y
8     | ^           | XOU bit-a-bit             | x ^ y
7     | \|          | OU bit-a-bit              | x \| y
6     | &&          | E lógico                  | x && y
5     | \|\|        | OU lógico                 | x \|\| y
4     | ? :         | Condição                  | \(x == y\) ? "Sim" : "Não"
  |   |  |
3     | +=          | Atribuição                | x += y
3     | +=          | Atribuição                | x += y
3     | -=          | Atribuição                | x -= y
3     | \*=         | Atribuição                | x \*= y
3     | %=          | Atribuição                | x %= y
3     | <<=         | Atribuição                | x <<= y
3     | \>\>=       | Atribuição                | x \>\>= y
3     | \>\>\>=     | Atribuição                | x \>\>\>= y
3     | &=          | Atribuição                | x &= y
3     | ^=          | Atribuição                | x ^= y
3     | \|=         | Atribuição                | x \|= y
   |  |   |
2     | yield       | Função Pausa              | yield x
1     | ,           | Vírgula                   | 5 , 6

    Expressões em parenteses são totalmente calculadas antes do valor ser usado
    no restante da expressão.

## Atribuições em JavaScript [JS Assignment](https://www.w3schools.com/js/js_assignment.asp)

Operadores de atribuição atribuem valores a variáveis de JavaScript.

Operador | Exemplo  | Mesmo que
---------|----------|--------------------
=        | x = y    | x = y
+=       | x += y   | x = x + y
-=       | x -= y   | x = x - y
\*=      | x \*= y   | x = x \* y
/=       | x /= y   | x = x / y
%=       | x %= y   | x = x % y
<<=      | x <<= y  | x = x << y
\>\>=    | x \>>= y  | x = x >> y
\>\>\>=  | x \>\>\>= y | x = x \>\>\> y
&=       | x &= y   | x = x & y
^=       | x ^= y   | x = x ^ y
\|=      | x \|= y  | x = x \| y
\*\*=    | x \*\*= y  | x = x \*\* y

[Continuação do texto](fundamentos2_js.md)
