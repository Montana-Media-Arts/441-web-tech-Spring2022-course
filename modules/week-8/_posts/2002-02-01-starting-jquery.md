---
title: The jQuery Object
module: 8
jotted: false
---

# Basics of jQuery

## The jQuery Object

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
<button class="tablinks" onclick="openTab(event, 'document')">document</button>
  <button class="tablinks" onclick="openTab(event, 'selector')">selector</button>
  <button class="tablinks" onclick="openTab(event, 'buttonclick')">button.click</button>
  <button class="tablinks" onclick="openTab(event, 'specificid')">Specific id</button>
  <button class="tablinks" onclick="openTab(event, 'this')">this</button>
  <button class="tablinks" onclick="openTab(event, 'example')">Example</button>
   <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

jQuery works from a simple idea that all elements should be easily accessible and manipulatable. To accomplish this, jQuery utilizes a CSS-like selection process for elements. To select an element, a developer needs to pass CSS-like selections to the jQuery selector. The jQuery selector is `$()`, with the CSS selectors being placed within double quotes.

For example, to select all of the `h1` elements on a page, a developer would call the following;

```js
$( "h1" )
```

This will return a jQuery object containing a reference to the all of the matching `h1` elements in the DOM.

As you will learn, it is from this object that most of your work will occur for jQuery.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/8_o6b0wUHIU" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="document" class="tabcontent">
<div class="tabhtml" markdown="1">

## Document Ready

Another common thing with jQuery is the encouragement that developers use a "document ready" function. This function should wrap any other statements or functions that will effect the DOM. The "document ready" function only executes _after_ the web page and DOM are loaded and ready for manipulation, but before things like images may fully be loaded. You should also get in practice of doing this.

The document ready function looks like one of the following;

```js
// long document ready object
$( document ).ready(function(){
    // your jQuery and DOM related code here
});

// short hand document ready function
$(function(){
    // your jQuery and DOM related code here
});
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zOy5hf8GvXE" frameborder="0" allowfullscreen></iframe></div>

Once, you have a jQuery script in place, you can perform different actions such as manipulate the DOM.

</div>
</div>

<div id="selector" class="tabcontent">
<div class="tabhtml" markdown="1">

One example that we discussed above is changing all the tags at once.  You can use selector **$** with the tag in between the parentheses to change all elements.  One example might be like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $("p").hide();
            });
        });
    </script>
</head>

<body>

    <p>This is a paragraph.</p>
    <p>This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

</div>
</div>

<div id="buttonclick" class="tabcontent">
<div class="tabhtml" markdown="1">

Notice, when you click on the button, it calls this **$("button").click** and then performs the function.  This is new syntax, but it really common in jQuery, so you will see this is many instances.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/_imDTAXNC4c" frameborder="0" allowfullscreen></iframe></div>

We can also find something by id by using the **$** and then the **#** aka hashtag - the cool kids use this.  This should look familiar.  From CSS right?

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $("#infoid").hide();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p>This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

</div>
</div>

<div id="specificid" class="tabcontent">
<div class="tabhtml" markdown="1">

This time only the paragraph with the id **infoid** will disappear while the other **p** tag remains visible.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Wd5AHOC1Z6Q" frameborder="0" allowfullscreen></iframe></div>

You can also find items by their class name and you guessed it, you use the dot `.` to find it.  For example, it might look like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $(".myGreatClass").hide();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/BPDwcA6RKeM" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="this" class="tabcontent">
<div class="tabhtml" markdown="1">

What if we want to find the item that was just clicked? Well, you are in luck!  You can use the `this` keyword and it will find the item that was just accessed.  For example, it will look like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $(this).hide();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```
<br/>
<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/1CRjAS0CF1Y" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="example" class="tabcontent">
<div class="tabhtml" markdown="1">

So, what is really happening behind the scenes?  Does it really remove the item?  I hope not! It's just setting its style to display:none.  What that means is that we can use another method called toggle and that will make items appear and disappear each time the button is clicked.  For example, you might see something like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                $(".myGreatClass").toggle();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/GyYDWOJnncg" frameborder="0" allowfullscreen></iframe></div>

So, where do we go from here?  Let's go to the next page and find out!
</div>
</div>
<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

Click on "Edit on CodePen" to edit and work with the code.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="eYByzjd" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery Example 1">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/eYByzjd">
  jQuery Example 1</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>
</div>