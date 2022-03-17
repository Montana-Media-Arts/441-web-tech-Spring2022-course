---
title: Phaser.io Setup
module: 12
jotted: true
---

# Phaser.io Install

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/HHsKBnSrTKE" frameborder="0" allowfullscreen></iframe></div>


First, go to Phaser.io and download the library.  From there, know that you need a live server to make this work. You can get this as an add-on in Atom and Visual Studio Code.  I won't run correctly otherwise.

## Live Server Instructions

The easiest thing to do is install live server in your editor.  Whenever you try and open your application make sure you choose "Open with Live Server".

![Live Server](../imgs/LiveServerVSCode.png "Live Server VS Code")

![Live Server](../imgs/LiveServerAtom1.png "Live Server Atom Search")

![Live Server](../imgs/LiveServerAtom2.png "Live Server Atom Install")


## Download Phaser.io

<a href="http://phaser.io/tutorials/getting-started-phaser3/part4" target="_new">Download the library</a>

## Assets

Don't forget to get the assets from GitHub.

<a href="https://github.com/photonstorm/phaser3-examples" target="_new">Get the Assets</a>

<a href="https://github.com/Montana-Media-Arts/441-WebTech-Spring2021-Examples" target="_new">Assets for the walkthrough</a>
Put these directly in the assets folder.

## Create a "Hello World!" in Phaser.io

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/xEvFkYvuZmI" frameborder="0" allowfullscreen></iframe></div>

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://cdn.jsdelivr.net/npm/phaser@3.15.1/dist/phaser-arcade-physics.min.js"></script>
</head>
<body>

    <script>
    var config = {
        type: Phaser.AUTO,
        width: 800,
        height: 600,
        physics: {
            default: 'arcade',
            arcade: {
                gravity: { y: 200 }
            }
        },
        scene: {
            preload: preload,
            create: create
        }
    };

    var game = new Phaser.Game(config);

    function preload ()
    {
        this.load.setBaseURL('http://labs.phaser.io');

        this.load.image('sky', 'assets/skies/space3.png');
        this.load.image('logo', 'assets/sprites/phaser3-logo.png');
        this.load.image('red', 'assets/particles/red.png');
    }

    function create ()
    {
        this.add.image(400, 300, 'sky');

        var particles = this.add.particles('red');

        var emitter = particles.createEmitter({
            speed: 100,
            scale: { start: 1, end: 0 },
            blendMode: 'ADD'
        });

        var logo = this.physics.add.image(400, 100, 'logo');

        logo.setVelocity(100, 200);
        logo.setBounce(1, 1);
        logo.setCollideWorldBounds(true);

        emitter.startFollow(logo);
    }
    </script>

</body>
</html>
```

Below is a screenshot of Hello Phaser.

![Phaser Hello World](../imgs/PhaserHello.png "Phaser Hello World")