---
title: Review Arrays
module: 6
jotted: false
---

# Review Arrays
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'push')">push</button>
  <button class="tablinks" onclick="openTab(event, 'pop')">pop</button>
  <button class="tablinks" onclick="openTab(event, 'delete')">delete</button>
  <button class="tablinks" onclick="openTab(event, 'functions')">functions</button>
  <button class="tablinks" onclick="openTab(event, 'concat')">concat</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
Hopefully, by now, you have found arrays to be quite handy.  Even in your memory game with only ten values in your array, it would be quite cumbersome if you had five variables for your images, another ten variables for your actual pictures, etc.  Remember, I could ask you to change your program so that it had like 30 images (15 real images times 2).  Yikes! So many variables if you don't use arrays.

</div>
</div>

<div id="push" class="tabcontent">
<div class="tabhtml" markdown="1">


So, what else can we do with arrays?  Well, last week, we looked at the **push** function, which allowed us to add items to our array.  Its syntax was like this:

```html
<html>
    <head>
        <title>
            Array Push
        </title>
        <script>
            function setInformation()
            {   
                var information = new Array();
                information.push("Item 1");
                document.getElementById("info").innerHTML = information[0];
            }
        </script>
    </head>
    <body onload="setInformation();">
        <div style="font-size: 24px" id="info"></div>
        <br>  
    </body>
</html>
```
<br/>
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/c0wjad5kNHI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="pop" class="tabcontent">
<div class="tabhtml" markdown="1">
The opposite of this is **pop**.  Names are added to the stack in a last in first out model **LIFO**.  So, think of it as a deck of cards or a stack of plates.  As you push onto the stack, you place an item on the top.  Then, if you call the pop function, the last thing added is removed.

Here is the syntax which shows how it works:

```html
<html>
    <head>
        <title>
            Array Pop
        </title>
        <script>
            var information;
            function setInformation()
            {          
                information = new Array();
                information.push("Item 1");
                information.push("Item 2");
                information.push("Item 3");
                information.push("Item 4");

                getInformation();   
            }

            function getInformation()
            {
                var firstElement = information.pop();
                document.getElementById("info").innerHTML = firstElement;
                whatsLeftInArray();
            }

            function whatsLeftInArray()
            {
                document.getElementById("whatsleft").innerHTML = information;
            }
            
            
        </script>
    </head>
    <body onload="setInformation();">
        <div style="font-size: 24px" id="info"></div>
        <br>
        <div style="font-size: 24px" id="whatsleft"></div>
        <br>
        
    </body>
</html>
```
Keep in mind that the **whatsLeftInArray** prints out all the elements except for **Item4** because it was popped off.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/-N__3KdXMrk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>


</div>
</div>

<div id="delete" class="tabcontent">
<div class="tabhtml" markdown="1">
Know that this is different from **deleting** an item from an array.  If you delete an item, it sets the value to undefined, but the index still exists in the array.  For example:

```html
<html>
    <head>
        <title>
            Array Delete
        </title>
        <script>
            var information;
            function setInformation()
            {          
                information = new Array();
                information.push("Item 1");
                information.push("Item 2");
                information.push("Item 3");
                information.push("Item 4");

                getInformation();   
            }

            function getInformation()
            {
                delete information[0];
                document.getElementById("info").innerHTML = information.toString();
            }
        </script>
    </head>
    <body onload="setInformation();">
        <div style="font-size: 24px" id="info"></div>
        <br>
        <div style="font-size: 24px" id="whatsleft"></div>
        <br> 
    </body>
</html>
```
<br/>
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/uwINAXU66Kw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="functions" class="tabcontent">
<div class="tabhtml" markdown="1">
Another interesting aspect of JavaScript arrays is that you can add not only strings, numbers, and objects, but also **functions**.  Adding functions to arrays means we can add functionality to an array.  That's crazy!  Here is the syntax for it:

```html
<html>
    <head>
        <title>
            Array Function Add
        </title>
        <script>
            function setInformation()
            {
                var information = new Array();
                information.push(changeInformation());

                information[0];
            }
            
            function changeInformation()
            {
                document.getElementById("info").innerHTML = "This is my function called from an array.";
            }
        </script>
    </head>
    <body onload="setInformation();">
        <div id="info"></div>
        <br>
    </body>
</html>
```
<br/>
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/mC4obhKrrPY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="concat" class="tabcontent">
<div class="tabhtml" markdown="1">
So, what if we have two arrays and we want to put them together?  That is where the **concat** function comes in.  You already know the **concatenation** term from strings.  Concat is no different; it just goes through and combines two (or more) arrays.  Here is the syntax for two arrays:

```html
<html>
    <head>
        <title>
            Array Concat
        </title>
        <script>
            function setInformation()
            {   
                var bikes = ["Salsa", "Santa Cruz", "Orbea", "Kona"];
                var models = ["Cutthroat", "5010", "Orca", "Jake the Snake"];
                var information = bikes.concat(models);
                document.getElementById("info").innerHTML = information.toString();
            }
        </script>
    </head>
    <body onload="setInformation();">
        <div style="font-size: 24px" id="info"></div>
        <br>  
    </body>
</html>
```
<br/>
<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/5uTy3_W-d5M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="references" class="tabcontent">
<div class="tabhtml" markdown="1">
There are many more functions that may help you along the way.  I recommend taking a look at these two links:

[Array Functions](https://www.w3schools.com/js/js_array_methods.asp)

[Array Sorting Functions](https://www.w3schools.com/js/js_array_sort.asp)
</div>
</div>

<div id="ToDo" class="tabcontent">
<div class="tabhtml" markdown="1">
Please feel free to experiment with the code from the other tabs.

Click on **Edit on CodePen** to experiment.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="result" data-user="retrog4m3r" data-slug-hash="OJbJLvb" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Workspace">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/OJbJLvb">
  MART 441 Workspace</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>
</div>

