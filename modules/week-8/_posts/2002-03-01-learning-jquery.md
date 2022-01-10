---
title: Learning jQuery
module: 8
jotted: false
---

# Learning jQuery

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
<button class="tablinks" onclick="openTab(event, 'example')">Example</button>
<button class="tablinks" onclick="openTab(event, 'other')">Other Methods</button>
<button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>

</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

Previously, we looked at the basics of accessing items through the DOM. What other functions are available to us?  We looked at toggle.  Below are even more methods.

Methods:

1. fadeIn()
2. fadeOut()
3. fadeToggle()
4. fadeTo()
5. slideDown()
6. slideUp()
7. slideToggle()
8. animate()

So, how do they function?

</div>
</div>

<div id="example" class="tabcontent">
<div class="tabhtml" markdown="1">

Here is an example:

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
                $(".myGreatClass").fadeOut();
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/uO4Qxymj26w" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="other" class="tabcontent">
<div class="tabhtml" markdown="1">

Now, try some of these other methods and see what happens.  Just replace fadeOut with the name of the function you want to try.

What about animate?  It is a little different than the other methods listed above.  Let's look at it closer.

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
                $(".myGreatClass").animate({left: '250px'});
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red;position:absolute; top: 100px; left: 25px">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

Again, we are just updating the style of this particular tag, but in a cooler way by adjusting its left property.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/72rOPWTTiYA" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

Click on "Edit on CodePen" to edit and work with the code.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="ZEBvOqp" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery Example 2">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/ZEBvOqp">
  jQuery Example 2</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>
</div>
