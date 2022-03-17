---
title: Set up files
module: 13
jotted: true
---

# Set up

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>

  <button class="tablinks" onclick="openTab(event, 'Sections')">Sections</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

The first thing we need to do is to make sure we have the correct setup.  Here is an example of a potential HTML file.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>My first three.js app</title>
        <style>
            body { margin: 0; }
            canvas { display: block; }
        </style>
    </head>
    <body>
        <script src="js/three.js"></script>
        <script>
            // Our Javascript will go here.
        </script>
    </body>
</html>
```

Notice, the three.js file is in the js folder.  Just make sure you reference your folder.

</div>
</div>
<div id="Sections" class="tabcontent">
<div class="tabhtml" markdown="1">

There are three main parts to a threejs file. 

* scene
* camera
* renderer

I assume you have heard and used these terms before. Hopefully, this section won't be too much a stretch.  Here the beginning code.  The following code goes in your js file or between your script tags.  It's up to you.

```js
var scene = new THREE.Scene();
var camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

var renderer = new THREE.WebGLRenderer();
renderer.setSize( window.innerWidth, window.innerHeight );
document.body.appendChild( renderer.domElement );
```

The first line creates the scene by accessing the threejs library and then sets the camera. Then, the next instantiates the renderer.  Keep in mind; it must use WebGL to render anything in 3D, which is no different than p5 or processing if you remember from Creative Coding 1.  I bet you never thought that would come back!

If you run this, you should see a black screen. Not too exciting, is it?  

So, where do we go from here?
</div>
</div>
<div id="ToDo" class="tabcontent">
<div class="tabhtml" markdown="1">
So, what does this look like when it's all together.  Check out this CodePen and make changes if you want.

<p class="codepen" data-height="358" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="vYggmZm" style="height: 158px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Initial threejs">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/vYggmZm">
  Initial threejs</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>