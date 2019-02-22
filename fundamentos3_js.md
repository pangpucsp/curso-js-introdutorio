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
    Os outros formatos não são tão bem definidos e podem ser específicos do navegador.

### Saída de Date no JavaScript

Independente do formato de entrada, JavaScript \(por norma\) faz a saída de dates no formato completo de texto em string:

  Tue Feb 24 2019 21:00:00 GMT-0300 (Brasilia Standard Time)

### Dates em ISO no JavaScript

ISO 8601 é o padrão internacional para a representação de datas e horas.

A sintaxe ISO 8601 \(AAAA-MM-DD\) é também o formato de Date preferido de JavaScript:

Exemplo \(Data completa\)

```javascript
var d = new Date("2019-09-25");
```

    O horário calculado será em relação à sua zona de tempo.
    Dependendo da sua zona de tempo, o resultado acima irá variar entre *24 Março*  e *25 Março*.

### ISO Dates \(Year and Month\)

ISO dates can be written without specifying the day \(YYYY-MM\):

Example

```javascript
var d = new Date("2015-03");
```

### ISO Dates \(Only Year\)

ISO dates can be written without month and day \(YYYY\):

Example

```javascript
var d = new Date("2015");
```

    Time zones will vary the result above between December 31 2014 and January 01 2015.

### ISO Dates \(Date-Time\)

ISO dates can be written with added hours, minutes, and seconds \(YYYY-MM-DDTHH:MM:SSZ\):

Example

```javascript
var d = new Date("2015-03-25T12:00:00Z");
```

Date and time is separated with a capital T.

UTC time is defined with a capital letter Z.

If you want to modify the time relative to UTC, remove the Z and add +HH:MM or -HH:MM instead:

Example

```javascript
var d = new Date("2015-03-25T12:00:00-06:30");
```

    UTC (Universal Time Coordinated) is the same as GMT (Greenwich Mean Time).

    Omitting T or Z in a date-time string can give different result in different browser.

### Time Zones

When setting a date, without specifying the time zone, JavaScript will use the browser's time zone.

When getting a date, without specifying the time zone, the result is converted to the browser's time zone.

In other words: If a date/time is created in GMT \(Greenwich Mean Time\), the date/time will be converted to CDT \(Central US Daylight Time\) if a user browses from central US.

### JavaScript Short Dates.

Short dates are written with an "MM/DD/YYYY" syntax like this:

Example

```javascript
var d = new Date("03/25/2015");
```

### WARNINGS !

In some browsers, months or days with no leading zeroes may produce an error:

```javascript
var d = new Date("2015-3-25");
```

The behavior of "YYYY/MM/DD" is undefined.
Some browsers will try to guess the format. Some will return NaN.

```javascript
var d = new Date("2015/03/25");
```


The behavior of  "DD-MM-YYYY" is also undefined.
Some browsers will try to guess the format. Some will return NaN.

```javascript
var d = new Date("25-03-2015");
```

### JavaScript Long Dates

Long dates are most often written with a "MMM DD YYYY" syntax like this:

Example

```javascript
var d = new Date("Mar 25 2015");
```

Month and day can be in any order:

Example

```javascript
var d = new Date("25 Mar 2015");
```

And, month can be written in full (January), or abbreviated (Jan):

Example

```javascript
var d = new Date("January 25 2015");
```

Example

```javascript
var d = new Date("Jan 25 2015");
```

Commas are ignored. Names are case insensitive:

Example

```javascript
var d = new Date("JANUARY, 25, 2015");
```

### Date Input - Parsing Dates

If you have a valid date string, you can use the Date.parse\(\) method to convert it to milliseconds.

Date.parse\(\) returns the number of milliseconds between the date and January 1, 1970:

Example

```javascript
var msec = Date.parse("March 21, 2012");
document.getElementById("demo").innerHTML = msec;
```

You can then use the number of milliseconds to convert it to a date object:

Example

```javascript
var msec = Date.parse("March 21, 2012");
var d = new Date(msec);
document.getElementById("demo").innerHTML = d;
```

## JavaScript Get Date Methods (https://www.w3schools.com/js/js_date_methods.asp)

These methods can be used for getting information from a date object:

Method              | Description
-----------------------------------------------------------------------------
getFullYear\(\)     | Get the year as a four digit number \(yyyy\)
getMonth\(\)        | Get the month as a number \(0-11\)
getDate\(\)         | Get the day as a number \(1-31\)
getHours\(\)        | Get the hour \(0-23\)
getMinutes\(\)      | Get the minute \(0-59\)
getSeconds\(\)      | Get the second \(0-59\)
getMilliseconds\(\) | Get the millisecond \(0-999\)
getTime\(\)         | Get the time \(milliseconds since January 1, 1970\)
getDay\(\)          | Get the weekday as a number \(0-6\)
Date.now\(\)        | Get the time. ECMAScript 5.

### The getTime\(\) Method

