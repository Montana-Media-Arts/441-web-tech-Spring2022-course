---
title: Canvas Classes
module: 11
jotted: true
---

# Class and Object Review

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/hu9PQ4JYwzI" frameborder="0" allowfullscreen></iframe></div>

And we are back in this!  How do we create classes and objects again? Start with this.

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
Then, create a class that might look like this.

```js
class Square
{
    constructor(x,y,w,h)
    {
        this.x = x;
        this.y = y;
        this.w = w;
        this.h = h;
    }

    get theX()
    {
        return this.x;
    }

    get theY()
    {
        return this.y;
    }

    get theW()
    {
        return this.w;
    }

    get theH()
    {
        return this.h;
    }
}

```
Now, use the Square class and then use the fillRect above using the object you create.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="xxRNxRN" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Week 11 Canvas Square">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/xxRNxRN">
  MART 441 Week 11 Canvas Square</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Using your **object** and your **key events**, make sure you can update your object properties and move the square.  



<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="xxRNxRN" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Week 11 Canvas Square">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/xxRNxRN">
  MART 441 Week 11 Canvas Square</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>