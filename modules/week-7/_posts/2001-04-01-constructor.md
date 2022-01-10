---
title: Constructor Method
module: 7
jotted: false
---

# Class Constructor
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'purpose')">Purpose</button>

  <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

In every class definition written, there should be at least one function; that is the `constructor` function. Furthermore, typically this should be the first function defined. It doesn't have to be, but by convention and for readability, it is usually the first thing in the class.

The constructor **is always** called by JavaScript when creating a new object from a class. Therefore, you **must** have a constructor.  What is the constructor, you say?  Well, think of the word construct.  What does that mean?  It means to build or construct. So, what the constructor is doing is creating the object from the class.  Cool huh?

</div>
</div>

<div id="purpose" class="tabcontent">
<div class="tabhtml" markdown="1">

## The Purpose of the Constructor

JavaScript uses the **constructor** to build new objects of a class type. You have created an object before -- think about creating a new Array().  Those parentheses at the end of the Array is calling the constructor.  Come on, that's cool, right?

#### So what goes in a _constructor_?

The constructor _initializes_ an object's _properties_.

As an example, if we were creating a Person, we may want to specify properties such as:

- `eyeColor`
- `numberOfLegs`
- `numberOfArms`
- `hairColor`

You will learn more specifically how to do this on the next page.

## Constructor Example

As mentioned, the _constructor_ should be the first function in a _class definition_.

Furthermore, if there is data that needed within the newly created object, this should be represented as _input parameters_ to this function, which works just like any other function.  You have done all of this before.  Don't you love it when it all comes full circle!

So our example might look like:

```js
// a class definition
class Person {

    // constructor
    constructor( eyeColor, numberOfLegs, numberOfArms, hairColor ) {
        // function block
        // Do stuff here to create an object
        console.log(eyeColor);
    }
}
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/p4xykn8VZUI" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="VwmbOQE" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Person class - Constructor">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/VwmbOQE">
  Person class - Constructor</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>
