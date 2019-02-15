# JavaScript Tutorial: Arrays

This is my annotations from [javascript tutorial W3C school study](https://www.w3schools.com/js/).

## JavaScript Arrays (https://www.w3schools.com/js/js_arrays.asp)

JavaScript arrays are used to store multiple values in a single variable.

```javascript
var cars = ["Saab", "Volvo", "BMW"];
```

### What is an Array?

An array is a special variable, which can hold more than one value at a time.

If you have a list of items (a list of car names, for example), storing the cars in single variables could look like this:

```javascript
var car1 = "Saab";
var car2 = "Volvo";
var car3 = "BMW";
```

However, what if you want to loop through the cars and find a specific one? And what if you had not 3 cars, but 300?

The solution is an **array**!

An array can hold many values under a single name, and you can access the values by referring to an index number.

### Creating an Array

Using an array literal is the easiest way to create a JavaScript Array.

*Syntax*:

```javascript
var array_name = [item1, item2, ...];
// Example
var cars = ["Saab", "Volvo", "BMW"];
```

Spaces and line breaks are not important. A declaration can span multiple lines:

```javascript
var cars = [
  "Saab",
  "Volvo",
  "BMW"
];
```

    Putting a comma after the last element (like "BMW",)  is inconsistent across browsers.
    IE 8 and earlier will fail.

### Using the JavaScript Keyword new

The following example also creates an Array, and assigns values to it:

```javascript
var cars = new Array("Saab", "Volvo", "BMW");
```

    The two examples above do exactly the same. There is no need to use new Array().
    For simplicity, readability and execution speed, use the first one (the array literal method).

### Access the Elements of an Array

You access an array element by referring to the index number.

This statement accesses the value of the first element in cars:

```javascript
var name = cars[0];
```

Example: (arraydemo1.html)

```javascript
var cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars[0];
```

    Array indexes start with 0.
    [0] is the first element. [1] is the second element.

### Changing an Array Element

This statement changes the value of the first element in cars:

```javascript
cars[0] = "Opel";
```

Example: (array_demo2.html)

```javascript
var cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Opel";
document.getElementById("demo").innerHTML = cars[0];
```

### Access the Full Array

With JavaScript, the full array can be accessed by referring to the array name:

```javascript
var cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars;
```

### Arrays are Objects

Arrays are a special type of objects. The typeof operator in JavaScript returns "object" for arrays.

But, JavaScript arrays are best described as arrays.

Arrays use numbers to access its "elements". In this example, person\[0\] returns John:

Array:
```javascript
var person = ["John", "Doe", 46];
```

Objects use names to access its "members". In this example, person.firstName returns John:

Object:
```javascript
var person = {firstName:"John", lastName:"Doe", age:46};
```

### Array Elements Can Be Objects

JavaScript variables can be objects. Arrays are special kinds of objects.

Because of this, you can have variables of different types in the same Array.

You can have objects in an Array. You can have functions in an Array. You can have arrays in an Array:

```javascript
myArray[0] = Date.now;
myArray[1] = myFunction;
myArray[2] = myCars;
```

### Array Properties and Methods

The real strength of JavaScript arrays are the built-in array properties and methods:

Examples
```javascript
var x = cars.length;   // The length property returns the number of elements
var y = cars.sort();   // The sort() method sorts arrays
```

### The length Property

The length property of an array returns the length of an array (the number of array elements).

Example
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.length;   // the length of fruits is 4
```

    The length property is always one more than the highest array index.

### Accessing the First Array Element

Example
```javascript
fruits = ["Banana", "Orange", "Apple", "Mango"];
var first = fruits[0];
```

### Accessing the Last Array Element

Example
```javascript
fruits = ["Banana", "Orange", "Apple", "Mango"];
var last = fruits[fruits.length - 1];
```

### Looping Array Elements

The safest way to loop through an array, is using a "for" loop:

Example: (array_demo3.html)

```javascript
var fruits, text, fLen, i;
fruits = ["Banana", "Orange", "Apple", "Mango"];
fLen = fruits.length;

text = "<ul>";
for (i = 0; i < fLen; i++) {
  text += "<li>" + fruits[i] + "</li>";
}
text += "</ul>";
```

You can also use the Array.forEach() function:

Example: (array_demo4.html)
```javascript
var fruits, text;
fruits = ["Banana", "Orange", "Apple", "Mango"];

text = "<ul>";
fruits.forEach(myFunction);
text += "</ul>";

function myFunction(value) {
  text += "<li>" + value + "</li>";
}
```

### Adding Array Elements

The easiest way to add a new element to an array is using the push\(\) method:

Example
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Lemon");    // adds a new element (Lemon) to fruits
```

    WARNING! 
    Adding elements with high indexes can create undefined "holes" in an array:

Example: (array_demo5.html)
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[6] = "Lemon";    // adds a new element (Lemon) to fruits
```

### Associative Arrays

Many programming languages support arrays with named indexes.

Arrays with named indexes are called associative arrays \(or hashes\).

JavaScript does not support arrays with named indexes.

In JavaScript, arrays always use numbered indexes.  

Example
```javascript
var person = [];
person[0] = "John";
person[1] = "Doe";
person[2] = 46;
var x = person.length;     // person.length will return 3
var y = person[0];         // person[0] will return "John"
```

    WARNING !!
    If you use named indexes, JavaScript will redefine the array to a standard object.
    After that, some array methods and properties will produce incorrect results.

Example:
```javascript
var person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
var x = person.length;     // person.length will return 0
var y = person[0];         // person[0] will return undefined
```

### The Difference Between Arrays and Objects
In JavaScript, **arrays** use **numbered indexes**.  

In JavaScript, **objects** use **named indexes**.

    Arrays are a special kind of objects, with numbered indexes.

### When to Use Arrays. When to use Objects.

  * JavaScript does not support associative arrays.
  * You should use objects when you want the element names to be strings \(text\).
  * You should use arrays when you want the element names to be numbers.

### Avoid new Array()

There is no need to use the JavaScript's built-in array constructor new Array\(\).

Use \[\] instead.

These two different statements both create a new empty array named points:

```javascript
var points = new Array();     // Bad
var points = [];              // Good
```
 
These two different statements both create a new array containing 6 numbers:

```javascript
var points = new Array(40, 100, 1, 5, 25, 10); // Bad
var points = [40, 100, 1, 5, 25, 10];          // Good
```

The new keyword only complicates the code. It can also produce some unexpected results:

```javascript
var points = new Array(40, 100);  // Creates an array with two elements (40 and 100)
```

What if I remove one of the elements?

```javascript
var points = new Array(40);  // Creates an array with 40 undefined elements !!!!!
```

### How to Recognize an Array

A common question is: How do I know if a variable is an array?

The problem is that the JavaScript operator typeof returns "object":

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

typeof fruits;    // returns object
```

The typeof operator returns object because a JavaScript array is an object.

#### Solution 1:

To solve this problem ECMAScript 5 defines a new method Array.isArray():

```javascript
Array.isArray(fruits);   // returns true
```

The problem with this solution is that ECMAScript 5 is not supported in **older browsers**.

#### Solution 2:

To solve this problem you can create your own isArray() function:

```javascript
function isArray(x) {
  return x.constructor.toString().indexOf("Array") > -1;
}
```

The function above always returns true if the argument is an array.

Or more precisely: it returns true if the object prototype contains the word "Array".

#### Solution 3:

The instanceof operator returns true if an object is created by a given constructor:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

fruits instanceof Array;   // returns true
```

## JavaScript Array Methods (https://www.w3schools.com/js/js_array_methods.asp)

### Converting Arrays to Strings

The JavaScript method toString\(\) converts an array to a string of \(comma separated\) array values.

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

The join\(\) method also joins all array elements into a string.

It behaves just like toString\(\), but in addition you can specify the separator:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * ");
```

Result
Banana * Orange * Apple * Mango

### Popping and Pushing

When you work with arrays, it is easy to remove elements and add new elements.

This is what popping and pushing is:

Popping items **out** of an array, or pushing items **into** an array.

### Popping

The pop\(\) method removes the last element from an array:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();              // Removes the last element ("Mango") from fruits
```

The pop\(\) method returns the value that was "popped out":

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.pop();              //  the value of x is "Mango"
```

### Pushing

The push\(\) method adds a new element to an array \(at the end\):

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");       //  Adds a new element ("Kiwi") to fruits
```

The push\(\) method returns the new array length:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.push("Kiwi");   //  the value of x is 5
```

### Shifting Elements

Shifting is equivalent to popping, working on the first element instead of the last.

The shift\(\) method removes the first array element and "shifts" all other elements to a lower index.

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift();            // Removes the first element "Banana" from fruits
```

The shift\(\) method returns the string that was "shifted out":

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.shift();    // the value of x is "Banana"
```

The unshift\(\) method adds a new element to an array \(at the beginning\), and "unshifts" older elements:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon");    // Adds a new element "Lemon" to fruits
```

The unshift\(\) method returns the new array length.

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon");    // Returns 5
```

### Changing Elements

Array elements are accessed using their index number:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[0] = "Kiwi";        // Changes the first element of fruits to "Kiwi"
```

The length property provides an easy way to append a new element to an array:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[fruits.length] = "Kiwi";          // Appends "Kiwi" to fruits
```

### Deleting Elements

Since JavaScript arrays are objects, elements can be deleted by using the JavaScript operator delete:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0];           // Changes the first element in fruits to undefined
```

    Using delete may leave undefined holes in the array. Use pop() or shift() instead.

### Splicing an Array

The splice\(\) method can be used to add new items to an array:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```

