---
title: Phaser.io Part 2
module: 12
jotted: true
---

# Phaser.io Part 2

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/mKbaClVmG0U" frameborder="0" allowfullscreen></iframe></div>

In this next second section, we will pre-load all the image assets.  Let's take a look:

```html
<!doctype html> 
<html lang="en"> 
<head> 
    <meta charset="UTF-8" />
    <title>Making your first Phaser 3 Game - Part 2</title>
    <script src="https://cdn.jsdelivr.net/npm/phaser@3.11.0/dist/phaser.js"></script>
    <style type="text/css">
        body {
            margin: 0;
        }
    </style>
</head>
<body>

<script type="text/javascript">

    var config = {
        type: Phaser.AUTO,
        width: 800,
        height: 600,
        scene: {
            preload: preload,
            create: create,
            update: update
        }
    };

    var game = new Phaser.Game(config);

    function preload ()
    {
        this.load.image('sky', 'assets/sky.png');
        this.load.image('ground', 'assets/platform.png');
        this.load.image('star', 'assets/star.png');
        this.load.image('bomb', 'assets/bomb.png');
        this.load.spritesheet('dude', 'assets/dude.png', { frameWidth: 32, frameHeight: 48 });
    }

    function create ()
    {
    }

    function update ()
    {
    }

</script>

</body>
</html>
```

So, this is just like preload images in JavaScript or even in P5 if you remember that!