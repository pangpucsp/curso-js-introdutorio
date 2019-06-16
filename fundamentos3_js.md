# Fundamentos III de JavaScript

Esta é a continuação de [Fundamentos II de JS](fundamento2_js.md).

## Objetos de [Horário](https://www.w3schools.com/js/js_dates.asp) \(Date\) em JavaScript

O Objeto **Date** de JavaScript permite que se trabalhe com horários.

Exemplo
```javascript
var d = new Date();
```

### Saída de Date no JavaScript

Por norma, JavaScript usa a zona de tempo do navegador e mostra um horário como uma string de texto:

  Fri Feb 22 2019 14:58:36 GMT-0300 \(Brasilia Standard Time\)

### Criação de Objetos Date

Objetos Date são criados com o construtor **new Date\(\)**.

Existem 4 maneiras de criar um novo objeto Date:

```javascript
new Date()
new Date(ano, mes, dia, horas, minutos, segundos, milisegundos)
new Date(milisegundos)
new Date(string de horario)
```

#### Construtor new Date\(\)

**new Date\(\)** cria um novo objeto Date com o dia e a hora atuais:

Exemplo

```javascript
var d = new Date();
```

    Objetos Date são estáticos. O horário no computador está avançando, mas os objetos Date não.

#### new Date\(ano, mes, ...\)

**new Date\(ano, mes, ...\)** cria um novo objeto Date com o dia e a hora especificados.

Os 7 números especificam ano, mes, dia, hora, minuto, segundo e milisegundo \(nesta ordem\):

Exemplo
```javascript
var d = new Date(2018, 11, 24, 10, 33, 30, 0);
```

    JavaScript conta os meses de 0 a 11.
    Janeiro é 0. Dezembro é 11.

Você pode omitir os últimos argumentos, apenas o ano e o mês são obrigatórios.

Exemplo

```javascript
var d = new Date(2018, 11);
```

#### Séculos passados

Ano com um ou dois dígitos são interpretados como 19xx:

Exemplo

```javascript
var d = new Date(99, 11, 24);
```

#### new Date\(dateString\)

new Date\(dateString\) cria um objeto Date a partir da string de horário:

Exemplo

```javascript
var d = new Date("October 13, 2014 11:13:00");
```

### JavaScript Armazena Horários como  Milisegundos

JavaScript armazena horários como o número de milisegundos desde Janeiro 01, 1970, 00:00:00 UTC \(Universal Time Coordinated\).

    Hora zero (0) é Janeiro 01, 1970 00:00:00 UTC.

Agora, 1550858316878 milisegundos desde Jaeiro 01, 1970.


#### new Date\(milisegundos\)

**new Date\(milisegundos\)** creates a new date object as zero time plus milliseconds:

Exemplo

```javascript
var horaZero = new Date(0);
var agora = new Date();
var milis = agora - horaZero;
```

01 January 1970 mais 100 000 000 000 milisegundos é aproximadamente 03 March 1973:

Exemplo

```javascript
var d = new Date(100000000000);
```

    Results: Sat Mar 03 1973 06:46:40 GMT-0300 (Brasilia Standard Time)

### Métodos de Date

Vários métodos permitem a manipulação de um objeto Date.

Métodos de Date permitem ler e alterar o ano, mês, dia, hora, minuto, segundo e milisegundo de objetos Date usando, tanto a hora local, quanto a hora UTC \(ou GMT\).

#### Exibição de Dates

JavaScript vai \(por norma\) exibir horários no formato de string de texto:

  Fri Feb 22 2019 18:45:11 GMT-0300 (Brasilia Standard Time)

Ao mostrar um objeto Date em HTML, ele é automaticamente convertido para um string, com o método toString\(\).

Exemplo

```javascript
d = new Date();
document.getElementById("demo").innerHTML = d;
```

Mesmo que:
```javascript
d = new Date();
document.getElementById("demo").innerHTML = d.toString();
```

O método **toUTCString\(\)** converte um date para uma string UTC  \(um padrão de exibição de Date\).

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.toUTCString();
// resulta em "Fri, 22 Feb 2019 21:50:03 GMT"
```

O método toDateString() converte um Date para um formato mais legível:

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.toDateString();
// resulta em "Fri Feb 22 2019"
```

