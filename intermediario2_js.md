# Fundamentos VII de JavaScript

Esta é a continuação de [Fundamentos VI de JS](intermediario1_js.md).

## [Debug em JavaScript](https://www.w3schools.com/js/js_debugging.asp)

Erros \(*bugs*\) podem \(vão\) acontecer, sempre que você escrever algum
código novo de computador.

### *Debug* de Código

*Bug* é como em computação são chamados os erros de código. *Debug* é retirar
os erros dos programas. Muitas vezes, *debug* é traduzido por depuração.
Códigos de programas podem ter erros de sintaxe ou erros lógicos.

Muitos destes erros são difíceis de diagnosticar.

Frequentemente, quando um código de programação possui erros, nada acontece.
Não há mensagens de erro e você não tem nenhuma indicação de onde procurar
os erros.

Procurar e consertar os erros no código dos programas é chamado de
*debugar* (depurar) os programas.

### *Debuggers* de JavaScript

Debugar não é fácil. Felizmente, todos os navegadores modernos possuem
um *debugger* \(depurador, ou "debugador"\) embutido.

*Debuggers* embutidos podem ser ligados ou desligados para relatar os erros
para os usuários.

Com um *debugger*, você também pode colocar *breakpoints* \(lugares no
  código em que a execução deve ser parada\) e examinar as variáveis enquanto
o programa está executando.

Normalmente, você ativa o *debugging* \(depuração\) no seu navegador com
a tecla <kbd>F12</kbd> e seleciona a aba de *Console* no menu do debugger.

### O Método `console.log()`

Se seu navegador suporta a depuração, você pode usar `console.log()` para
mostrar os valores de JavaScript na janela de depuração:

Exemplo

```html
<!DOCTYPE html>
<html>
<body>

<h1>Minha Primeira Página WEB</h1>

<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>

</body>
</html>
```

### Colocação de *Breakpoints*

Na janela do *debugger*, você pode colocar *breakpoints* no código JavaScript.

Em cada *breakpoint*, o JavaScript parará a execução e o *debugger* permite
que você examine o valor das variáveis e calcule outros valores.

Depois de examinar os valores, você pode prosseguir a execução do código
\(tipicamente com um botão de *play*\).

### A Palavra-Chave `debugger`

A palavra-chave `debugger` para a execução do JavaScript e chama \(se
  estiver disponível\) a função de depuração.

Isto tem o mesmo efeito que colocar um *breakpoint* no *debugger*.

Se nenhuma depuração estiver disponível, a instrução `debugger` não
tem efeito.

Com o *debugger* ligado, o código abaixo para a execução antes de executar a
terceira linha.

Exemplo

```javascript
var x = 15 * 5;
debugger;
document.getElementById("demo").innerHTML = x;
```

### Ferramentas de *Debugging* dos Principais Navegadores

Normalmente, você ativa a depuração no navegador com <kbd>F12</kbd> e
seleciona a aba *Console* no menu do *debugger*.

Se não, siga as seguintes instruções:

#### Chrome
  1. Rode o navegador.
  2. Do menu, selecione "Outras Ferramentas".
  3. Das Ferramentas, escolha "Ferramentas de Desenvolvimento".
  4. Enfim, selecione "Console".

#### Firefox
  1. Rode o  navegador.
  2. Do menu, selecione "Desenvolvedor Web".
  3. Enfim, selecione "Console Web".

#### Edge
  1. Rode o  navegador.
  2. Do menu, selecione "Ferramentas Desenvolvedor".
  3. Enfim, selecione "Console".

#### Opera
  1. Rode o  navegador.
  2. Do menu, selecione "Desenvolvedor".
  3. De "Desenvolvedor", selecione "Ferramentas Desenvolvedor".
  4. Enfim, selecione "Console".

#### Safari
  1. Vá ao Safari, Preferências, Avançado no menu principal.
  2. Marque "Enable Show Develop menu in menu bar".
  3. Quando a nova opção "Develop" aparecer no menu:
  4. Escolha "Show Error Console".

## Guia de Estilo e [Convenções de Codificação](https://www.w3schools.com/js/js_conventions.asp) de JavaScript

Sempre use as mesmas convenções de codificação para todos os seus projetos
de JavaScript.

### Convenções de Codificação de JavaScript

Convenções de codificação são recomendações de estilo para a programação.
Elas, em geral, cobrem:

  * Regras para a formação de nomes e declaração de variáveis e funções.
  * Regras para o uso de espaços, indentação \(tabulação\) e comentários.
  * Práticas e princípios de programação.

Convenções de codificação asseguram a qualidade:

  * Melhora a legibilidade do código.
  * Torna a manutenção do código mais fácil.

Convenções de codificação podem ser regras documentadas para equipes seguirem,
ou serem apenas a prática de codificação individual do programador.

    Esta seção descreve convenções de codificação de JavaScript usadas
    frequentemente.
    Leia também a próxima seção "Melhores Práticas" e aprenda a evitar
    armadilhas de programação.

### Nomes de Variáveis

Use a *notação camelo* para os nomes dos identificadores \(para variáveis e
  funções\). Na *notação camelo*, quando um identificador é composto por
  várias palavras, as palavras são colocadas juntas, a primeira letra de cada
  palavra é escrita em maiúsculo e as outras em minúsculas \(a não ser que
  seja uma abreviação, ou sigla, quando todas as letras permanecem maiúculas\).

