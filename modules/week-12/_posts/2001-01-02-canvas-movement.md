---
title: Canvas Movement
module: 11
jotted: true
---

# Canvas Movement

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/58CftynH-2Y" frameborder="0" allowfullscreen></iframe></div>

What about moving our element on the canvas? Do you remember how? Let's start with this.

```html
<html>
    <head>
        <title>Canvas</title>
        <style>
            #myCanvas{
                border:black;
                border-style: solid;
                border-width: 2px;
            }
        </style>
    </head>
   
    <body>
        <canvas id="myCanvas" height="600" width="800"></canvas>
        <script>
            var canvas = document.getElementById("myCanvas");
            var ctx = canvas.getContext("2d");
            var x = 50;
            var y = 50;
            ctx.fillStyle = "#0000FF";
            drawSquare();
            setInterval(update, 1000);

            function update()
            {     
                drawSquare();
            }

            function drawSquare()
            {
                ctx.fillRect(x, y, 20, 20);
            }

        </script>
    </body>
</html>
```

Recall, the implementation of Key Events use the following jQuery events.

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

Now, you need to add the key events to make sure you can move the square around.  Give it a try!

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="xxRNxRN" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Week 11 Canvas Square">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/xxRNxRN">
  MART 441 Week 11 Canvas Square</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>