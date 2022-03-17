---
title: Add Models
module: 13
jotted: true
---

# Add Models

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
<button class="tablinks" onclick="openTab(event, 'Example')">Example</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

threejs also allows you to add models that were created in other applications and exported as glb files.  The following example shows what is required to make the model appear.

```html
    <script src="js/three.js"></script>
    <script src="js/OBJLoader.js"></script>
    <script src="js/TrackballControls.js"></script>
```

</div>
</div>
<div id="Example" class="tabcontent">
<div class="tabhtml" markdown="1">

You need the threejs library of course, but you also need the OBJLoader which is in the examples -> libraries folder as well.

```js
  /**
  * Generate a scene object with a background color
  **/

   function getScene() {
    var scene = new THREE.Scene();
    scene.background = new THREE.Color(0x111111);
    return scene;
  }

  /**
  * Generate the camera to be used in the scene. Camera args:
  *   [0] field of view: identifies the portion of the scene
  *     visible at any time (in degrees)
  *   [1] aspect ratio: identifies the aspect ratio of the
  *     scene in width/height
  *   [2] near clipping plane: objects closer than the near
  *     clipping plane are culled from the scene
  *   [3] far clipping plane: objects farther than the far
  *     clipping plane are culled from the scene
  **/

  function getCamera() {
    var aspectRatio = window.innerWidth / window.innerHeight;
    var camera = new THREE.PerspectiveCamera(75, aspectRatio, 0.1, 1000);
    camera.position.set(0, 90, -10);
    return camera;
  }

  /**
  * Generate the light to be used in the scene. Light args:
  *   [0]: Hexadecimal color of the light
  *   [1]: Numeric value of the light's strength/intensity
  *   [2]: The distance from the light where the intensity is 0
  * @param {obj} scene: the current scene object
  **/

  function getLight(scene) {
    var light = new THREE.PointLight(0xffffff, 1, 0);
    light.position.set(20, 50, 20);
    scene.add(light);

    var ambientLight = new THREE.AmbientLight(0x111111);
    scene.add(ambientLight);
    return light;
  }

  /**
  * Generate the renderer to be used in the scene
  **/

  function getRenderer() {
    // Create the canvas with a renderer
    var renderer = new THREE.WebGLRenderer({antialias: true});
    // Add support for retina displays
    renderer.setPixelRatio(window.devicePixelRatio);
    // Specify the size of the canvas
    renderer.setSize(window.innerWidth, window.innerHeight);
    // Add the canvas to the DOM
    document.body.appendChild(renderer.domElement);
    return renderer;
  }

  /**
  * Generate the controls to be used in the scene
  * @param {obj} camera: the three.js camera for the scene
  * @param {obj} renderer: the three.js renderer for the scene
  **/

  function getControls(camera, renderer) {
    var controls = new THREE.TrackballControls(camera, renderer.domElement);
    controls.zoomSpeed = 0.4;
    controls.panSpeed = 0.4;
    return controls;
  }

  /**
  * Load Skull model
  **/

  function loadModel() {
    var loader = new THREE.OBJLoader();
    loader.load( 'Skull.obj', function ( object ) {
      object.rotation.z = Math.PI;
      scene.add( object );
      document.querySelector('h1').style.display = 'none';
    } );
  }

  /**
  * Render!
  **/

  function render() {
    requestAnimationFrame(render);
    renderer.render(scene, camera);
    controls.update();
  };

  var scene = getScene();
  var camera = getCamera();
  var light = getLight(scene);
  var renderer = getRenderer();
  var controls = getControls(camera, renderer);

  loadModel()

  render();
```

Did you get to see your model?  Great!
</div>
</div>
<div id="ToDo" class="tabcontent">
<div class="tabhtml" markdown="1">

<p class="codepen" data-height="304" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="VwPPWXG" style="height: 104px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 three.js Model">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/VwPPWXG">
  MART 441 three.js Model</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>