## [Formatos](https://www.w3schools.com/js/js_date_formats.asp) de Date no JavaScript

### Entradas  de Date no JavaScript

Existem 3 tipos de formatos de entrada de Date no JavaScript:

Tipo       | Exemplo
-----------|--------------------------------------------
ISO Date   | "2015-03-25" (The International Standard)
Short Date | "03/25/2015"
Long Date  | "Mar 25 2015" or "25 Mar 2015"

    O formato ISO segue um padrão estrito em JavaScript.
    Os outros formatos não são tão bem definidos e
    podem mudar de navegador para navegador.

### Saída de Date no JavaScript

Independente do formato de entrada, JavaScript \(por norma\) faz a saída de dates no formato completo de texto em string:

  Tue Feb 24 2019 21:00:00 GMT-0300 (Brasilia Standard Time)

### Datas em ISO no JavaScript

ISO 8601 é o padrão internacional para a representação de datas e horas.

A sintaxe ISO 8601 \(AAAA-MM-DD\) é também o formato de Date preferido de JavaScript:

Exemplo \(Data completa\)

```javascript
var d = new Date("2019-09-25");
```

    O horário calculado será em relação à sua zona de tempo.
    Dependendo da sua zona de tempo, o resultado acima irá variar entre *24 de Março*  e *25 de Março*.

### Datas em ISO \(Ano e Mes\)

Datas em ISO dates podem ser escritas sem o dia \(YYYY-MM\):

Exemplo

```javascript
var d = new Date("2015-03");
```

### Datas em ISO \(Só o Ano\)

Datas em ISO podem ser escritas sem o mes e o dia \(YYYY\):

Exemplo

```javascript
var d = new Date("2015");
```

    Zonas de tempo podem mudar o resultado acima entre 31 de Dezembro
    de 2014 e 01 de Janeiro de 2015.

### Datas em ISO \(Data-Hora\)

Datas em ISO podem ser escritas incluindo horas, minutos e segundos
\(YYYY-MM-DDTHH:MM:SSZ\):

Exemplo

```javascript
var d = new Date("2015-03-25T12:00:00Z");
```

Data e Hora são separados pela letra T maiúscula.

Hora em UTC é definido pela letra maiúscula Z.

Se quiser mudar a hora em relação à UTC, remova o Z e adicione +HH:MM ou -HH:MM,
no lugar:

Exemplo

```javascript
var d = new Date("2015-03-25T12:00:00-06:30");
```

    UTC (Universal Time Coordinated) é o mesmo que GMT (Greenwich Mean Time).

    Omitir T ou Z numa string de data-hora pode dar resultados diferentes
    dependendo do navegador.

### Zonas de Tempo, Timezone

Ao ajustar uma data, sem especificar a zona de tempo, JavaScript usará a zona de
tempo do navegador.

Ao obter uma data, sem especificar a zona de tempo, o resultado será convertido
para a zona de tempodo navegador.

Ou seja, se uma data/hora é criada em GMT, a data/hora será convertida para BRT
\(Brazilian Time, ou UTC-3\) se o navegador estiver na maior parte do Brasil.

### Datas Abrevidas em JavaScript

Datas abreviadas são escritas com uma sintaxe do tipo "MM/DD/YYYY":

Exemplo

```javascript
var d = new Date("03/25/2015");
```

### Alerta !

Em alguns navegadores, meses e dias sem zeros iniciais podem produzir um erro:

```javascript
var d = new Date("3/25/2015");
```

O comportamento de "YYYY/MM/DD" é indefinido.
Alguns navegadores tentam advinhar o formato. Alguns retornam **NaN**.

```javascript
var d = new Date("2015/03/25");
```


O comportamento de "DD-MM-YYYY"também é indefinido.
Alguns navegadores tentam advinhar o formato. Alguns retornam **NaN**.

```javascript
var d = new Date("25-03-2015");
```

### Datas Longas em JavaScript

Datas longas são escritas, em geral, com a sintaxe "MMM DD YYYY":

Exemplo

```javascript
var d = new Date("Mar 25 2015");
```

Mes e dia podem estar em qualquer ordem:

Exemplo

```javascript
var d = new Date("25 Mar 2015");
```

E o mes pode ser escrito completo \(January\), ou abreviado \(Jan\):

Exemplo

