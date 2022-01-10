---
title: Creating new Objects from Classes
module: 7
jotted: false
---

# Creating Objects from Classes

<div class="tab">
    <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
    <button class="tablinks" onclick="openTab(event, 'access')">Access</button>
    <button class="tablinks" onclick="openTab(event, 'calling')">Calling</button>
    <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

A lot of discussions have occurred about classes and objects, yet you still do not know how to create an object from your class definition formally!

To create a new object "of class type _X_", you need to call the `new` keyword, followed by the name of the class, including any constructor input parameters within parentheses trailing the class name.  Remember, we did this with the Array class.  It had the parentheses, but no parameters.

The following creates a new object of class type `Person`, and passes it two input parameters. The variable `myPerson` stores the new object.

```js
let eyeColor = "blue";
let hairColor = "green";
let myPerson = new Person( eyeColor, hairColor );
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/gGc6NUT1Mnc" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="access" class="tabcontent">
<div class="tabhtml" markdown="1">

# Accessing an Objects Properties

To access the properties of an object, we will use the same "_dot notation_" as we learned about with objects' data structures.

```js
myPerson.eyeColor; // ← returns the value of 'myPerson's eyeColor.
```

We can also set object properties using this same notation.

```js
myPerson.hairColor = "purple"; // ← sets the value of the property to purple
```

**NOTE:** Typically, when using classes and OOP paradigms, setting object properties with this notation is considered poor style. Direct access can lead to errors in code, and we will discuss this later.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/r4mjFdaet5E" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="calling" class="tabcontent">
<div class="tabhtml" markdown="1">

# Calling Object Functions

Object function use the _dot notation_.   Parenthesis is always added to the function name, regardless of whether input parameters are being passed into the function.

```js
myPerson.walk(); // ← executes myPerson's function, 'walk'.

myPerson.timeToTravel(distance); // ← execute the function and pass it one input parameter value.
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/q_wACy_hEGI" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="XWNRwxz" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Person class - Accessing Properties and Functions">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/XWNRwxz">
  Person class - Accessing Properties and Functions</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>