The first parameter \(2\) defines the position where new elements should be added \(spliced in\).

The second parameter \(0\) defines how many elements should be removed.

The rest of the parameters \("Lemon" , "Kiwi"\) define the new elements to be added.

The splice\(\) method returns an array with the deleted items:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 2, "Lemon", "Kiwi");
```

### Using splice\(\) to Remove Elements

With clever parameter setting, you can use splice\(\) to remove elements without leaving "holes" in the array:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);        // Removes the first element of fruits
```

The first parameter \(0\) defines the position where new elements should be added \(spliced in\).

The second parameter \(1\) defines how many elements should be removed.

The rest of the parameters are omitted. No new elements will be added.

### Merging \(Concatenating\) Arrays

The concat\(\) method creates a new array by merging \(concatenating\) existing arrays:

Example \(Merging Two Arrays\)

```javascript
var myGirls = ["Cecilie", "Lone"];
var myBoys = ["Emil", "Tobias", "Linus"];
var myChildren = myGirls.concat(myBoys);   // Concatenates (joins) myGirls and myBoys
```

    The concat\(\) method does not change the existing arrays. It always returns a new array.

The concat\(\) method can take any number of array arguments:

Example \(Merging Three Arrays\)

```javascript
var arr1 = ["Cecilie", "Lone"];
var arr2 = ["Emil", "Tobias", "Linus"];
var arr3 = ["Robin", "Morgan"];
var myChildren = arr1.concat(arr2, arr3);   // Concatenates arr1 with arr2 and arr3
```

