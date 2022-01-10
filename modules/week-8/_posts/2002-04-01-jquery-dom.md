---
title: jQuery DOM
module: 8
jotted: false
---

# jQuery and the DOM

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
<button class="tablinks" onclick="openTab(event, 'text')">text</button>
<button class="tablinks" onclick="openTab(event, 'html')">html</button>
<button class="tablinks" onclick="openTab(event, 'val')">val</button>
<button class="tablinks" onclick="openTab(event, 'changetext')">Change text</button>
<button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

What about the DOM?  Remember the document.getElementById?  How do we access the DOM elements in jQuery?

So, to access or change items in the DOM, you have three main methods that allow you to do that:

1. text()
2. html()
3. val()

These will allow us to get the text items from an element, the text including any HTML markup or the value from a textbox for instance.

</div>
</div>

<div id="text" class="tabcontent">
<div class="tabhtml" markdown="1">

Let's see these in action.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#infoid").text());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

This code should return just the inner text of the paragraph tag.  

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/OVwOulkRlqI" frameborder="0" allowfullscreen></iframe></div>


</div>
</div>

<div id="html" class="tabcontent">
<div class="tabhtml" markdown="1">

However, using the **html** method, we should get everything including the bold tags **<b>**.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#infoid").html());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/evCDKmkQSYM" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="val" class="tabcontent">
<div class="tabhtml" markdown="1">

Finally, if we want to get something out of a textfield, we can use the val() method.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#txtName").val());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <input type="text" id="txtName">
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

You have to admit, it's definitely shorter! I know it's different syntax, but you are doing some really cool stuff here.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/cfK9I95BYsw" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="changetext" class="tabcontent">
<div class="tabhtml" markdown="1">

So, what about if you want to change the text of a tag in the DOM?  Before, we used the equal sign and changed the innerHTML, now we can change it by passing a parameter into the method.  For example, we can do something like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                $("#infoid").text("I am a changed man!");
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/X89m1dnVe5o" frameborder="0" allowfullscreen></iframe></div>

I can do that with the html() and val() methods as well. Now, that is good stuff!  Keep in mind, there are a lot more things we can do with jQuery, but I wanted to just introduce you to the concept this week and then we will go into more functionality next week.

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

Click on "Edit on CodePen" to edit and work with the code.

#### text()

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="poNpEQd" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery text()">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/poNpEQd">
  jQuery text()</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### html()

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="KKNZgbX" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery html()">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/KKNZgbX">
  jQuery html()</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### val()

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="YzpYGBz" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery val()">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/YzpYGBz">
  jQuery val()</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>
