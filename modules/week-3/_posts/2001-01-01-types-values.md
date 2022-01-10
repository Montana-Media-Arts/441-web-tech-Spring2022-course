---
title: Types & Values
module: 3
jotted: true
---

# Values, Data Types, & Operators


<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'Operators')">Math Operators</button>
  <button class="tablinks" onclick="openTab(event, 'String')">String Operators</button>
  <button class="tablinks" onclick="openTab(event, 'Unary')">Unary Operators</button>
  <button class="tablinks" onclick="openTab(event, 'Comparison')">Comparison Operator</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
Consider reading the following

- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 1: Values, Types, and Operators_](http://eloquentjavascript.net/3rd_edition/01_values.html)
- **JavaScript Guide.** MDN web docs. 2018. Web.
    - [_Grammar and Types_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types)
    - [_Expressions and operators_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

- **Values**
    - Regular Values
    - Empty Values
        - `null`
        - `undefined`
- **Data Types**
    - Numbers
        - Regular Numbers
        - Special Numbers
    - Strings
        - regular strings (`"Hello World!"`, `'single quote string'`)
        - special characters (i.e., `\n`, `\t`)
        - template literal strings (``these use backticks and have special properties``)
    - Booleans

### The latest ECMAScript standard defines nine types:

Six Data Types that are primitive:

* undefined 
* Boolean 
* Number 
* String 
* BigInt 
* Symbol 

#### Structural Types:

**Object** : typeof instance === "object". Special non-data but Structural type for any constructed object instance also used as data structures: new Object, new Array, new Map, new Set, new WeakMap, new WeakSet, new Date and almost everything made with new keyword;

**Function** : a non-data structure, though it also answers for typeof operator: typeof instance === "function". This is merely a special shorthand for Functions, though every Function constructor is derived from Object constructor.

#### Structural Root Primitive:

**null** : typeof instance === "object". Special primitive type having additional usage for its value: if object is not inherited, then null is shown;
Keep in mind the only valuable purpose of typeof operator usage is checking the Data Type. If we wish to check any Structural Type derived from Object it is pointless to use typeof for that, as we will always receive "object". The indeed proper way to check what sort of Object we are using is instanceof keyword. But even in that case there might be misconceptions.

As we can see the meaning of every primitive type is obvious except of undefined and null which are almost the same. This happens as the concept of Time is strictly connected with the purpose of algorithms. We can purport something that does not yet exist or does not exist anymore: undefined. But when we wish to be able to represent something that exists being empty, we have to invent another keyword. And that is what null stands for: the beginning of structural meaning.

**Video**

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/XSI_ta0mvOE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>

<div id="Operators" class="tabcontent">
<div class="tabhtml" markdown="1">


**Mathematical Operators**
    
JavaScript Arithmetic Operators

Arithmetic operators perform arithmetic on numbers (literals or variables).

**Operator	    Description**
- `+`	        Addition
- `-`	        Subtraction
- `*`	        Multiplication
- `**`	        Exponentiation
- `/`	        Division
- `%`	        Modulus (Remainder)
- `++`	        Increment
- `--`	        Decrement

**Video**

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/isrkyyJfAz4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="String" class="tabcontent">
<div class="tabhtml" markdown="1">

JavaScript strings are used for storing and manipulating text.

#### JavaScript Strings

A JavaScript string is zero or more characters written inside quotes.


```js
var x = "John Doe";
```

You can use single or double quotes:

```js
var carName1 = "Volvo XC60";  // Double quotes
var carName2 = 'Volvo XC60';  // Single quotes
```

You can use quotes inside a string, as long as they don't match the quotes surrounding the string:

```js
var answer1 = "It's alright";
var answer2 = "He is called 'Johnny'";
var answer3 = 'He is called "Johnny"';
```

String Length

To find the length of a string, use the built-in length property:

```js
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```


Escape Character

Because strings must be written within quotes, JavaScript will misunderstand this string:

```js
var x = "We are the so-called "Vikings" from the north.";
```

The string will be chopped to "We are the so-called ".

The solution to avoid this problem, is to use the backslash escape character.

The backslash (\) escape character turns special characters into string characters:

**Code	Result	Description**
- `\'`	`'`	    Single quote
- `\"`	`"`	    Double quote
- `\\`	`\`	    Backslash

The sequence \"  inserts a double quote in a string:

```js
var x = "We are the so-called \"Vikings\" from the north.";
```

The sequence \'  inserts a single quote in a string:

```js
var x = 'It\'s alright.';
```

The sequence \\  inserts a backslash in a string:

```js
var x = "The character \\ is called backslash.";
```

Six other escape sequences are valid in JavaScript:

**Code	Result**
- `\b`	Backspace
- `\f`	Form Feed
- `\n`	New Line
- `\r`	Carriage Return
- `\t`	Horizontal Tabulator
- `\v`	Vertical Tabulator

**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/DTk3ptbINGo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>

<div id="Unary" class="tabcontent" >
<div class="tabhtml" markdown="1">

#### Unary Operators

The typeof Operator

You can use the typeof operator to find the data type of a JavaScript variable.


* typeof "John"                 // Returns "string"
* typeof 3.14                   // Returns "number"
* typeof NaN                    // Returns "number"
* typeof false                  // Returns "boolean"
* typeof [1,2,3,4]              // Returns "object"
* typeof {name:'John', age:34}  // Returns "object"
* typeof new Date()             // Returns "object"
* typeof function () {}         // Returns "function"
* typeof myCar                  // Returns "undefined" *
* typeof null                   // Returns "object"

Please observe:

* The data type of NaN is number
* The data type of an array is object
* The data type of a date is object
* The data type of null is object
* The data type of an undefined variable is undefined *
* The data type of a variable that has not been assigned a value is also undefined *
* You cannot use typeof to determine if a JavaScript object is an array (or a date).


The Data Type of typeof

The typeofoperator is not a variable. It is an operator. Operators ( + - * / ) do not have any data type.

But, the typeof operator always returns a string (containing the type of the operand).
    
**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/O6_MphRS0E8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>

<div id="Comparison" class="tabcontent">
<div class="tabhtml" markdown="1">

Comparison and Logical operators are used to test for true or false.

#### Comparison Operators

Comparison operators are used in logical statements to determine equality or difference between variables or values.

Given that x = 5, the table below explains the comparison operators:
<blockquote>
<table>
<tr>
<td>Operator</td><td>Description</td><td>Comparing</td><td>Returns</td>
</tr>
<tr>
<td>==</td><td>equal to</td><td>x == 8</td><td>false</td>
</tr>
<tr>
<td colspan="2">&nbsp;</td><td>x == 5</td><td>true</td>
</tr>
<tr>
<td colspan="2">&nbsp;</td><td>x == "5"</td><td>true</td>
</tr>
<tr>
<td>===</td><td>equal value and equal type</td><td>x === 5</td><td>true</td>
</tr>
<tr>
<td colspan="2">&nbsp;</td><td>x === "5"</td><td>false</td>
</tr>
<tr>
<td>!=</td><td>not equal</td><td>x != 8</td><td>true</td>
</tr>
<tr>
<td>!==</td><td>not equal value or not equal type</td><td>x != 5</td><td>false</td>
</tr>
<tr>
<td colspan="2">&nbsp;</td><td>x !== "5"</td><td>true</td>
</tr>
<tr>
<td colspan="2">&nbsp;</td><td>x !== 8</td><td>true</td>
</tr>
<tr>
<td>></td><td>greater than</td><td>x > 8</td><td>false</td>
</tr>
<tr>
<td><</td><td>less than</td><td>x < 8</td><td>true</td>
</tr>
<tr>
<td>>=</td><td>greater than or equal to</td><td>x >= 8</td><td>false</td>
</tr>
<tr>
<td><=</td><td>less than or equal to</td><td>x <= 8</td><td>true</td>
</tr>
</table>
</blockquote>	


#### How Can it be Used

Comparison operators can be used in conditional statements to compare values and take action depending on the result:

if (age < 18) text = "Too young to buy alcohol";
You will learn more about the use of conditional statements in the next chapter of this tutorial.

#### Logical Operators

Logical operators are used to determine the logic between variables or values.

Given that x = 6 and y = 3, the table below explains the logical operators:

**Operator	Description	Example**
- `&&`	    `and`	    `(x < 10 && y > 1) is true`	
- `||`	    `or`	    `(x == 5 || y == 5) is false`	
- `!`	    `not`	    `!(x == y) is true`	

**Conditional (Ternary) Operator**

JavaScript also contains a conditional operator that assigns a value to a variable based on some condition.

**Syntax**

variablename = (condition) ? value1:value2 

```js
var voteable = (age < 18) ? "Too young":"Old enough";
```

If the variable age is a value below 18, the value of the variable voteable will be "Too young", otherwise the value of voteable will be "Old enough".

**Comparing Different Types**

Comparing data of different types may give unexpected results.

When comparing a string with a number, JavaScript will convert the string to a number when doing the comparison. An empty string converts to 0. A non-numeric string converts to NaN which is always false.

**Case	Value**
- `2 < 12`	true	
- `2 < "12"`	true	
- `2 < "John"`	false	
- `2 > "John"`	false	
- `2 == "John"`	false	
- `"2" < "12"`	false	
- `"2" > "12"`	true	
- `"2" == "12"`	false	

When comparing two strings, "2" will be greater than "12", because (alphabetically) 1 is less than 2.

To secure a proper result, variables should be converted to the proper type before comparison:

```js
age = Number(age);
if (isNaN(age)) {
  voteable = "Input is not a number";
} else {
  voteable = (age < 18) ? "Too young" : "Old enough";
}
```
    
**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/yjg6D7B7ozM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">

The following might take a few seconds to load.

<iframe src="https://umontanamediaarts.com/MART441/wp-admin/admin-ajax.php?action=h5p_embed&id=1" width="959" height="345" frameborder="0" allowfullscreen="allowfullscreen"></iframe><script src="https://umontanamediaarts.com/MART441/wp-content/plugins/h5p/h5p-php-library/js/h5p-resizer.js" charset="UTF-8"></script>

### Interactive JS Console

Feel free to try out some of the prior examples.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            content: "// try out operators, values, etc, here...\n\n// as an example\nconsole.log( typeof \"Hello World!\");\nconsole.log( 5*10 == 50 );\n\n\n"
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: false } },
    ]
});
</script>
</div>
</div>

<em><a href="https://www.w3schools.com/js/default.asp" target="_new">Reference</a></em>