The concat\(\) method can also take values as arguments:

Example \(Merging an Array with Values\)

```javascript
var arr1 = ["Cecilie", "Lone"];
var myChildren = arr1.concat(["Emil", "Tobias", "Linus"]);
```
 
 ### Slicing an Array
 
The slice\(\) method slices out a piece of an array into a new array.

This example slices out a part of an array starting from array element 1 \("Orange"\):

Example

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1);
```

    The slice() method creates a new array. It does not remove any elements from the source array.

The slice\(\) method can take two arguments like slice\(1, 3\).

The method then selects elements from the start argument, and up to \(but not including\) the end argument.

Example

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3);
```

If the end argument is omitted, like in the first examples, the slice() method slices out the rest of the array.

Example

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(2);
```

### Automatic toString\(\)

JavaScript automatically converts an array to a comma separated string when a primitive value is expected.

This is always the case when you try to output an array.

These two examples will produce the same result:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits;
```

    All JavaScript objects have a toString\(\) method.

### Finding Max and Min Values in an Array

There are no built-in functions for finding the highest or lowest value in a JavaScript array.

## JavaScript Sorting Arrays (https://www.w3schools.com/js/js_array_sort.asp)

### Sorting an Array

The sort\(\) method sorts an array alphabetically:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();        // Sorts the elements of fruits
```

### Reversing an Array

The reverse\(\) method reverses the elements in an array.

You can use it to sort an array in descending order:

Example

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();        // First sort the elements of fruits 
fruits.reverse();     // Then reverse the order of the elements
```

