# JavaScript Tutorial: Basics III

This is my annotations from [javascript tutorial W3C school study](https://www.w3schools.com/js/).

## JavaScript Date Objects (https://www.w3schools.com/js/js_dates.asp)

JavaScript Date Object lets us work with dates.

Example
```javascript
var d = new Date();
```

### JavaScript Date Output

By default, JavaScript will use the browser's time zone and display a date as a full text string:

    Mon Jan 07 2019 22:01:26 GMT-0200 \(Brasilia Summer Time\)

### Creating Date Objects

Date objects are created with the new Date\(\) constructor.

There are 4 ways to create a new date object:

```javascript
new Date()
new Date(year, month, day, hours, minutes, seconds, milliseconds)
new Date(milliseconds)
new Date(date string)
```

#### new Date\(\)

new Date\(\) creates a new date object with the current date and time:

Example

```javascript
var d = new Date();
```

    Date objects are static. The computer time is ticking, but date objects are not.

#### new Date\(year, month, ...\)

new Date\(year, month, ...\) creates a new date object with a specified date and time.

7 numbers specify year, month, day, hour, minute, second, and millisecond \(in that order\):

Example

```javascript
var d = new Date(2018, 11, 24, 10, 33, 30, 0);
```

    JavaScript counts months from 0 to 11.
    January is 0. December is 11.

You can omit last arguments til month \(year and month are obrigatory\).

Example

```javascript
var d = new Date(2018, 11);
```

#### Previous Century

One and two digit years will be interpreted as 19xx:

Example

```javascript
var d = new Date(99, 11, 24);
```

#### new Date\(dateString\)

new Date\(dateString\) creates a new date object from a date string:

Example

```javascript
var d = new Date("October 13, 2014 11:13:00");
```

### JavaScript Stores Dates as Milliseconds

JavaScript stores dates as number of milliseconds since January 01, 1970, 00:00:00 UTC \(Universal Time Coordinated\).

    Zero time is January 01, 1970 00:00:00 UTC.

Now the time is: 1546905686177 milliseconds past January 01, 1970

#### new Date\(milliseconds\)

new Date\(milliseconds\) creates a new date object as zero time plus milliseconds:

Example

```javascript
var d = new Date(0);
```

01 January 1970 plus 100 000 000 000 milliseconds is approximately 03 March 1973:

Example

```javascript
var d = new Date(100000000000);
```

    Results: Sat Mar 03 1973 06:46:40 GMT-0300 (Brasilia Standard Time)

### Date Methods

When a Date object is created, a number of methods allow you to operate on it.

Date methods allow you to get and set the year, month, day, hour, minute, second, and millisecond of date objects, using either local time or UTC \(universal, or GMT\) time.

    Date methods and time zones are covered in the next chapters.

#### Displaying Dates

JavaScript will \(by default\) output dates in full text string format:

  Tue Mar 24 2015 21:00:00 GMT-0300 \(Brasilia Standard Time\)
  
When you display a date object in HTML, it is automatically converted to a string, with the toString\(\) method.

Example

```javascript
d = new Date();
document.getElementById("demo").innerHTML = d;
```

Same as:
```javascript
d = new Date();
document.getElementById("demo").innerHTML = d.toString();
```

The **toUTCString\(\)** method converts a date to a UTC string \(a date display standard\).

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.toUTCString();
```

The toDateString() method converts a date to a more readable format:

Example

```javascript
var d = new Date();
document.getElementById("demo").innerHTML = d.toDateString();
```

## JavaScript Date Formats (https://www.w3schools.com/js/js_date_formats.asp)

### JavaScript Date Input

There are generally 3 types of JavaScript date input formats:

Type       | Example
--------------------------------------------------------
ISO Date   | "2015-03-25" (The International Standard)
Short Date | "03/25/2015"
Long Date  | "Mar 25 2015" or "25 Mar 2015"

    The ISO format follows a strict standard in JavaScript.
    The other formats are not so well defined and might be browser specific.

### JavaScript Date Output

Independent of input format, JavaScript will \(by default\) output dates in full text string format:

  Tue Mar 24 2015 21:00:00 GMT-0300 (Brasilia Standard Time)

### JavaScript ISO Dates

ISO 8601 is the international standard for the representation of dates and times.

The ISO 8601 syntax \(YYYY-MM-DD\) is also the preferred JavaScript date format:

Example \(Complete date\)

```javascript
var d = new Date("2015-03-25");
```

    The computed date will be relative to your time zone.
    Depending on your time zone, the result above will vary between March 24 and March 25.

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
    
