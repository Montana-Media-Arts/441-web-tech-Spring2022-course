---
title: HTML5 Collisions
module: 10
jotted: true
---

# HTML5 Collisions

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'createclass')">Create a Class</button>
  <button class="tablinks" onclick="openTab(event, 'twoshapes')">Two Shapes</button>
  <button class="tablinks" onclick="openTab(event, 'movement')">Movement</button>
  <button class="tablinks" onclick="openTab(event, 'collision')">Collision</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/oeTBJ3_05ms" frameborder="0" allowfullscreen></iframe></div>

With any game, you need to be able to handle collisions. We are going to use a simple box collider.  It checks the corners of the boxes to see if they are overlapping.  If they are, then it returns true, else it returns false.  Keep in mind, a collision can be more precise, but it takes more processing because of all the algorithm checks all the points of the shape.  Also, every move checks collision.

Here is our collision code:

```javascript
function hasCollided(object1, object2) {
    return !(
        ((object1.y + object1.height) < (object2.y)) ||
        (object1.y > (object2.y + object2.height)) ||
        ((object1.x + object1.width) < object2.x) ||
        (object1.x > (object2.x + object2.width))
    );
}
```

Now, wait a minute. You might have thought that objects were going away. But what if I told you that you could create an object out of each of your squares (assuming you have at least two).  Then, you can send your objects into this function, and it will check to see if you have collided or not.

</div>
</div>

<div id="createclass" class="tabcontent">
<div class="tabhtml" markdown="1">

## Try it out!

Do you remember how to create a class? Can you create a class called Square with the properties x, y, height, width, and color?  Then, create your constructor and getters and setters.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="OJbrqza" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Class and Canvas">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/OJbrqza">
  MART 441 Class and Canvas</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Check to see if everything is in your objects by writing to the console.  Did it work? Yes? Great job!

</div>
</div>

<div id="twoshapes" class="tabcontent">
<div class="tabhtml" markdown="1">

## Try it yourself!

Can you create two squares and add them to the screen? Make them different colors and different sizes. (I know you can!  The power is in you!).

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="ExNGMRZ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Canvas Multiple Shapes">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/ExNGMRZ">
  MART 441 Canvas Multiple Shapes</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>

<div id="movement" class="tabcontent">
<div class="tabhtml" markdown="1">

## Try it yourself!

Now, can you make the one square move with the KeyEvents using WASD?  Yes, yes, you can!

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="gOLZEjB" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Canvas, Objects, Movement">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/gOLZEjB">
  MART 441 Canvas, Objects, Movement</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>

<div id="collision" class="tabcontent">
<div class="tabhtml" markdown="1">

Look how far you have come!  I am so proud of you!

## Try it yourself!

Now, here comes the new stuff, check for collision.  You can use the code above and check the collision between your two squares each time the first square moves.  Just make sure that the first square can no longer move or have the first square move back a bit from the second square (like a bounce)if they collide or move. It's up to you!

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="BaQvbvE" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Canvas Collision">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/BaQvbvE">
  MART 441 Canvas Collision</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


You did it!  I am proud of you! I knew you could do it!  Is there more?  Of course, there is, but we are going to wait until next week to do more.  Good job this week!

</div>
</div>


    