```javascript
var d = new Date("January 25 2015");
```

Exemplo

```javascript
var d = new Date("Jan 25 2015");
```

Vírgulas são ignoradas. Nomes podem ser em maiúsculas, ou minúsculas:

Exemplo

```javascript
var d = new Date("JANUARY, 25, 2015");
```

### Entrada de Datas - Análise Léxica \(parsing\) de Datas

Se você tiver uma string de data válida, você pode usar o método Date.parse\(\)
para convertê-la em milisegundos.

Date.parse\(\) retorna o número de milisegundos entre 1&ordm; de janeiro de 1970
e a data:

Exemplo

```javascript
var msec = Date.parse("March 21, 2012");
document.getElementById("demo").innerHTML = msec;
```

Você pode, então, usar o número de milisegundos para convertê-lo num objeto de
data:

Exemplo

```javascript
var msec = Date.parse("March 21, 2012");
var d = new Date(msec);
document.getElementById("demo").innerHTML = d;
```

## Métodos de JavaScript para Obter Datas [JS Date Methods](https://www.w3schools.com/js/js_date_methods.asp)

Os métodos abaixo podem ser usados para obter informações de objetos de data:

|Método              | Descrição |
|--------------------|-------------------------------------------------------|
|getFullYear\(\)     | Obtém o ano com 4 dígitos \(yyyy\) |
|getMonth\(\)        | Obtém o mes como um número \(0-11\) |
|getDate\(\)         | Obtém o dia como um número \(1-31\) |
|getHours\(\)        | Obtém a hora \(0-23\) |
|getMinutes\(\)      | Obtém os minutos \(0-59\) |
|getSeconds\(\)      | Obtém os segundos \(0-59\) |
|getMilliseconds\(\) | Obtém os milisegundos \(0-999\) |
|getTime\(\)         | Obtém a hora \(milisegundos desde 1&ordm; de janeiro de 1970\) |
|getDay\(\)          | Obtém o dia da semana como um número \(0-6\) |
|Date.now\(\)        | Obtém a hora. ECMAScript 5. |

### O Método getTime\(\)

O método getTime\(\) retorna o número de milisegundos desde 1&ordm; de janeiro de 1970:

Exemplo: [Demo: date 2](date_demo2.html)

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getTime();
```

### O Método getFullYear\(\)

O método getFullYear\(\) retorna o ano de uma dara como um número de 4 dígitos:

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getFullYear();
```

### O Método getMonth\(\)