Todos os nomes começam com uma letra minúscula \(a não ser que o
identificador seja o nome de uma classe\).

```javascript
nome = "José";
nomeDoMeio = "Antônio";
sobrenome = "da Silva";

preco = 19.90;
imposto = 0.20;

precoCheio = preco + (preco * imposto);
```

### Espaços em Volta dos Operadores

Sempre coloque espaços em volta dos operadores \( = + - * / \)
e depois de vírgulas:

Exemplos:

```javascript
var x = y + z;
var valores = ["Volvo", "Saab", "Fiat"];
```

### Indentação de Códigos

Sempre use 2 espaços para a indentação de blocos de códigos:

Funções:
```javascript
// função para converter graus Fahrenheit em graus Celsius
function paraCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}
```

    Não use tabs \(tabuladores\) para indentação.
    Diferentes editores interpretam tabs diferentemente.

### Regras para Instruções

Regras gerais para instruções simples:

Sempre termine uma instrução com ponto-e-vírgula \(;\).

Exemplos

```javascript
var valores = ["Volvo", "Saab", "Fiat"];  // array

var pessoa = {  // objeto
  nome: "José",
  sobrenome: "da Silva",
  idade: 50,
  corDosOlhos: "azul"
};
```

Regras gerais para instruções complexas \(compostas\):

  * Abra chave no fim da primeira linha;
  * Coloque um espaço antes de abrir chave;
  * Feche chave numa linha nova, retirando indentação do bloco e
  * Não termine uma instrução complexa com ponto-e-vírgula.

Funções:
```javascript
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}
```

*Loops*:
```javascript
for (i = 0; i < 5; i++) {
  x += i;
}
```

Condicionais:
```javascript
if (hora < 12) {
  saudacao = "Bom dia";
} else if (hora < 18) {
  sudacao = "Boa tarde";
} else {
  saudacao = "Boa noite";
}
```

### Regras para Objetos