### Numeric Sort

By default, the sort\(\) function sorts values as strings.

This works well for strings \("Apple" comes before "Banana"\).

However, if numbers are sorted as strings, "25" is bigger than "100", because "2" is bigger than "1".

Because of this, the sort\(\) method will produce incorrect result when sorting numbers.

You can fix this by providing a compare function:

Example

```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b});
```

Use the same trick to sort an array descending:

Example

```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a});
```

### The Compare Function

The purpose of the compare function is to define an alternative sort order.

The compare function should return a negative, zero, or positive value, depending on the arguments:

```javascript
function(a, b){return a-b}
```

When the sort\(\) function compares two values, it sends the values to the compare function, and sorts the values according to the returned \(negative, zero, positive\) value.

Example:

When comparing 40 and 100, the sort\(\) method calls the compare function\(40,100\).

The function calculates 40-100, and returns -60 \(a negative value\).

The sort function will sort 40 as a value lower than 100.

You can use this code snippet to experiment with numerically and alphabetically sorting: (array-demo6.html)

```html
<button onclick="myFunction1()">Sort Alphabetically</button>
<button onclick="myFunction2()">Sort Numerically</button>

<p id="demo"></p>

<script>
var points = [40, 100, 1, 5, 25, 10];
document.getElementById("demo").innerHTML = points;

function myFunction1() {
  points.sort();
  document.getElementById("demo").innerHTML = points;
}

function myFunction2() {
  points.sort(function(a, b){return a - b});
  document.getElementById("demo").innerHTML = points;
}
</script>
```

### Sorting an Array in Random Order

Example

```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return 0.5 - Math.random()});
```

### Find the Highest \(or Lowest\) Array Value

There are no built-in functions for finding the max or min value in an array.

However, after you have sorted an array, you can use the index to obtain the highest and lowest values.

Sorting ascending:

Example

```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b});
// now points[0] contains the lowest value
// and points[points.length-1] contains the highest value
```

    Sorting a whole array is a very inefficient method if you only want to find the highest (or lowest) value.

#### Using Math.max\(\) on an Array

You can use Math.max.apply to find the highest number in an array:

Example

```javascript
function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}
```

Math.max.apply\(\[1, 2, 3\]\) is equivalent to Math.max\(1, 2, 3\).

#### Using Math.min\(\) on an Array

You can use Math.min.apply to find the lowest number in an array:

Example

```javascript
function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}
```

Math.min.apply\(\[1, 2, 3\]\) is equivalent to Math.min\(1, 2, 3\).

#### My Min / Max JavaScript Methods

The fastest solution is to use a "home made" method.

This function loops through an array comparing each value with the highest value found:

Example \(Find Max\)

```javascript
function myArrayMax(arr) {
  var len = arr.length
  var max = -Infinity;
  while (len--) {
    if (arr[len] > max) {
      max = arr[len];
    }
  }
  return max;
}
```

This function loops through an array comparing each value with the lowest value found:

Example \(Find Min\)

```javascript
function myArrayMin(arr) {
  var len = arr.length
  var min = Infinity;
  while (len--) {
    if (arr[len] < min) {
      min = arr[len];
    }
  }
  return min;
}
```

### Sorting Object Arrays

JavaScript arrays often contain objects:

Example

```javascript
var cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];
```

Even if objects have properties of different data types, the sort\(\) method can be used to sort the array.

The solution is to write a compare function to compare the property values:

Example

```javascript
cars.sort(function(a, b){return a.year - b.year});
```

Comparing string properties is a little more complex:

Example

```javascript
cars.sort(function(a, b){
  var x = a.type.toLowerCase();
  var y = b.type.toLowerCase();
  if (x < y) {return -1;}
  if (x > y) {return 1;}
  return 0;
});
```

## JavaScript Array Iteration Methods (https://www.w3schools.com/js/js_array_iteration.asp)

Array iteration methods operate on every array item.

### Array.forEach\(\)

The forEach\(\) method calls a function \(a callback function\) once for each array element.

Example

```javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt = txt + value + "<br>"; 
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself
  
The example above uses only the value parameter. The example can be rewritten to:

Example

```javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value) {
  txt = txt + value + "<br>"; 
}
```

Array.forEach\(\) is supported in all browsers except Internet Explorer 8 or earlier.

### Array.map\(\)

The map\(\) method creates a new array by performing a function on each array element.

The map\(\) method does not execute the function for array elements without values.

The map\(\) method does not change the original array.

This example multiplies each array value by 2:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var numbers2 = numbers1.map(myFunction);

function myFunction(value, index, array) {
  return value * 2;
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself
  
When a callback function uses only the value parameter, the index and array parameters can be omitted:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var numbers2 = numbers1.map(myFunction);

function myFunction(value) {
  return value * 2;
}
```

### Array.filter\(\)

The filter\(\) method creates a new array with array elements that passes a test.

This example creates a new array from elements with a value larger than 18:

Example

```javascript
var numbers = [45, 4, 9, 16, 25];
var over18 = numbers.filter(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

### Array.reduce\(\)

The reduce\(\) method runs a function on each array element to produce \(reduce it to\) a single value.

The reduce\(\) method works from left-to-right in the array. See also reduceRight().

The reduce\(\) method does not reduce the original array.

This example finds the sum of all numbers in an array:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction);

function myFunction(total, value, index, array) {
  return total + value;
}
```

Note that the function takes 4 arguments:

  * The total \(the initial value / previously returned value\)
  * The item value
  * The item index
  * The array itself

The example above does not use the index and array parameters. It can be rewritten to:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction);

function myFunction(total, value) {
  return total + value;
}
```

The reduce\(\) method can accept an initial value:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction, 100);

function myFunction(total, value) {
  return total + value;
}
```

#### Array.reduceRight\(\)

The reduceRight\(\) method runs a function on each array element to produce \(reduce it to\) a single value.

The reduceRight\(\) works from right-to-left in the array. See also reduce\(\).

The reduceRight\(\) method does not reduce the original array.

This example finds the sum of all numbers in an array:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduceRight(myFunction);

function myFunction(total, value, index, array) {
  return total + value;
}
```

Note that the function takes 4 arguments:

  * The total (the initial value / previously returned value)
  * The item value
  * The item index
  * The array itself
  
The example above does not use the index and array parameters. It can be rewritten to:

Example

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduceRight(myFunction);

function myFunction(total, value) {
  return total + value;
}
```

### Array.every\(\)

The every\(\) method check if all array values pass a test.

This example check if all array values are larger than 18:

Example

```javascript
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself
  
When a callback function uses the first parameter only \(value\), the other parameters can be omitted:

Example

```javascript
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value) {
  return value > 18;
}
```

 ### Array.some\(\)
 
The some\(\) method check if some array values pass a test.

This example check if some array values are larger than 18:

Example

```javascript
var numbers = [45, 4, 9, 16, 25];
var someOver18 = numbers.some(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself

### Array.indexOf\(\)

Search an array for an element value and returns its position.

Example: Search an array for the item "Apple": (array_demo7.html)

```javascript
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple");
```

#### Syntax

```javascript
array.indexOf(item, start)
```

      |
-------------------------------------------------
item  | Required. The item to search for.
start | Optional. Where to start the search. Negative values will start at the given position counting from the end, and search to the end.

Array.indexOf\(\) returns -1 if the item is not found.

If the item is present more than once, it returns the position of the first occurrence.

### Array.lastIndexOf\(\)

Array.lastIndexOf\(\) is the same as Array.indexOf\(\), but searches from the end of the array.

Example: Search an array for the item "Apple":

```javascript
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");
```

#### Syntax

```javascript
array.lastIndexOf(item, start)
```

      |
-------------------------------------------------
item  | Required. The item to search for.
start | Optional. Where to start the search. Negative values will start at the given position counting from the end, and search to the end.

Array.indexOf\(\) returns -1 if the item is not found.

### Array.find\(\)

The find\(\) method returns the value of the first array element that passes a test function.

This example finds \(returns the value of \) the first element that is larger than 18:

Example

```javascript
var numbers = [4, 9, 16, 25, 29];
var first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself

### Array.findIndex\(\)

The findIndex\(\) method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

Example

```javascript
var numbers = [4, 9, 16, 25, 29];
var first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```

Note that the function takes 3 arguments:

  * The item value
  * The item index
  * The array itself