The getTime\(\) method returns the number of milliseconds since January 1, 1970:

Example: (date_demo2.html)

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getTime();
```

### The getFullYear\(\) Method

The getFullYear\(\) method returns the year of a date as a four digit number:

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getFullYear();
```

### The getMonth\(\) Method

The getMonth\(\) method returns the month of a date as a number \(0-11\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMonth();
```

You can use an array of names, and getMonth() to return the month as a name:

Example

```javascript
var d = new Date();
var months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
document.getElementById("demo").innerHTML = months[d.getMonth()];
```

### The getDate\(\) Method

The getDate\(\) method returns the day of a date as a number \(1-31\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getDate();
```

### The getHours\(\) Method

The getHours\(\) method returns the hours of a date as a number \(0-23\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getHours();
```

### The getMinutes\(\) Method

The getMinutes\(\) method returns the minutes of a date as a number \(0-59\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMinutes();
```

### The getSeconds\(\) Method

The getSeconds\(\) method returns the seconds of a date as a number \(0-59\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getSeconds();
```

### The getMilliseconds\(\) Method

The getMilliseconds\(\) method returns the milliseconds of a date as a number \(0-999\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getMilliseconds();
```

### The getDay\(\) Method

The getDay\(\) method returns the weekday of a date as a number \(0-6\):

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.getDay();
```

    In JavaScript, the first day of the week (0) means "Sunday", even if some countries in the world consider the first day of the week to be "Monday"

You can use an array of names, and getDay() to return the weekday as a name:

Example

```javascript
var d = new Date();
var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
document.getElementById("demo").innerHTML = days[d.getDay()];
```

### UTC Date Methods

UTC date methods are used for working with UTC dates (Universal Time Zone dates):

Method                  | Description
---------------------------------------------------------------------------------------
getUTCDate\(\)          | Same as getDate\(\), but returns the UTC date
getUTCDay\(\)           | Same as getDay\(\), but returns the UTC day
getUTCFullYear\(\)      | Same as getFullYear\(\), but returns the UTC year
getUTCHours\(\)         | Same as getHours\(\), but returns the UTC hour
getUTCMilliseconds\(\)  | Same as getMilliseconds\(\), but returns the UTC milliseconds
getUTCMinutes\(\)       | Same as getMinutes\(\), but returns the UTC minutes
getUTCMonth\(\)         | Same as getMonth\(\), but returns the UTC month
getUTCSeconds\(\)       | Same as getSeconds\(\), but returns the UTC seconds

## JavaScript Set Date Methods (https://www.w3schools.com/js/js_date_methods_set.asp)

Set Date methods let you set date values \(years, months, days, hours, minutes, seconds, milliseconds\) for a Date Object.

### Set Date Methods

Set Date methods are used for setting a part of a date:

Method              | Description
--------------------------------------------------------------------
setDate\(\)         | Set the day as a number \(1-31\)
setFullYear\(\)     | Set the year \(optionally month and day\)
setHours\(\)        | Set the hour \(0-23\)
setMilliseconds\(\) | Set the milliseconds \(0-999\)
setMinutes\(\)      | Set the minutes \(0-59\)
setMonth\(\)        | Set the month \(0-11\)
setSeconds\(\)      | Set the seconds \(0-59\)
setTime\(\)         | Set the time \(milliseconds since January 1, 1970\)

### The setFullYear\(\) Method

The setFullYear\(\) method sets the year of a date object. In this example to 2020:

Example

```html
<script>
var d = new Date();
d.setFullYear(2020);
document.getElementById("demo").innerHTML = d;
</script>
```

The setFullYear\(\) method can optionally set month and day:

Example

```html
<script>
var d = new Date();
d.setFullYear(2020, 11, 3);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setMonth\(\) Method

The setMonth\(\) method sets the month of a date object \(0-11\):

Example

```html
<script>
var d = new Date();
d.setMonth(11);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setDate\(\) Method

The setDate\(\) method sets the day of a date object \(1-31\):

Example

```html
<script>
var d = new Date();
d.setDate(20);
document.getElementById("demo").innerHTML = d;
</script>
```

The setDate\(\) method can also be used to add days to a date:

Example

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

Example

```html
<script>
var d = new Date();
d.setHours(22);
document.getElementById("demo").innerHTML = d;
</script>
```

### The setMinutes\(\) Method

The setMinutes\(\) method sets the minutes of a date object \(0-59\):

Example

```html
var d = new Date();
d.setMinutes(30);
document.getElementById("demo").innerHTML = d;
</script>
```
<script>

### The setSeconds\(\) Method

The setSeconds\(\) method sets the seconds of a date object \(0-59\):

Example

```html
<script>
var d = new Date();
d.setSeconds(30);
document.getElementById("demo").innerHTML = d;
</script>
```

### Compare Dates

Dates can easily be compared.

The following example compares today's date with January 14, 2100:

Example: (date_demo3.html)

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
