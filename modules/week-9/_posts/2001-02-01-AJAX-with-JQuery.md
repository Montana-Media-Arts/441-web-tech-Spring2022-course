---
title: AJAX with jQuery
module: 9
jotted: false
---

# AJAX with jQuery

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>

  <button class="tablinks" onclick="openTab(event, 'jqueryexample')">jQuery Example</button>

  <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>


</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

The previous examples were a little more complicated, wouldn't you agree?  How does JQuery help us with that?

Let's look at an example:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("#bikeInformation").load("bikeInfo.txt");
            });
        });
    </script>
</head>

<body>
    <div id="bikeInformation">Nothing yet</div>
    <button>Get Bike Information</button>
</body>

</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/hX2sMTCjOxA" frameborder="0" allowfullscreen></iframe></div>

The basic syntax of the JQuery AJAX call looks like this.

`$(selector).load(URL,data,callback);`

</div>
</div>

<div id="jqueryexample" class="tabcontent">
<div class="tabhtml" markdown="1">

The previous code shows how we can access elements using the jQuery selector, load some data from a URL, send data parameters, which are optional, and then add an optional callback function when the load is complete.

So, we could do something like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("#bikeInformation").load("bikeInfo.txt", fadeText);
            });
        });

        function fadeText()
        {
            $("#bikeInformation").fadeOut("slow").fadeIn("slow");
        }
    </script>
</head>

<body>
    <div id="bikeInformation"></div>
    <button>Get Bike Information</button>
</body>

</html>
```
Here we execute a function after the data is retrieved and displayed.  Cool eh?

There are even more jQuery functions that you can use, but I will refer you to W3Schools to check them out.

<a href="https://www.w3schools.com/jquery/jquery_ref_ajax.asp" target="_new">W3Schools JQuery AJAX</a>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/m57TJlG7J_g" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

#### jQuery and AJAX

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="zYoLwQp" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="AJAX - jQuery Example">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/zYoLwQp">
  AJAX - jQuery Example</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### jQuery, AJAX, Callbacks

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="MWbBmMm" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery, AJAX, Callbacks">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/MWbBmMm">
  jQuery, AJAX, Callbacks</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



</div>
</div>