O método getMonth\(\) retorna o mes de uma data como um número \(0-11\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMonth();
```

Você pode usar um vetor de nomes e getMonth\(\) para obter o mes como um nome:

Exemplo

```javascript
var d = new Date();
var meses = ["Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho",
"Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"];
document.getElementById("demo").innerHTML = meses[d.getMonth()];
```

### O Método getDate\(\)

O método getDate\(\) retorna o dia de uma data como um número \(1-31\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getDate();
```

### O Método getHours\(\)

O método getHours\(\) retorna as horas de uma data como um número \(0-23\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getHours();
```

### O Método getMinutes\(\)

O método getMinutes\(\) retorna os minutos de uma data como um número \(0-59\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMinutes();
```

### O Método getSeconds\(\)

O método getSeconds\(\) retorna os segundos de uma data como um número \(0-59\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getSeconds();
```

### O Método getMilliseconds\(\)

O método getMilliseconds\(\) retorna os milisegundos de uma data como um número \(0-999\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMilliseconds();
```

### O Método getDay\(\)

O método getDay\(\) retorna o dia da semana de uma data como um número \(0-6\):

Exemplo

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getDay();
```

    Em JavaScript, O primeiro dia da semana (0) é o *Domingo*, apesar de alguns
    países considerarem que o primeiro dia da semana é a *Segunda-feira*.

Como com os meses, você pode usar um vetor de nomes e obter os dias da semana
pelo nome:

Exemplo

```javascript
var d = new Date();
var dias = ["Domingo", "Segunda-feira", "Terça-feira", "Quarta-feira",
            "Quinta-feira", "Sexta-feira", "Sábado"];
document.getElementById("demo").innerHTML = days[d.getDay()];
```

### Métodos de Datas em UTC

Métodos de dadtas em UTC são usados para trabalhar com datas em UTC
(datas na Zona de Tempo Universal):

|Método                  | Descrição |
|------------------------|----------------------------------------------------|
|getUTCDate\(\)          | O mesmo que getDate\(\), mas retorna a data UTC |
|getUTCDay\(\)           | O mesmo que getDay\(\), mas retorna o dia UTC |
|getUTCFullYear\(\)      | O mesmo que getFullYear\(\), mas retorna o ano UTC |
|getUTCHours\(\)         | O mesmo que getHours\(\), mas retorna a hora UTC |
|getUTCMilliseconds\(\)  | O mesmo que getMilliseconds\(\), mas retorna os milisegundos UTC |
|getUTCMinutes\(\)       | O mesmo que getMinutes\(\), mas retorna os minutos UTC |
|getUTCMonth\(\)         | O mesmo que getMonth\(\), mas retorna o mes UTC |
|getUTCSeconds\(\)       | O mesmo que getSeconds\(\), mas retorna os segundos UTC |

## Métodos para Ajustar as Datas em JavaScript [JS date set methods](https://www.w3schools.com/js/js_date_methods_set.asp)

Os métodos Set de datas permite ajustar os valores de data \(anos, meses, dias,
horas, minutos, segundos, milisegundos\) de um Objeto Date.

### Métodos Set para Datas

Os métodos Set para datas são usados para ajustar uma parte de uma data:

| Método              | Descrição |
|---------------------|----------------------------------------------|
| setDate\(\)         | Set the day as a number \(1-31\) |
| setFullYear\(\)     | Set the year \(optionally month and day\) |
| setHours\(\)        | Set the hour \(0-23\) |
| setMilliseconds\(\) | Set the milliseconds \(0-999\) |
| setMinutes\(\)      | Set the minutes \(0-59\) |
| setMonth\(\)        | Set the month \(0-11\) |
| setSeconds\(\)      | Set the seconds \(0-59\) |
| setTime\(\)         | Set the time \(milliseconds since January 1, 1970\) |

### The setFullYear\(\) Method

The setFullYear\(\) method sets the year of a date object. In this Exemplo to 2020:

Exemplo

```html
<script>
var d = new Date();
d.setFullYear(2020);
document.getElementById("demo").innerHTML = d;
</script>
```

The setFullYear\(\) method can optionally set month and day:

Exemplo

```html
<script>
var d = new Date();
d.setFullYear(2020, 11, 3);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setMonth\(\) Method

The setMonth\(\) method sets the month of a date object \(0-11\):

Exemplo

```html
<script>
var d = new Date();
d.setMonth(11);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setDate\(\) Method

The setDate\(\) method sets the day of a date object \(1-31\):

Exemplo

```html
<script>
var d = new Date();
d.setDate(20);
document.getElementById("demo").innerHTML = d;
</script>
```

The setDate\(\) method can also be used to add days to a date:

Exemplo

```html
<script>
var d = new Date();
d.setDate(d.getDate() + 50);
document.getElementById("demo").innerHTML = d;
</script>
```

    If adding days, shifts the month or year, the changes are handled automatically by the Date object.

### The setHours\(\) Method

The setHours\(\) method sets the hours of a date object \(0-23\):

Exemplo

```html
<script>
var d = new Date();
d.setHours(22);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setMinutes\(\) Method

The setMinutes\(\) method sets the minutes of a date object \(0-59\):

Exemplo

```html
var d = new Date();
d.setMinutes(30);
document.getElementById("demo").innerHTML = d;
</script>
```
<script>

### The setSeconds\(\) Method

The setSeconds\(\) method sets the seconds of a date object \(0-59\):

Exemplo

```html
<script>
var d = new Date();
d.setSeconds(30);
document.getElementById("demo").innerHTML = d;
</script>
```

### Compare Dates

Dates can easily be compared.

The following Exemplo compares today's date with January 14, 2100:

Exemplo: (date_demo3.html)

```javascript
var today, someday, text;
today = new Date();
someday = new Date();
someday.setFullYear(2100, 0, 14);

if (someday > today) {
  text = "Today is before January 14, 2100.";
} else {
  text = "Today is after January 14, 2100.";
}
document.getElementById("demo").innerHTML = text;
```

    JavaScript counts months from 0 to 11. January is 0. December is 11.
