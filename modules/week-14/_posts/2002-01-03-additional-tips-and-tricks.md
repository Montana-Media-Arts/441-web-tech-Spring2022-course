---
title: Additional Tips and Tricks
module: 13
jotted: true
---

# Additional Tips and Tricks



If you are interested in pursuing threejs further, here is a resource providing some tips and tricks on making your threejs projects even more interesting.

## Beginner Friendly Tips, or Help! Why Can’t I See Anything?
You’ve followed a couple of basic tutorials, and everything worked fine, but now you’re creating your app, and you’ve set everything up exactly as the tutorial says. But you just can’t see anything! WTH??

Here’s a couple of things you can do to figure out the problem.

1. Check the browser console for error messages
But you already did that, right?

2. Set the background color to something other than black
Staring at a black canvas? It’s hard to tell whether something is happening or not if all you can see is black. Try setting the background color to red:

```js
scene.background = new THREE.Color( 'red' );
```

If you get a red canvas, that’s a means that your renderer.render calls are working, and you can move on to figuring out what else is wrong.

3. Make sure that you have light in your scene and that it’s illuminating your objects
Just like in the real world, most materials in three.js need light to be seen. One exception is the MeshBasicMaterial, so you can temporarily override all the materials in your scene to see whether this is your problem.

```js
scene.overrideMaterial = new THREE.MeshBasicMaterial( { color: 'green' } );
```

4. Is your object is within the camera’s viewing frustum?
If your object is not inside the viewing frustum, it will get clipped. Try making your far clipping plane big:

```js
camera.far = 100000;
camera.updateProjectionMatrix();
```

Remember, this is just for testing, though! The camera’s frustum is measured in meters, and you should make it as small as possible for the best performance.

5. Is your camera inside the object?
By default, everything gets created at the point (0,0,0)(0,0,0), AKA the origin. Make sure you have moved your camera back so that you can see your scene!

```js
camera.position.z = 10;
```

6. Think carefully about the scale of your scene
Try to visualize your scene, and remember that one unit in three.js is one meter. Does everything fit together in a reasonably logical manner?

## General Tips

Object creation in JavaScript is expensive, so don’t create objects in a loop. Instead, create a single object such as a Vector3 and use vector.set() or similar methods inside your loop.

The same goes for your render loop - make sure you are doing as little work as possible in your render loop since you want it to run smoothly 60 times per second.

Always use BufferGeometry instead of Geometry, it’s faster
The same goes for the pre-built objects, always use the buffer geometry version (BoxBufferGeometry rather than BoxGeometry)

Always try to reuse objects such as objects, materials, textures, etc. (bearing in mind updating some things may be slow, see texture tips below)

### Work in SI Units

three.js is developed using SI units. If you stick with this convention, you will find things more manageable, and if you break it, then make sure that you do so for a good reason!

### Distance is measured in meters (1 three.js unit = 1 meter)

### Time is measured in seconds

Light is measured in SI light units, Candela (cd), Lumen (lm), and Lux (lx)
If you are creating things on a truly epic scale (space simulations and things like that), either uses a scaling factor or switch to using a logarithmic depth buffer.

## Accurate Colors

For (nearly) accurate colors, use these settings for the renderer:

```js
renderer.gammaFactor = 2.2;
renderer.gammaOutput = true;
```

Then for colors do this:

```js
const color = new Color( 0x800080 );
color.convertSRGBToLinear();
```

Or, in the more common case of using a color in a material:

```js
const material = new MeshBasicMaterial( { color: 0x800080 } );
material.color.convertSRGBToLinear();
```

Finally, to get (nearly) correct colors in your textures, you’ll need to set the texture encoding for the color, environment, and emissive maps only:

```js
const colorMap = new TextureLoader().load( 'colorMap.jpg' );
colorMap.encoding = sRGBEncoding;
```

All other map types should remain in linear color space, so don’t change them!

Note that I’m saying nearly correct here since three.js color management is not correct at the moment. Hopefully, it will be fixed soon, but in the meantime, the difference in color will be so minor that it’s doubtful anybody will notice unless you are doing scientific or medical renderings.

## JavaScript

The JavaScript engines used by web browsers change frequently and do an amazing amount of optimization of your code behind the scenes. Don’t trust your intuition about what will be faster, always test. Don’t trust articles from a few years ago telling you to avoid specific methods such as array.map or array.forEach. Test it for yourself.

## Models, Meshes and Other Visible Thing

Avoid using standard text-based 3D data formats, such as Wavefront OBJ or COLLADA, for asset delivery. Instead, use formats optimized for the web, such as glTF
use Draco mesh compression with glTF

If you need to make large groups of objects visible and invisible (or add/remove them from your scene), consider using Layers for best performance.

Objects in the same position cause flickering. Try offsetting things by a tiny amount like 0.0010.001 to make things look like they are in the same position, but keep your GPU happy.

Keep your scene centered around the origin to prevent floating point errors at astronomical coordinates

Never move your Scene object. It gets created at (0,0,0)(0,0,0), and this is the default frame of reference for all the objects inside it.

## Camera

Make your frustum as small as possible for better performance. It’s fine to use a large frustum in development, but once you are fine-tuning your app for deployment, make your frustum as small as possible to gain a few FPS.

Don’t put things right on the far clipping plane (especially if your far clipping plane is vast); this can cause flickering

## Renderer

* Don’t enable preserveDrawingBuffer unless you need it
* Disable the alpha buffer unless you need it
* Don’t enable the stencil buffer unless you need it
* Disable the depth buffer unless you need it (but you probably do need it)
* use powerPreference: "high-performance" when creating renderer. This may make a user's system choose the high-performance GPU, in multi-GPU systems.
* Consider only rendering when the camera position changes by epsilon or when an animation happens
* If your scene is static and uses OrbitControls, you can listen for the change event to only render when the camera moves:

