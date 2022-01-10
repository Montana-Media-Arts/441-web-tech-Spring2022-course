---
title: Program Structure
module: 3
jotted: true
---

# Program Structure

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'Bindings')">Bindings</button>
  <button class="tablinks" onclick="openTab(event, 'Functions')">Functions</button>
  <button class="tablinks" onclick="openTab(event, 'Controls')">Controls</button>
  <button class="tablinks" onclick="openTab(event, 'Assignments')">Assignments</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
Consider reading the following

- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 2; Program Structure_](http://eloquentjavascript.net/3rd_edition/02_program_structure.html)
- **JavaScript Guide.** MDN web docs. 2018. Web.
    - [_Control flow and error handling_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
    - [Loops and Iteration_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)

</div>

<div id="Bindings" class="tabcontent">
<div class="tabhtml" markdown="1">

- _Bindings_
    - `let`
    - `var`
    - `const`
        - Recognize that the latter of these is unchangeable

#### Using let and const (2015)

Before 2015, using the **var** keyword was the only way to declare a JavaScript variable.

The 2015 version of JavaScript (ES6 - ECMAScript 2015) allows the use of the **const** keyword to define a variable that cannot be reassigned, and the **let** keyword to define a variable with restricted scope.

#### Scope 
let and const two keywords provide **Block Scope** variables (and constants) in JavaScript.

Before ES2015, JavaScript had only two types of scope: Global Scope and Function Scope. 

**Global Scope**

Variables declared Globally (outside any function) have Global Scope.

```js
var carName = "Volvo";

// code here can use carName

function myFunction() {
  // code here can also use carName
}
```

**Function Scope**

Variables declared Locally (inside a function) have Function Scope.

```js
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```

**JavaScript Block Scope**

Variables declared with the var keyword cannot have Block Scope.

Variables declared inside a block {} can be accessed from outside the block.

```js
{
  var x = 2;
}
// x CAN be used here
```

Before ES2015 JavaScript did not have Block Scope.

Variables declared with the let keyword can have Block Scope.

Variables declared inside a block {} cannot be accessed from outside the block:

```js
{
  let x = 2;
}
// x can NOT be used here
```

#### Const

Assigned when Declared

JavaScript const variables must be assigned a value when they are declared:


Incorrect

```js
const PI;
PI = 3.14159265359;
```

Correct

```js
const PI = 3.14159265359;
```

**Not Real Constants**

The keyword const is a little misleading.

It does NOT define a constant value. It defines a constant reference to a value.

Because of this, we cannot change constant primitive values, but we can change the properties of constant objects.

Primitive Values

If we assign a primitive value to a constant, we cannot change the primitive value: 

```js
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/7OLJsDclVXY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>
<div id="Functions" class="tabcontent">
<div class="tabhtml" markdown="1">

- _Functions_
    - especially;
        - `console.log()`
        - `prompt()`

**The console.log() Method**

If your browser supports debugging, you can use console.log() to display JavaScript values in the debugger window:

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>

<script>
    a = 5;
    b = 6;
    c = a + b;
    console.log(c);
</script>

</body>
</html>
```

#### Window prompt() Method


Display a prompt box which ask the user for her/his name, and output a message:

```js
var person = prompt("Please enter your name", "Harry Potter");

if (person != null) {
  document.getElementById("demo").innerHTML =
  "Hello " + person + "! How are you today?";
}
```

**Definition and Usage**

The prompt() method displays a dialog box that prompts the visitor for input.

A prompt box is often used if you want the user to input a value before entering a page.

Note: When a prompt box pops up, the user will have to click either "OK" or "Cancel" to proceed after entering an input value. Do not overuse this method, as it prevents the user from accessing other parts of the page until the box is closed.

The prompt() method returns the input value if the user clicks "OK". If the user clicks "cancel" the method returns null.

Recognize that the _functions_ can produce _Return Values_

**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/smVWNLrZnz4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>
<div id="Controls" class="tabcontent">
<div class="tabhtml" markdown="1">

_Control Flow_
- As well as using _conditional execution_ with control flow

- `if(){}`
- `if(){} / else{}`
- `if(){} / else if(){} / else{}`
- `while(){}`
- `do{}while()`
- `break`
- `switch`

**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/-UZdpIUFGQo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>
<div id="Assignments" class="tabcontent">
<div class="tabhtml" markdown="1">


#### Basic coding standards and conventions
    - Use proper "naming conventions" when creating bindings
        - Including what characters can and cannot be used
        - Utilize a single approach to capitalization
    - Indent Code Properly
    - Understand how to include comments

#### Assignment operators
    - `+=`
    - `-=`
    - `*=`
    - `/=`
    - `++`
    - `--`

**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/G4v2oGLIIYw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
</div>
</div>
<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">

Please allow a few seconds for this to load.

<iframe src="https://umontanamediaarts.com/MART441/wp-admin/admin-ajax.php?action=h5p_embed&id=2" width="959" height="301" frameborder="0" allowfullscreen="allowfullscreen"></iframe><script src="https://umontanamediaarts.com/MART441/wp-content/plugins/h5p/h5p-php-library/js/h5p-resizer.js" charset="UTF-8"></script>

### Interactive JS Console

Feel free to try out some of the prior examples.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            content: "// try out operators, values, etc, here...\n\n// as an example\nconsole.log( typeof \"Hello World!\");\nif(2<10)\n{\nconsole.log( 'true' );\n}\n\n\n"
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