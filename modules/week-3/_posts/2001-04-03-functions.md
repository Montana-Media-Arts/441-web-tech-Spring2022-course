---
title: Functions
module: 3
jotted: true
---

# Functions
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'Create')">Create</button>
  <button class="tablinks" onclick="openTab(event, 'Test')">Test</button>
  <button class="tablinks" onclick="openTab(event, 'Update')">Update</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
**Video**
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/eLZjLu6yIgY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Okay, so now let's take it a step further and create a function.  Now, do you all feel comfortable with functions, also known as methods? 

If not, functions are chunks of code that can be reused and usually perform only one thing.  Reuse is vital, so we don't duplicate code everywhere.  We want to maximize reusability and minimize maintainability.  That should be your mantra!
</div>


<div id="Create" class="tabcontent">
<div class="tabhtml" markdown="1">
So, now let's create a function and use it.

Please create a new file and called it functions.html.  Enter the following:

```html
<html>
    <head>
        <title>Accessing the DOM</title>
        <script>
            function doSomething()
            {
                window.alert("HI");
            }
        </script>
   
    </head>
    <body>
        <div id="changeme">I love functions</div>
    </body>
</html>
```
</div>
</div>
<div id="Test" class="tabcontent">
<div class="tabhtml" markdown="1">
Now, when you open this page, nothing happens.  Check the console, and you shouldn't see any errors.  So, what happened? Remember, how I said HTML pages start at the top and read down?  The HTML page reads from top to bottom, but for the function to execute, it must be called.  So, for this to work, we need to do something like this:

```html
<html>
    <head>
        <title>Accessing the DOM</title>
        <script>
            function doSomething()
            {
                window.alert("HI");
            }
        </script>
   
    </head>
    <body>
        <div id="changeme">I love functions</div>
        <script>
            doSomething();
        </script>
    </body>
</html>
```

Did you see the annoying popup box?  Yes!  You have created your first one.  It won't be your last.
</div>
</div>
<div id="Update" class="tabcontent">
<div class="tabhtml" markdown="1">
The final portion that you need to know is changing the window.alert to something that will print out on the screen.

To do this, you want to change the following.

```js
 window.alert("HI");
```

to something like this

```js
document.write("HI");
```

Now, it should show up on the web page as opposed to a popup.  Keep in mind that you can add HTML tags in between the double-quotes.

```js
document.write("<h1>HI</h1>");
```
</div>
</div>
<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">

Please wait a few seconds for this to load.

<iframe src="https://umontanamediaarts.com/MART441/wp-admin/admin-ajax.php?action=h5p_embed&id=4" width="959" height="347" frameborder="0" allowfullscreen="allowfullscreen"></iframe><script src="https://umontanamediaarts.com/MART441/wp-content/plugins/h5p/h5p-php-library/js/h5p-resizer.js" charset="UTF-8"></script>

### Interactive JS Console

Feel free to try out some of the prior examples. If you want to make changes, please click on **Edit on CodePen**

<iframe height="265" style="width: 100%;" scrolling="no" title="MART 441 Functions" src="https://codepen.io/retrog4m3r/embed/BaLEypd?height=265&theme-id=dark&default-tab=html,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/retrog4m3r/pen/BaLEypd'>MART 441 Functions</a> by Michael Cassens
  (<a href='https://codepen.io/retrog4m3r'>@retrog4m3r</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
</div>
</div>