```js
OrbitControls.addEventListener( 'change', () => renderer.render( scene, camera ) );
```

You won’t get a higher frame rate from the last two, but what you will get is fewer laptop fans switching on, and less battery drain on mobile devices.

Note: I’ve seen a few places around the web recommending that you disable antialiasing and apply for a post-processing AA pass instead. In my testing, this is not true. On modern hardware, built-in MSAA seems to be extremely cheap even on low-power mobile devices, while the post-processing FXAA or SMAA passes cause a considerable frame drop.

## Lights

Lights, especially SpotLight, PointLight, DirectionalLight are slow. Use as few lights as possible in your scenes

Avoid adding and removing lights from your scene, since this requires the WebGLRenderer to recompile all shader programs (it does cache the programs so subsequent times that you do this, it will be faster than the first)

Turn on renderer.physicallyCorrectLights for proper lighting that uses the SI units.

## Shadows

If your scene is static, only update the shadow map when something changes, rather than every frame.

Use a CameraHelper to visualize the shadow camera’s viewing frustum
Remember that point light shadows are more expensive than other shadow types since they must render six times (once in each direction), compared with a single time for DirectionalLight and SpotLight shadows

While we’re on the topic of PointLight shadows, note that the CameraHelper only visualizes one out of six of the shadow directions when used to visualize point light shadows. It’s still useful, but you’ll need to use your imagination for the other five directions

## Materials

The built-in three.js materials have a simple performance/quality tradeoff:

* MeshStandardMaterial highest quality/slowest
* MeshPhongMaterial
* MeshLambertMaterial
* MeshBasicMaterial lowest quality/fastest
* Use the best quality material you can afford, and switch to lower quality materials when you need to.

MeshLambertMaterial doesn’t work for shiny materials, but for matte materials like cloth it will give very similar results to MeshPhongMaterial but is faster
If you are using morph targets, make sure you set morphTargets = true in your material, or they won’t work!

The same goes for morph normals.

And if you’re using a SkinnedMesh for skeletal animations, make sure that material.skinning = true

Materials used with morph targets, morph normals, or skinning can’t be shared. You’ll need to create a unique material for each skinned or morphed mesh (material.clone() is your friend here).

## Custom Materials

Only update your uniforms when they change, not every frame.

## Geometry

Avoid the use of line loop since it must be emulated by lines strip

## Textures

All of your textures need to be power of two (POT) size: 1, 2, 4, 8, 16, …, 512, 2048, …1,2,4,8,16,…,512,2048,…

Don’t change the dimensions of your textures. Create new ones instead; it’s faster

Use the smallest texture sizes possible (can you get away with a 256x256 tiled texture? You might be surprised!)

Non-power-of-two (NPOT) textures require linear or nearest filtering, and clamp-to-border or clamp-to-edge wrapping. Mipmap filtering and repeat wrapping are not supported. But seriously, just don’t use NPOT textures.

All textures with the same dimensions are the same size in memory so that JPG may have a smaller file size than PNG, but it will take up the same amount of memory on your GPU

## Post-Processing

The built-in antialiasing doesn’t work with post-processing (at least in WebGL 1). You will need to do this manually, using FXAA or SMAA (probably faster, better)

Since you are not using the built-in AA, be sure to disable it!
three.js has loads of post-processing shaders, and that’s just great! But remember that each pass requires rendering your entire scene. Once you’re done testing, consider whether you can combine some of your passes into one single custom pass.

## Disposing of Things

Are you removing something from your scene?

First of all, consider not doing that, especially if you will add it back again later. You can hide objects temporarily using object.visible = false (works for lights too), or material.opacity = 0. You can set light.intensity = 0 to disable a light without causing shaders to recompile.

If you do need to remove things from your scene permanently, read this article first: How to dispose of objects

## Updating Objects in Your Scene?

Read this article: How to update things.

## Performance

set object.matrixAutoUpdate = false for static or rarely moving objects and manually call object.updateMatrix() when their position/quaternion/scale are updated

Transparent objects are slow, use as few transparent objects as possible in your scenes
use alphatest instead of standard transparency if possible, it’s faster
When testing the performance of your apps, one of the first things you’ll need to do is check whether it is CPU bound or GPU bound. Replace all materials with basic material using scene.overrideMaterial (see beginners tips and the start of the page). If performance increases, then your app is GPU bound.

When performance testing on a fast machine, you’ll probably be getting the maximum frame rate of 60fps. Run chrome using open -a "Google Chrome" --args --disable-gpu-vsync fo ran unlimited frame rate.

Modern mobile devices have high pixel ratios as high as 55 - consider limiting max pixel ratio to 2 or 3 on these devices at the expense of some very slight blurring of your scene.

Bake lighting and shadow maps to reduce the number of lights in your scene
If you have the resources and time, use compressed textures. Unfortunately, setting these up for the web is a pain at the moment since there is no one format supported by all devices.

Keep an eye on the number of drawcalls in your scene. A good rule of thumb is fewer draw calls = better performance.

Far away objects don’t need the same level of detail as objects close to the camera. There are many tricks used to increase performance by reducing the quality of the distant object. For example, the LOD (Level Of Detail) object stores different objects for different distances (for example, near, medium, and far). You may also get away with only updating position/animation every 2nd or 3rd frame for distant objects

## Advanced Tips

Don’t use TriangleFanDrawMode; it’s slow.
use geometry instancing when you have hundreds or thousands of similar geometries
Animate on the GPU instead of the CPU, especially when animating vertices or particles (see THREE.Bas for one approach to doing this)

[Reference](https://discoverthreejs.com/tips-and-tricks/)