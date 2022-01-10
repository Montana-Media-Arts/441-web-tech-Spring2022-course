---
title: Creating jQuery Plugins
module: 9
jotted: false
---

# Creating jQuery Plugins

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>

  <button class="tablinks" onclick="openTab(event, 'multipletags')">Multiple Tags</button>
  <button class="tablinks" onclick="openTab(event, 'chaining')">Chaining</button>
    <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>


</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

How about if we want to make our own, though?  Even though it might sound daunting, it's not too bad.  Let's look at a small example:

```js
$.fn.bluey = function() {
    this.css( "background-color", "blue" );
};
```

We define the function with the `$.fn`, and then name it `bluey`.  Not sure if that is a word or not, but hey, why not?!

Then, the `function()` keyword creates the function, and the CSS applies the styles to whatever element uses the `bluey` function.

So, what does the whole page look like?

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
    <script>
        $.fn.bluey = function () {
            this.css("background-color", "blue");
        };

        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey();
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>

```

If you were to run this page, the background color of our div tag would turn blue when you click the button. Low and behold, we have a new look based on our function.  

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/ammsnsb6Ngg" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="multipletags" class="tabcontent">
<div class="tabhtml" markdown="1">

We can have it apply to any tags we want.  And we can add more changes to the same jQuery plugin function.  It might look like this:

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
        };

        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey();
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/97wPti2QG-s" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="chaining" class="tabcontent">
<div class="tabhtml" markdown="1">

For this to work in a chaining situation and survive in the real world, we must make some changes to the plugin.  First, we have to return `this`. This will return the object so that more functions can be chained to our plugin.  The function definition needs to be put into a **Immediately Invoked Function Expression** and then we need to pass the function jQuery so that it knows that it is a jQuery plugin and won't conflict with anything else.

The new fully qualified jQuery plugin looks like this now:

```js

    (function($){
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
            return this;
       };
    }(jQuery));
```

What this means is that we can do something like this now:

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
       
        (function($){
        $.fn.bluey = function () {
            this.css("background-color", "blue");
            this.css("color", "white");
            this.css("font-size", 24);
            return this;
        };
        }(jQuery));
        $(function () {
            $("button").click(function () {
                $("#changeDiv").bluey().fadeOut("slow").fadeIn("slow");
            });

        });
    </script>
</head>
<body>
    <div id="changeDiv">Test information</div>
    <button id="btnSubmit">Click</button>
</body>
</html>
```

At this point, you can create a simple jQuery plugin.  Come on, that's pretty cool!

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/D-awHrt-Ves" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

#### Basic jQuery Plugin

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="QWGBgWK" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Basic jQuery Plugin">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/QWGBgWK">
  Basic jQuery Plugin</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### Basic jQuery Plugin 2

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="GRNBEgK" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Basic jQuery Plugin 2">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/GRNBEgK">
  Basic jQuery Plugin 2</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### Fully qualified jQuery Plugin

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="YzpjQPM" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Fully qualified jQuery Plugin">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/YzpjQPM">
  Fully qualified jQuery Plugin</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>