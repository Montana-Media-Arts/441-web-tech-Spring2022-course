---
title: Classes and Objects Example
module: 5
jotted: true
---

# An Example using Classes and Objects

Let's finish out the Ball class example so that you can see all of this in use.

## Define a Class

First, we need to write our class. We know we want this class to be a digital representation of a "ball", so let's label it as such. This means, our class initially will look like the following;

```js
class Ball {
    constructor() {

    }
}
```

## Consider Object Properties

I would argue the next step is to consider what type of properties a "ball object" needs to exist in our digital world. To do this, we need to define the ball's behavior.

Let's for the purposes of this experience, say this ball will;

- have a solid color
- and of size "20".

This ball will also;

- travel on straight line

These spec's can help us determine the properties the ball will need. We can say that the ball will likely need;

- a color property
- a radius, to describe it size
- a set of position values (X and Y)
- a set of delta values to describe the movement of the ball (dx and dy)

From this, lets assume we will set the delta value randomly within the constructor method, and will pass the color, size, and position properties to the ball when a new one is created.

This might result in the following constructor method;

```js
class Ball {
    constructor( x, y, color ) {
        this.color = color;
        this.size = 20;
        this.posX = x;
        this.posY = y;
        this.dx = 2;
        this.dy = 0;
    }
}
```

## Consider Object Methods

The next step might be to start writing the methods objects of this class may need. Since we are trying to write modular, highly-readable code, we want to try and write methods that do individual, well defined tasks. With that in mind, we can start to describe the following characteristic of balls that we need;

- An ability to print the balls parameters.
- A method to move the ball
- A method to get or set the deltaX value of the ball.

With this in mind, lets write three methods, one for each of the characteristic described above.

#### toString

The first of these we may want to write is the method to display the parameters of the ball.

In this method, we need to grab the ball's size, color, and position properties, so that it can be returned as a string.

```js
toString() {
    let str;
    str = `This ball is ${this.color}, is ${this.size} large, and is currently located at x: ${this.posX}, y: ${this.posY}`;
    return str;
}
```

#### Move the Ball

To move the ball, we are going to write a method like we did on the previous page. This method will grab the X and Y position properties, respectively. It will then add the X and Y delta values to each, and reassign the new value back to the X and Y position properties.

```js
move() {
    this.posX += this.dx;
    this.posY += this.dy;
}
```

#### deltaX Getter Setter

The final methods we will write utilize the special "getter" and "setter" keywords from the class system. These are used to create special ways of getting or setting data.

In this instance we want to get and set the delta values together;

```js
get deltas() {
    return [this.dy, this.dx];
}
set deltas([deltaX, deltaY]) {
    // check that the input parameter is valid
    // if it is, then set deltaX new value
    if ((typeof deltaX) === "number" && (typeof deltaX) === "number") {
        this.dx = deltaX;
        this.dy = deltaY;
    }
}
```

#### Altogether

Altogether, the class definition might look like;


{% highlight js linenos %}
/* Define a Ball Class */
class Ball {
    constructor(x, y, color) {
        this.color = color;
        this.size = 20;
        this.posX = x;
        this.posY = y;
        this.dx = 2;
        this.dy = 0;
    }

    toString() {
        let str;
        str = `This ball is ${this.color}, is ${this.size} large, and is currently located at x: ${this.posX}, y: ${this.posY}`;
        return str;
    }

    move() {
        this.posX += this.dx;
        this.posY += this.dy;
    }

    get deltas() {
        return [this.dy, this.dx];
    }
    set deltas([deltaX, deltaY]) {
        // check that the input parameter is valid
        // if it is, then set deltaX new value
        if ((typeof deltaX) === "number" && (typeof deltaX) === "number") {
            this.dx = deltaX;
            this.dy = deltaY;
        }
    }
}
{% endhighlight %}

# Creating and Using a Ball Object

To create and use a Ball object in JS, we will need to;

- create a variable namespace to store a reference to the object in
- create a new object and store it in the variable namespace
- call the object's methods


#### Create a Variable Namespace

The first thing, according to our list above, is to create a variable to store a reference to the object in.

```js
let ball;
```

#### Create a New Ball Object

Next, we will create a new Ball object and then bind this object to `ball`. Also, we have four parameters that we need to pass to the Ball's constructor function. Again these are; `x` and `y` position, `size`, and `color`.

```js
ball = new Ball( 0, 0, 'red' );
```

#### Call the Ball's Methods

Finally, we can use our ball object.


> Look how simple and clean that code below looks! It is so easy to read and understand. By abstracting the ball into a class, we can create a ball object, that we call simple instructions on. Each one makes sense and is readable!


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url: "https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/05/classes-example/classes-example-01.js"
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 69 } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/05/classes-example.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/441-WebTech/blob/master/lecture_code/05/classes-example/classes-example-01.js) |
