---
title: HTML5 Key Events
module: 10
jotted: true
---

# Key Events

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'keyevents')">Key Events</button>
  <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
  <button class="tablinks" onclick="openTab(event, 'hint')">Hint</button>
  <button class="tablinks" onclick="openTab(event, 'todo2')">To Do</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/SkXtDH2aGwI" frameborder="0" allowfullscreen></iframe></div>

In the last section, we looked at moving items across the screen. If you can do that, then you can move something with a key event too. Let's use our code from before to draw a blue square:

```html
<html>
    <head>
        <title>Canvas</title>
    </head>
    <style>
        #myCanvas{
            border:black;
            border-style: solid;
            border-width: 2px;
            
        }
    </style>
    <body>
        <canvas id="myCanvas" height="600" width="800"></canvas>

        <script>
            var canvas = document.getElementById("myCanvas");
            var ctx = canvas.getContext("2d");
            var x = 50;
            var y = 50;
            ctx.fillStyle = "#0000FF";
            drawSquare();
            
            function drawSquare()
            {
                ctx.clearRect(0,0,800,600);
                ctx.fillRect(x, y, 20, 20);
            }

        </script>
    </body>
</html>
```

</div>
</div>

<div id="keyevents" class="tabcontent">
<div class="tabhtml" markdown="1">

## KeyEvents

Should we use WASD or arrows?  Or both?  Let's start with WASD.

You may recall that all keys (input) have to get translated for the computer to understand the keypress.  For example, how do we know when the user presses the M or Q keys? Did you know that the computer maps the keys to a certain number? The computer translates those numbers into 0's and 1's so that it knows what to do with them?  Cool huh?

In JavaScript and jQuery, we have to either use their key's number or try and compare the actual letter.

```javascript
$(document).ready(function(){
    $(this).keypress(function(event){
        getKey(event);
    });
});

function getKey(event)
{
    var char = event.which || event.keyCode;
    var actualLetter = String.fromCharCode(char);
}
```

Remember `this`?  It's back!  The `this` keyword allows us to check for keyEvents on anything that might be on the page.  Then, we can get the keystroke pressed and do something.

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

## You try it out!

How can you use the code above to move the square up?  Don't worry about the other directions (yet).

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="NWbeJgo" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Key Events">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/NWbeJgo">
  MART 441 Key Events</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
Did you get it to move up? Yes?  Good job!

</div>
</div>

<div id="hint" class="tabcontent">
<div class="tabhtml" markdown="1">

#### Need a hint

So, let me ask you this. If I wanted to go up, which letter would I press?  `w` right?  Which value would I need to change? **x** or **y**?  If you answered **y**, you are correct!  What do I need to do to **y** to make the shape move up?  Do I need to **add** to it or **subtract** from it?  Keep in mind that 0,0 is in the upper left-hand corner.  If you answered **subtract** from **y**, you were correct!

So, the function might be like this:

```javascript
function getKey(event)
{
    var char = event.which || event.keyCode;
    var actualLetter = String.fromCharCode(char);
    if(actualLetter == "w")
    {
        moveUp();
    }
    drawSquare();
}

function moveUp()
{
    y-=10;
}
```
Did you notice I put the drawSquare function in after the if statement?  Why did I need to do that?

</div>
</div>

<div id="todo2" class="tabcontent">
<div class="tabhtml" markdown="1">

## You try it out!

Can you put add the other letters? 

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="gOLZEGj" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Key Events - Up">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/gOLZEGj">
  MART 441 Key Events - Up</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Did it work? Yes? Great!

So, what about collisions?  Go to the next section, and we will see about that!
</div>
</div>

