---
title: Add Shapes
module: 13
jotted: true
---

# Add a Cube

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>

  <button class="tablinks" onclick="openTab(event, 'Animate')">Animate</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

Although the black screen is appealing, let's add a shape to our scene.  The following code adds a cube.  Put it at the bottom of your script.

```js
var geometry = new THREE.BoxGeometry();
var material = new THREE.MeshBasicMaterial({
    color: 0x00ff00
});
var cube = new THREE.Mesh(geometry, material);
scene.add(cube);

camera.position.z = 5;
```

Save and take a look at your screen.  Do you see anything?  I don't either!  Dang!

</div>
</div>
<div id="Animate" class="tabcontent">
<div class="tabhtml" markdown="1">

So, how do we make it appear?  We need a little more code to make that happen. We need to animate the shape so that it will appear.

Add the following code under the last line.

```js
function animate() {
    requestAnimationFrame( animate );
    renderer.render( scene, camera );
}
animate();
```

Now, do you see something?  Like a green square?  Great!  Okay, so that is fine, but the whole idea is that we want to know the power of threejs, just see a flat square.  So, above the render line, add these two lines.

```js
cube.rotation.x += 0.01;
cube.rotation.y += 0.01;
```

The final animate method should look like this.

```js
function animate() {
    requestAnimationFrame( animate );
    cube.rotation.x += 0.01;
    cube.rotation.y += 0.01;
    renderer.render( scene, camera );
}
animate();

```

Now, think about this for a second.  It's just rotating on its own. That's pretty darn cool.  We didn't have to create a timer or use a jQuery function to animate this.  Since built into the library, it animates the shape.  

What else can we do?  Move on and find out!
</div>
</div>
<div id="ToDo" class="tabcontent">
<div class="tabhtml" markdown="1">

<p class="codepen" data-height="353" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="WNRRjaP" style="height: 153px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Box Shape">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/WNRRjaP">
  MART 441 Box Shape</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>