Regras gerais para a definição de objetos:

  * Abra chave \(\{\) na mesma linha do nome do objeto;
  * Use dois pontos \(:\) mais espaço entre cada propriedade e seu valor;
  * Use aspas \(\"\) em volta de valores de strings, não em volta de
    valores numéricos;
  * Não adicione uma vírgula após o último par propriedade-valor;
  * Feche chave \(\}\) numa nova linha, retirando uma indentação e
  * Sempre termine uma definição de objeto com ponto-e-vírgula.

Exemplo

```javascript
var pessoa = {
  nome: "José",
  sobrenome: "da Silva",
  idade: 50,
  corDosOlhos: "azul"
};
```

Objetos curtos podem ser escritos comprimidos, numa linha, use espaços
apenas entre as propriedades, assim:

```javascript
var pessoa = {nome:"José", sobrenome:"da Silva", idade:50, corDosOlhos:"azul"};
```

### Comprimento de Linha < 80

Para legibilidade, evite linhas mais longas do que 80 caracteres.

Se uma instrução JavaScript não cabe numa linha, o melhor lugar para quebrá-la
é depois de um operador ou de uma vírgula.

Exemplo

```javascript
document.getElementById("demo").innerHTML =
"Alô, Teresinha!";
```

### Convenções para Nomes

Sempre use a convenção de nomes para todos os seus códigos. Por exemplo:

  * Nomes de variáveis e funções escritas em *notação camelo*
  * Variáveis globais em letras maiúsculas
  * Constantes \(como PI\) em maiúsculas

Observe que existe constantemente uma discussão sobre como escrever
identificadores compostos de várias palavras:

  - programadores Lisp usam hífens, atributos em HTML e CSS, também;
  - programadores C/C++, PHP, Pearl e SQL usam sublinhado \(\_\) e
  - programadores Java usam a *notação camelo*.

#### Hífens em HTML e CSS

Atributos em HTML5 podem começar com *data-* \(data-quantity, data-price\).

CSS usa hífens nos nomes-de-propriedades \(font-size\).

> Hífens podem ser confundidas com tentativas de substração.
> Hífens não são permitidos nos nomes de JavaScript.

#### Sublinhados

Muitos programadores preferem usar sublinhados \(data_de_nascimento\),
especialmente em bancos de dados SQL e na programação em linguagem C.

Sublinhados são frequentemente usados na documentação de PHP.

#### CamelCase \(notação camelo\):

Notação camelo é usada pelo próprio JavaScript, pelo jQuery e outras
bibliotecas de JavaScript. Nela, os identificadores compostos por vários nomes
cada nome começa em maiúsculo \(com a possível exceção do primeiro nome que deve
  ser em maiúsculo apenas se o identificador for o nome de uma classe\).

> Não comece nomes com o sinal de dollar \(\$\).
> Você entrará em conflito com muitos nomes de bibliotecas do JavaScript.

### Carregamento do JavaScript no HTML

Use sintaxe simples para carregar *scripts* externos \(o atributo tipo
  não é necessário\):

```html
<script src="meuscript.js"></script>
```

> Observe que nem sempre usamos a notação camelo para nome de arquivo.

### Acesso aos Elementos de HTML

Uma consequência do uso de estilos HTML "desarrumados" é provocar
erros no JavaScript.

Estas duas instruções de JavaScript vão produzir resultados diferentes:

```javascript
var obj = getElementById("Demo")

var obj = getElementById("demo")
```

Se possível, use as mesmas convenções de formação de nomes \(como no
  JavaScript\) em HTML.

### Extensões de Arquivos

Arquivos HTML devem ter uma extensão **.html** \(não **.htm**\).

Arquivos CSS devem ter uma extensão **.css**.

Arquivos JavaScript devem ter uma extensão **.js**.

### Use Nomes de Arquivos com Minúsculas

A maioria dos servidores de WEB \(Apache, Unix\) diferenciam maiúsculas
e minúsculas nos nomes dos arquivos:

`london.jpg` não pode ser acessado como `London.jpg`.

Alguns servidores WEB \(Microsoft, IIS\) não diferenciam as caixas:

`london.jpg` pode ser acessado como `London.jpg` ou `london.jpg`.

Se você misturar maiúsculas com minúsculas, num servidor sensível à caixa,
você tem ser muito consistente.

Se você mudar de um servidor insensível à caixa para um sensível, pequenos
erros podem quebrar seu site WEB.

Para evitar estes problemas, sempre use nomes de arquivos em minúsculas.

### Desempenho

Convenções de codificação não são usadas pelos computadores. A maioria
das regras têm pouco impacto na execução dos programas.

Indentação e espaços extras não são significantes em *scripts* pequenos.

Para o desenvolvimento de código, a legibilidade deve ser sempre preferida.
Grandes *scripts* em produção devem ser minimizados.

## Melhores [Práticas de JavaScript](https://www.w3schools.com/js/js_best_practices.asp)

Evite *variáveis globais*, evite `new`, evite `==`, evite `eval()`.

### Evite Variáveis globais

Minimize o uso de variáveis globais.

Isto vale para todos os tipos de dados, objetos e funções.

Variáveis e funções globais podem ser sobreescritas por outros scripts.

Use variáveis locais e aprenda a usar fechamentos \(*closures*\).

### Sempre Declare Variáveis Locais

Todas as variáveis usadas numa função devem ser declaradas como variáveis
locais.

Variáveis locais devem ser declaradas com a palavra-chave `var`, senão elas
se tornam globais.

O modo *strict* não permite variáveis não declaradas, procure usá-lo.

### Declarações no Topo

É uma boa prática de programação coloxar todas as declarações no topo de cada
script ou função.

  * Permite ter um código mais claro
  * Fornece um único lugar para procurar pelas variáveis locais
  * Torna mais fácil evitar variáveis globais indesejadas \(implícitas\)
  * Reduz a possibilidade de re-declarações acidentais

```javascript
// Declare no início
var nome, sobrenome, preco, desconto, precoCheio;

// Use depois
nome = "José";
sobrenome = "da Silva";

preco = 19.90;
desconto = 0.10;

precoCheio = preco / (1 - desconto / 100);
```

Isto também vale para variáveis de malhas:

```javascript
// Declare no inicio
var i;

// Use depois
for (i = 0; i < 5; i++) {
  // ...
}
```

> O JavaScript move todas as declarações para o topo \(Promoção do JavaScript\).

### Inicialize as Variáveis

É uma boa prática, inicializar as variáveis quando você as declara.

  * Resulta num código mais claro
  * Fornece um único lugar para inicializar as variáveis
  * Evita valores indefinidos

```javascript
// Declare e inicialize no começo
var nome = "",
sobrenome = "",
preco = 0,
desconto = 0,
precoCheio = 0,
meuArray = [],
meuObjeto = {};
```

> Inicializar as variáveis fornece uma ideia do uso pretendido \(e o tipo de
dado pretendido\).

### Nunca Declare Objeto Número, String ou Booleano

Sempre trate números, strings ou booleanos como valores primitivos.
Não como objetos.

Declarar estes tipos como objetos, reduz a velocidade do processamento e
produz efeitos colaterais desagradáveis.

Exemplo

```javascript
var x = "José";             
var y = new String("José");
(x === y) // é false porque x é uma string e y é um objeto.
```

Ou pior ainda:

Exemplo
```javascript
var x = new String("José");             
var y = new String("José");
(x == y) // é false porque você não pode comparar objetos.
```

#### Não Use `new Object()`

  * Use `{}` no lugar de `new Object()`
  * Use `""` no lugar de `new String()`
  * Use `0` no lugar de `new Number()`
  * Use `false` no lugar de `new Boolean()`
  * Use `[]` no lugar de `new Array()`
  * Use `/()/` no lugar de `new RegExp()`
  * Use `function (){}` no lugar de `new Function()`

Exemplo

```javascript
var x1 = {};           // novo objeto
var x2 = "";           // nova string primitiva
var x3 = 0;            // novo número primitivo
var x4 = false;        // novo booleano primitivo
var x5 = [];           // novo objeto array
var x6 = /()/;         // novo objeto regexp
var x7 = function(){}; // novo objeto função
```

### Cuidado com Conversões Automáticas de Tipos

Cuidado, números podem ser automaticamente convertidos para *strings* ou
NaN \(*Not a Number*\).

JavaScript é fracamente tipado. Uma variável pode conter diferentes tipos
de dados e uma variável pode trocar o seu tipo de dado:

Exemplo

```javascript
var x = "Alo";     // typeof x é uma string
x = 5;             // muda typeof x para um número
```

Ao fazer operações matemáticas, JavaScript pode converter números em *strings*:

Exemplo

```javascript
var x = 5 + 7;       // x.valueOf() é 12,  typeof x é um número
var x = 5 + "7";     // x.valueOf() é 57,  typeof x é uma string
var x = "5" + 7;     // x.valueOf() é 57,  typeof x é uma string
var x = 5 - 7;       // x.valueOf() é -2,  typeof x é um número
var x = 5 - "7";     // x.valueOf() é -2,  typeof x é um número
var x = "5" - 7;     // x.valueOf() é -2,  typeof x é um número
var x = 5 - "x";     // x.valueOf() é NaN, typeof x é um número
```

> Substrair uma string de uma string não gera um *erro*, mas retorna `NaN`

Exemplo

```javascript
"Alo" - "Terezinha"    // retorna NaN
```

### Use a Comparação com `===`

O operador de comparação `==` sempre converte antes da comparação \(para tipos
  iguais\).

O operador `===` força a comparação de tipo e valor:

Exemplo

```javascript
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```

### Use Parâmetros com Valor Padrão \(*Defaults*\)

Se uma função é chamada com um argumento ausente, o valor do argumento ausente
é colocado como `undefined`.

Valores não definidos \(*undefined*\) podem quebrar o seu código. É um hábito
bom atribuir valores padrões \(*defaults*\) aos argumentos.

Exemplo

```javascript
function myFunction(x, y) {
  if (y === undefined) {
    y = 0;
  }
}
```

ECMAScript 2015 permite definir parâmetros com valores padrões para as chamadas
das funções:

```javascript
function (a=1, b=1) {
  // código da function
}
```

### Termine Seus `switch`es com `default`

Sempre termine seus `switch` com um `default`. Mesmo que você ache que não
precisa dele.

Exemplo

```javascript
switch (new Date().getDay()) {
  case 0:
    dia = "Domingo";
    break;
  case 1:
    dia = "Segunda-feira";
    break;
  case 2:
    dia = "Terça-feira";
    break;
  case 3:
    dia = "Quarta-feira";
    break;
  case 4:
    dia = "Quinta-feira";
    break;
  case 5:
    dia = "Sexta-feira";
    break;
  case 6:
    dia = "Sábado";
    break;
  default:
    dia = "Desconhecido";
}
```

### Evite Usar `eval()`

A função `eval()` é usada para executar texto como código. Em quase todos os
casos, não deve ser necessário usá-la, a menos que você esteja escrevendo um
interpretador.

Ela permite que qualquer código seja executado e isto pode ser um risco à
segurança.

## [Erros Comuns em JavaScript](https://www.w3schools.com/js/js_mistakes.asp)

### Uso Acidental do Operador de Atribuição

Programas em JavaScript, ou em qualquer linguagem, pode gerar resultados
inesperados se um programador usa acidentalmente um operador de atribuição
\(`=`\), no lugar de um operador de comparação \(`==`\) numa condição.

A condição do `if` abaixo vale `false` \(como esperado\) porque `x` não é
igual a `10`:

```javascript
var x = 0;
if (x == 10)
```

A condição da instrução `if` vale `true` \(ao contrário do esperado), porque
`10` é `true`:

```javascript
var x = 0;
if (x = 10)
```

A condição da instrução `if` abaixo vale `false` \(ao contrário do que se
espera\), porque `0` é `false`:

```javascript
var x = 0;
if (x = 0)
```

Uma atribuição sempre volta o valor da atribuição, isto é, o valor da expressão
a direita da atribuição.

### Expectativa de Comparação Fraca

Numa comparação normal, o tipo do dado *nao importa*. A condição da instrução
`if` abaixo vale `true`:

```javascript
var x = 10;
var y = "10";
if (x == y)
```

Numa comparação estrita, o tipo do dado *importa*.  A condição da instrução
`if` abaixo vale `false`:

```javascript
var x = 10;
var y = "10";
if (x === y)
```

Um erro comum é esquecer que os `case` da instrução `switch` usam a
comparação estrita:

O `switch` abaixo vai mostrar um alerta:

```javascript
var x = 10;
switch(x) {
  case 10: alert("Alo");
}
```

O `switch` abaixo não vai mostrar o alerta:

```javascript
var x = 10;
switch(x) {
  case "10": alert("Alo");
}
```

### Confusão com Adição e Concatenação

Adição soma *números*.

Concatenação junta *strings*.

No JavaScript ambas operações usam o mesmo operador `+`.

Por causa disto, adicionar um número como um número pode resultar em algo
diferente de adicionar um número como *string*:

```javascript
var x = 10 + 5;          // o resultado em x é 15
var x = 10 + "5";        // o resultado em x é "105"
```

Ao adicionar duas variáveis, é difícil de prever o resultado:

```javascript
var x = 10;
var y = 5;
var z = x + y;           // o resultado em z é 15

var x = 10;
var y = "5";
var z = x + y;           // o resultado em z é "105"
```

### Má Compreensão de *Floats*

Todos os números em JavaScript são armazenados como números de ponto flutuante
de 64-bits \(*Floats*, ou *doubles*\).

Todas as linguagens de programação, inclusive o JavaScript, têm problemas
com valores exatos de ponto flutuante:

```javascript
var x = 0.1;
var y = 0.2;
var z = x + y            // O resultado em z não é 0.3
```

Para resolver o problema acima, ajuda, multiplicar e dividir:

Exemplo

```javascript
var z = (x * 10 + y * 10) / 10;       // z é 0.3
```

### Quebra de *String* em JavaScript

JavaScript permite que você quebre uma instrução em duas linhas:

Exemplo 1

```javascript
var x =
"Hello World!";
```

Mas, quebrar uma instrução no meio de uma *string* não funciona:

Exemplo 2

```javascript
var x = "Hello
World!";
```

Você precisa usar uma barra invertida \(`\`\) se quiser quebrar uma *string*
numa instrução:

Exemplo 3

```javascript
var x = "Hello \
World!";
```

### Erro de Colocação de Ponto-e-vírgula

Devido a um ponto-e-vírgula mal colocado, o código abaixo vai executar
independente do valor de x:

```javascript
if (x == 19);
{
  // bloco de código  
}
```

### Quebra de uma Instrução `return`

O comportamento padrão de JavaScript é terminar automaticamente uma instrução
no final de uma linha.

Por causa disto, os dois exemplos a seguir são equivalentes:

Exemplo 1
```javascript
function minhaFuncao(a) {
  var potencia = 10  
  return a * potencia
}
```

Exemplo 2
```javascript
function minhaFuncao(a) {
  var potencia = 10;
  return a * potencia;
}
```

O JavaScript também permite que você quebre uma instrução em duas linhas.

Por causa disto, o exemplo 3 também resulta no msmo que os anteriores:

Exemplo 3
```javascript
function mnhaFuncao(a) {
  var
  potencia = 10;  
  return a * potencia;
}
```

Mas, o que acontece se você quebrar a instrução `return` em duas linhas?

Exemplo 4
```javascript
function minhaFuncao(a) {
  var
  potencia = 10;  
  return
  a * potencia;
}
```

A função retorna o valor `undefined`!

Por que? Porque o JavaScript pensou que você queria dizer:

Exemplo 5
```javascript
function minhaFuncao(a) {
  var
  potencia = 10;  
  return;
  a * potencia;
}
```

#### Explicação

Se uma instrução está incompleta como em:

```javascript
var
```

O JavaScript tentará completá-la com a próxima linha:

```javascript
potencia = 10;
```

Mas, como a instrução está completa:

```javascript
return
```

O JavaScript automaticamente a termina como se tivesse sido escrito:

```javascript
return;
```

Isto ocorre porque a finalização das instruções com ponto-e-vírgula é opcional
em JavaScript.

O JavaScript terminará a instrução de `return` no fim da linha porque ela é
uma instrução completa.

> **Nunca quebre** uma instrução `return`.

### Acesso de *Arrays* com *Strings* como Índice

Muitas linguagens de programação possuem suporte para índices de *arrays* com
nomes.

*Arrays* com *strings* como índice são chamados de *arrays associativos*, ou mapas
associativos, ou dicionários, \(ou *hashes*\).

O JavaScript não dá suporte a *arrays* com nomes como índice.

No JavaScript, *arrays* usam números inteiros como índice:  

Exemplo:

```javascript
var pessoa = [];
pessoa[0] = "João";
pessoa[1] = "da Silva";
pessoa[2] = 46;
var x = pessoa.length;       // pessoa.length volta 3
var y = pessoa[0];           // pessoa[0] volta "João"
```

No JavaScript, objetos usam índices com nomes.

Se você usar um índice com nome, ao acessar um *array*, o JavaScript redefinirá
o *array* como um objeto padrão.

Depois da redefinição automática, os métodos e propriedades de *array* na
variável resultarão em valores `undefined` ou incorretos.

Exemplo:

```javascript
var pessoa = [];
pessoa["nome"] = "João";
pessoa["sobrenome"] = "da Silva";
pessoa["idade"] = 46;
var x = pessoa.length;      // pessoa.length retorna 0
var y = pessoa[0];          // pessoa[0] retorna undefined
```

### Término de Definições com Vírgula

Vírgulas no final da definição de um objeto são permitidas no ECMAScript 5.

Exemplo de Objeto:

```javascript
pessoa = {nome:"João", sobrenome:"da Silva", idade:46,}
```

Exemplo de *Array*:

```javascript
pontos = [40, 100, 1, 5, 25, 10,];
```

ALERTA !!

> Não funciona no Internet Explorer 8.

> JSON não permite vírgulas no final.

JSON:

```javascript
pessoa = {"nome":"João", "sobrenome":"da Silva", "idade":46}
```

JSON:
```javascript
pontos = [40, 100, 1, 5, 25, 10];
```

### `undefined` **Não É** `null`

Os objetos, as variáveis, as propriedades e os métodos em JavaScript podem
ser `undefined`.

Além disso, os objetos vazios de JavaScript podem ter valor `null`.

Isto torna um pouco difícil testar para saber se um objeto está vazio.

Você pode testar se um objeto existe testando se o tipo é `undefined`:

Exemplo:

```javascript
if (typeof meuObj === "undefined")
```

Mas, você não pode testar se um objeto é `null`, porque isto vai lançar um
*error* se o objeto é `undefined`:

Incorreto:
```javascript
if (myObj === null)
```

Para resolver este problema, você deve testar se um objeto não é `null`, nem
`undefined`.

Mas, isto ainda pode lançar um `error`:

Incorreto:
```javascript
if (meuObj !== null && typeof meuObj !== "undefined")
```

Porque você deve testar antes se é `undefined` e só depois se é `null`:

Correto:
```javascript
if (typeof meuObj !== "undefined" && meuObj !== null)
```

### Escopo no Nível de Bloco

JavaScript não cria um novo escopo para cada bloco de código.

Isto acontece com muitas linguagens, mas não com o JavaScript.

O código abaixo vai mostrar o valor de \(10\), mesmo *fora* do bloco da malha:

Exemplo

```javascript
for (var i = 0; i < 10; i++) {
  // algum código
}
return i;
```

## Desempenho do JavaScript (https://www.w3schools.com/js/js_performance.asp)

### Redução de Atividades em *Loops*

*Loops* são sempre usados em programação.

Cada instrução num loop, inclusive a própria instrução de **for**, é executada
para cada *iteração* \(repetição\) do *loop*.

Instruções e atribuições que podem ser colocadas fora de um *loop* podem
tornar a execução do *loop* mais rápida.

Ruim:

```javascript
var i;
for (i = 0; i < arr.length; i++) {
  // ...
}
```

Código melhor:

```javascript
var i;
var l = arr.length;
for (i = 0; i < l; i++) {
  // ...
}
```

O código ruim acessa a propriedade `length` de um array cada vez que o *loop* é
repetido.

O código melhor acessa a propriedade `length` fora do *loop* e torna a execução
do *loop* mais rápida.

### Redução de Acessos ao DOM

Acessar o DOM do HTML é muito lento, comparado com outras instruções de
JavaScript.

Se você espera acessar um elemento de DOM várias vezes, acesse ele uma vez e
use-o como uma variável local:

Exemplo

```javascript
var obj;
obj = document.getElementById("demo");
obj.innerHTML = "Alo";
```

### Redução do Tamanho do **DOM**

Mantenha o número de elementos no **DOM HTML** pequeno.

Isto sempre melhorará o carregamento da página e acelerará a renderização
\(exibição da página\), especialmente e dispositivos pequenos.

Todas as tentativas de busca no **DOM** \(como com `getElementsByTagName`\)
se beneficiam de um **DOM** menor.

### Evite Variáveis Desnecessárias

Não crie variáveis novas a menos que pretenda salvar os valores.

Em geral, você pode substituir código como:

```javascript
var nomeCompleto = nome + " " + sobrenome;
document.getElementById("demo").innerHTML = nomeCompleto;
```

Por:

```javascript
document.getElementById("demo").innerHTML = nome + " " + sobrenome;
```

### Retarde o Carregamento do JavaScript

Colocar seus *scripts* no final do corpo da página deixa o navegador carregar a
página antes.

Enquanto um *script* é baixado \(downloaded\), o navegador não começa a baixar
nada mais. Além disso, toda atividade de análise sintática e renderização pode
ficar bloqueada.

A especificação do HTTP define que navegadores não devem baixar mais de 2
componentes em paralelo.

Uma alternativa é usar `defer="true"` na *tag* do *script*. O atributo `defer`
especifica que o *script* deve ser executado depois da página ter sido
analisada lexicamente, mas ele só funciona para *scripts* externos.

Se possível, você pode adicionar seu *script* à página por código, depois que
a página for carregada:

Exemplo

```javascript
<script>
window.onload = function() {
  var elemento = document.createElement("script");
  elemento.src = "meuScript.js";
  document.body.appendChild(elemento);
};
</script>
```

### Evite o Uso do `with`

Evite usar a palavra-chave `with`. Ela tem um efeito negativo na velocidade de
execução. Ele também confunde os escopos do JavaScript.

A palavra-chave `with` **não é permitida** no modo estrito.

## Palavras Reservadas do JavaScript (https://www.w3schools.com/js/js_reserved.asp)

### No JavaScript, você não pode usar as palavras reservadas como variáveis, rótulos ou nomes de funções:

---------   -----------   ---------     ----------
abstract    arguments     await\*       boolean
break       byte          case          catch
char        class\*       const         continue
debugger    default       delete        do
double      else          enum\*        eval
export\*    extends\*     false         final
finally     float         for           function
goto        if            implements    import\*
in          instanceof    int           interface
let\*       long          native        new
null        package       private       protected
public      return        short         static
super\*     switch        synchronized  this
throw       throws        transient     true
try         typeof        var           void
volatile    while         with          yield
---------   -----------   ---------     ----------

Palavras marcadas com \* são novas no ECMAScript 5 e 6.

### Palavras Removidas da Reserva

As palavras chaves a seguir foram removidas dos padrões ECMAScript 5/6:

---------------   -------------   ----------    -----------
abstract          boolean         byte          char
double            final           float         goto
int               long            native        short
synchronized      throws          transient     volatile
---------------   -------------   ----------    -----------

Não use estas palavras como variáveis. ECMAScript 5/6 não tem suporte completo
em todos os navegadores.

### Objetos, Propriedades e Métodos em JavaScript

Você também deve evitar o uso do nome de objetos, propriedades e métodos do
JavaScript.


--------------   ----------   --------   ----------
Array            Date         eval       function
hasOwnProperty   Infinity     isFinite   isNaN
isPrototypeOf    length       Math       NaN
name             Number       Object     prototype
String           toString     undefined  valueOf
--------------   ----------   --------   ----------

### Palavras Reservadas do Java

JavaScript é usado com frequência com Java. Você deve evitar usar alguns
objetos e propriedades de Java com identificadores de JavaScript.

----------   ------------------   -----------  ---------
getClass     java                 JavaArray    javaClass
JavaObject   JavaPackage
----------   ------------------   -----------  ---------

### Outras Palavras Reservadas

JavaScript pode ser usado como linguagem de programação para muitas aplicações.

Você deve evitar, também, usar o nome de objetos e propriedades de HTML e
Window:

------------  ------------------   ------------------   -------------------
alert         all                  anchor               anchors
area          assign               blur                 button
checkbox      clearInterval        clearTimeout         clientInformation
close         closed               confirm              constructor
crypto        decodeURI            decodeURIComponent   defaultStatus
document      element              elements             embed
embeds        encodeURI            encodeURIComponent   escape
event         fileUpload           focus                form
forms         frame                innerHeight          innerWidth
layer         layers               link                 location
mimeTypes     navigate             navigator            frames
frameRate     hidden               history              image
images        offscreenBuffering   open                 opener
option        outerHeight          outerWidth           packages
pageXOffset   pageYOffset          parent               parseFloat
parseInt      password             pkcs11               plugin
prompt        propertyIsEnum       radio                reset
screenX       screenY              scroll               secure
select        self                 setInterval          setTimeout
status        submit               taint                text
textarea      top                  unescape             untaint
window    
------------  ------------------   ------------------   -------------------

### Manipuladores de Eventos de HTML

Além disso, você deve evitar o uso do nome de todos os manipuladores de
eventos de HTML.

Exemplos:

----------  -----------  ------------  ---------------------
onblur      onclick      onerror       onfocus
onkeydown   onkeypress   onkeyup       onmouseover
onload      onmouseup    onmousedown   onsubmit
----------  -----------  ------------  ---------------------

## JSON (https://www.w3schools.com/js/js_json.asp)

JSON é um formato para armazenar e transferir dados.

JSON é usado com frequência quando dados devem ser enviados de um servidor para
uma página de Web.

### O Que É JSON?

  * JSON é a sigla para *JavaScript Object Notation* \(notação de objetos JS\)
  * JSON é um formato *leve* para troca de dados
  * JSON é independente da linguagem de programação \(\*\)
  * JSON é *auto-descritivo* e fácil de entender

\* A sintaxe do JSON syntax é derivada da notação da sintaxe de notação de
objetos do JavaScript, mas o formato JSON é puro texto. Código para ler e gerar
dados em JSON podem ser escritos em qualquer linguagem de prohramação.

### Exemplo de JSON

Esta sintaxe de JSON define um objetos `empregados`: um *array* com
registros \(objetos\) de 3 empregados:

Exemplo de JSON
```json
{
"empregados":[
  {"nome":"João", "sobrenome":"Silva"},
  {"nome":"Ana", "sobrenome":"Carvalho"},
  {"nome":"Pedro", "sobrenome":"Cavalcante"}
]
}
```

### O Formato JSON É Calculado Em Objetos JavaScript

O formato JSON é sintaticamente identico ao código para criar objetos de
JavaScript.

Por causa da semelhança, um programa JavaScript pode converter facilmente dados
em JSON em objetos JavaScript nativos.

### Regras Sintáticas de JSON

  * Dados estão em pares nome/valor
  * Dados são separados por vírgulas
  * Chaves representam objetos
  * Colchetes representam *arrays*

### JSON Data - A Name and a Value

JSON data is written as name/value pairs, just like JavaScript object properties.

A name/value pair consists of a field name \(in double quotes\), followed by a colon, followed by a value:

```json
"firstName":"John"
```

    JSON names require double quotes. JavaScript names do not.

### JSON Objects

JSON objects are written inside curly braces.

Just like in JavaScript, objects can contain multiple name/value pairs:

```json
{"firstName":"John", "lastName":"Doe"}
```

### JSON Arrays
JSON arrays are written inside square brackets.

Just like in JavaScript, an array can contain objects:

```json
"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]
```

In the example above, the object "employees" is an array. It contains three objects.

Each object is a record of a pessoa \(with a first name and a last name\).

### Converting a JSON Text to a JavaScript Object

A common use of JSON is to read data from a web server, and display the data in a web page.

For simplicity, this can be demonstrated using a string as input.

First, create a JavaScript string containing JSON syntax:

```json
var text = '{ "employees" : [' +
'{ "firstName":"John" , "lastName":"Doe" },' +
'{ "firstName":"Anna" , "lastName":"Smith" },' +
'{ "firstName":"Peter" , "lastName":"Jones" } ]}';
```

Then, use the JavaScript built-in function JSON.parse\(\) to convert the string into a JavaScript object:

```javascript
var obj = JSON.parse(text);
```

Finally, use the new JavaScript object in your page:

Exemplo
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
obj.employees[1].firstName + " " + obj.employees[1].lastName;
</script>
```

## JavaScript Forms (https://www.w3schools.com/js/js_validation.asp)

### JavaScript Form Validation

HTML form validation can be done by JavaScript.

If a form field (fname) is empty, this function alerts a message, and returns false, to prevent the form from being submitted:

JavaScript Exemplo:
```javascript
function validateForm() {
  var x = document.forms["myForm"]["fname"].value;
  if (x == "") {
    alert("Name must be filled out");
    return false;
  }
}
```

The function can be called when the form is submitted:

HTML Form Exemplo: [Demo: Form Val1](valid_demo1.html)
```html
<form name="myForm" action="/action_page.php" onsubmit="return validateForm()" method="post">
Name: <input type="text" name="fname">
<input type="submit" value="Submit">
</form>
```

### JavaScript Can Validate Numeric Input

JavaScript is often used to validate numeric input: [Demo: Form Val2](valid_demo2.html)
Exemplo:
```javascript
function myFunction() {
  var x, text;

  // Get the value of the input field with id="numb"
  x = document.getElementById("numb").value;

  // If x is Not a Number or less than one or greater than 10
  if (isNaN(x) || x < 1 || x > 10) {
    text = "Input not valid";
  } else {
    text = "Input OK";
  }
  document.getElementById("demo").innerHTML = text;
}
```

### Automatic HTML Form Validation

HTML form validation can be performed automatically by the browser:

If a form field (fname) is empty, the required attribute prevents this form from being submitted:

HTML Form Exemplo
```html
<form action="/action_page.php" method="post">
  <input type="text" name="fname" required>
  <input type="submit" value="Submit">
</form>
```

### Data Validation

Data validation is the process of ensuring that user input is clean, correct, and useful.

Typical validation tasks are:

  * has the user filled in all required fields?
  * has the user entered a valid date?
  * has the user entered text in a numeric field?

Most often, the purpose of data validation is to ensure correct user input.

Validation can be defined by many different methods, and deployed in many different ways.

**Server side validation** is performed by a web server, after input has been sent to the server.

**Client side validation** is performed by a web browser, before input is sent to a web server.

   Obs.: You should do both. DON'T rely only on client side validation. Data may be coming without using your js validation.

### HTML Constraint Validation

HTML5 introduced a new HTML validation concept called **constraint validation**.

HTML constraint validation is based on:

  * Constraint validation HTML Input Attributes
  * Constraint validation CSS Pseudo Selectors
  * Constraint validation DOM Properties and Methods

#### Constraint Validation HTML Input Attributes

Attribute | Description
----------|-------------
disabled | Specifies that the input element should be disabled
max | Specifies the maximum value of an input element
min | Specifies the minimum value of an input element
pattern | Specifies the value pattern of an input element
required | Specifies that the input field requires an element
type  | Specifies the type of an input element

#### Constraint Validation CSS Pseudo Selectors

Selector | Description
---------|-------------
:disabled | Selects input elements with the "disabled" attribute specified
:invalid | Selects input elements with invalid values
:optional | Selects input elements with no "required" attribute specified
:required | Selects input elements with the "required" attribute specified
:valid | Selects input elements with valid values

## JavaScript Validation API [JS Validation](https://www.w3schools.com/js/js_validation_api.asp)

### Constraint Validation DOM Methods

Property | Description
---------|---------------
checkValidity\(\) | Returns true if an input element contains valid data.
setCustomValidity\(\) | Sets the validationMessage property of an input element.

If an input field contains invalid data, display a message:

#### The checkValidity\(\) Method

Exemplo: [Demo: Form Val3](valid_demo3.html)
```html
<input id="id1" type="number" min="100" max="300" required>
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var inpObj = document.getElementById("id1");
  if (!inpObj.checkValidity()) {
    document.getElementById("demo").innerHTML = inpObj.validationMessage;
  }
}
</script>
```

### Constraint Validation DOM Properties

Property | Description
---------|------------
validity | Contains boolean properties related to the validity of an input element.
validationMessage | Contains the message a browser will display when the validity is false.
willValidate | Indicates if an input element will be validated.

### Validity Properties
The validity property of an input element contains a number of properties related to the validity of data:

Property | Description
---------|----------------
customError | Set to true, if a custom validity message is set.
patternMismatch | Set to true, if an element's value does not match its pattern attribute.
rangeOverflow | Set to true, if an element's value is greater than its max attribute.
rangeUnderflow | Set to true, if an element's value is less than its min attribute.
stepMismatch | Set to true, if an element's value is invalid per its step attribute.
tooLong | Set to true, if an element's value exceeds its maxLength attribute.
typeMismatch | Set to true, if an element's value is invalid per its type attribute.
valueMissing | Set to true, if an element \(with a required attribute\) has no value.
valid | Set to true, if an element's value is valid.

### Exemplos

If the number in an input field is greater than 100 \(the input's max attribute\), display a message:

#### The rangeOverflow Property
```html
<input id="id1" type="number" max="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var txt = "";
  if (document.getElementById("id1").validity.rangeOverflow) {
    txt = "Value too large";
  }
  document.getElementById("demo").innerHTML = txt;
}
</script>
```

If the number in an input field is less than 100 \(the input's min attribute\), display a message:

#### The rangeUnderflow Property
```html
<input id="id1" type="number" min="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
  var txt = "";
  if (document.getElementById("id1").validity.rangeUnderflow) {
    txt = "Value too small";
  }
  document.getElementById("demo").innerHTML = txt;
}
</script>
```

[Próxima unidade](intermediario3_js.md)
