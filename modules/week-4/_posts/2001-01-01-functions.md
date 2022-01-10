---
title: Functions
module: 4
jotted: true
---

# Functions In More Depth

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'Calling')">Calling</button>
  <button class="tablinks" onclick="openTab(event, 'Defining')">Defining</button>
  <button class="tablinks" onclick="openTab(event, 'Parameters')">Parameters</button>
  <button class="tablinks" onclick="openTab(event, 'Example')">Example</button>
  <button class="tablinks" onclick="openTab(event, 'Expression')">Expressions</button>
  <button class="tablinks" onclick="openTab(event, 'Reading')">Reading</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
We have already learned that _Functions_ are one of the basic building blocks of programming.  Functions _do something_ in code. They compute values and return data to the main program, or do something else as a side-effect to the main program.

The Mozilla Developer Network (MDN) defines functions as follows;

> Generally speaking, a function is a "subprogram" that can be called by code external to the function. Like the program itself, a function is composed of a sequence of statements called the function body. Values can be passed to a function, and the function may return a value.

Remember, you have been using functions. These include;

```js
console.log("something to print");

prompt("something to say in a popup box");

document.write("print something to the DOM");

window.alert("Hi there!");
```

There are many "builtin" functions to JavaScript, which you will learn about and use as you progress.
</div>
</div>
<div id="Calling" class="tabcontent" >
<div class="tabhtml" markdown="1">


JavaScript also allows you to define and use _your own custom_ functions. Custom functions are critical techniques for writing well structured and maintainable code. As such, you will spend a lot of time this week learning about writing functions and how to use them.

## Basic Invocation

#### Calling Functions

As you will learn about in more detail below, functions are called through the invocation of their name, followed by the _function operator_ (`()`).

```js
doSomething();
```

#### Supplying Function Parameters

Within the function operator, you can supply _parameters_ to the function.  These are variables that we can send to the function

```js
doSomething( param1, param2 );
```

</div>
</div>

<div id="Defining" class="tabcontent" >
<div class="tabhtml" markdown="1">
## Defining Functions

There are generally three ways to define your functions in JS.

#### Function Declaration

The first is to call the `function` keyword, followed by;

- the function name
- a list of parameters (comma separated) to be used
- a series of JS statements within curly brackets (`{}`) to execute when invoking the function.
- notice that the function parameters don't have var in front of it

So, if we look at our earlier example, we need to get information out of the textbox.  We will create a function to get it.

```html
<html>
    <body>
        <label id="lblName">Your Name Goes Here</label><br>
        <input id="txtName" type="text"><br>
        <button id="btnSubmit">Submit</button><br>

         <script>
            function getName()
            {
                var currentName = document.getElementById("txtName").value;
                document.getElementById("lblName").innerHTML = currentName;
                
            }
            
        </script>
    </body>
</html>
```

There are two things to you should notice.  First, look at the **getElementById("txtName").value**  That is new!  To get information from the textbox, you get the value instead of the innerHTML.

Second, we are now assigning the currentName to the **getElementById("lblName").innerHTML**

So, look at it in the browser.  Does it work?

No? Dang!  That's because we never called the function.  So, we need to connect it to the button event.  

So, we are going to add the function call the button click event.

It will look like this.

```html
<html>
    <body>
        <label id="lblName">Your Name Goes Here</label><br>
        <input id="txtName" type="text"><br>
        <button id="btnSubmit" onclick="getName();">Submit</button><br>

         <script>
            function getName()
            {
                var currentName = document.getElementById("txtName").value;
                document.getElementById("lblName").innerHTML = currentName;
                
            }
            
        </script>
    </body>
</html>
```



The onclick event is connected to the button.  It says, when I click on the button, then call the getName function.  Cool right?!!

That is the most common way in which you can create a function.  There are other ways.  However, we will look at those as time goes on.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/A48w8znhujU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="Parameters" class="tabcontent" >
<div class="tabhtml" markdown="1">

The only other thing we are going to examine is parameters.  Functions with parameters look like this.

```html
<html>
    <body>
        <label id="lblName">Your Name Goes Here</label><br>
        <input id="txtName" type="text"><br>
        <button id="btnSubmit" onclick="getName('Nice to meet you');">Submit</button><br>

         <script>
            function getName(greeting)
            {
                var currentName = document.getElementById("txtName").value;
                document.getElementById("lblName").innerHTML = currentName + ", " + greeting;
                
            }
            
        </script>
    </body>
</html>
```
So, we are sending in the **getName(greeting)** greeting parameter, which means we can send in any message and that will be concatenated to the currentName in the message.

Also, notice single quotes surround the message sent into the getName function **onclick="getName('Nice to meet you');"**  Why is that?  It's because the double quotes start and end the call to the function and so we can't use double quotes again.  However, we can use single quotes.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/gzbSPipixbA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="Example" class="tabcontent" >
<div class="tabhtml" markdown="1">

Below is another example

<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            content:
`function myFirstFunction( inParam1, inParam2 ) {
    console.log( "a statement of something to do." );
    return inParam1 * inParam2;
}

let val = myFirstFunction( 4, 2 );
// -> returns 8 to 'val'
// -> and prints "a statement of something to do." in the console

// print val to ensure accuracy
console.log(val);
`
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>

</div>
</div>

<div id="Expression" class="tabcontent" >
<div class="tabhtml" markdown="1">

#### Function Expression

The second way of defining functions is through _function expressions_; these assign a function to a binding namespace (i.e., a variable).

<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            content:
`let multFunc = function( inParam1 ) {
    return inParam1 * inParam1;
};

let result = multFunc(3);
// -> result would equal 9
console.log( result );
`
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>


_Function Expressions_ work the same as _Function Definitions_; the primary difference is that _Function Expressions_ must be defined **before** calling them. _Function Definitions_ are **hoisted** to the top of the JS interpreter and can be placed anywhere in the code, even after their initial call because they are compiled first.

</div>
</div>

<div id="Reading" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Reading

To get started, please read the following, which cover the usage and definition of functions in great detail;

- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 3; Functions_](http://eloquentjavascript.net/3rd_edition/03_functions.html)
- **JavaScript Guide.** MDN web docs. 2018. Web.
    - [_Functions_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

</div>
</div>

<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">

Please feel free to experiment with the code from the other tabs. Click on **Edit on CodePen** to experiment.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="result" data-user="retrog4m3r" data-slug-hash="OJbJLvb" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Workspace">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/OJbJLvb">
  MART 441 Workspace</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>
