---
title: Collisions
module: 12
jotted: true
---

# Collision Review

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/OstFxwJnTI8" frameborder="0" allowfullscreen></iframe></div>

So, remember, we can use this collision method below.

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

You will need to iterate over your array objects each time you move and check to see if you have collided with all the objects on the page.  Give it a try!

<p class="codepen" data-height="600" data-default-tab="html,result" data-slug-hash="wvobajM" data-editable="true" data-user="retrog4m3r" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/wvobajM">
  MART 441 Arrays</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>