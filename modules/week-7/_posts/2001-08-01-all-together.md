---
title: Classes and Objects Example
module: 7
jotted: true
---

# An Example using Classes and Objects

<div class="tab">
    <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
    <button class="tablinks" onclick="openTab(event, 'define')">Define</button>
    <button class="tablinks" onclick="openTab(event, 'functions')">Functions</button>
    <button class="tablinks" onclick="openTab(event, 'three')">Three Functions</button>
     <button class="tablinks" onclick="openTab(event, 'getset')">Get/Set</button>
      <button class="tablinks" onclick="openTab(event, 'together')">Together</button>
       <button class="tablinks" onclick="openTab(event, 'create')">Create</button>
    <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

Let's finish out the Person class example so that you can see all of this in use.

</div>
</div>

<div id="define" class="tabcontent">
<div class="tabhtml" markdown="1">

## Define a Class

First, we need to write our class. We know we want this class to be a digital representation of a "person", so let's label it as such.  Our class initially looks like the following;

```js
class Person {
    constructor() {

    }
}
```

</div>
</div>

<div id="properties" class="tabcontent">
<div class="tabhtml" markdown="1">

## Consider Object Properties

So, we should also consider what a person can do.  That is what we did in the previous section. They could walk and get the timeToTravel.

For our example, let's have our main properties eyeColor and hairColor, and then the methods/functions be walk and timeToTravel.

- eye color that is brown
- hair color that is blonde

The Person will also:

- walk
- get the time to travel a certain distance

These specifications can help us determine the properties the Person will need. We can say that the Person will likely need;

- an eye color property
- a hair color property
- a walking speed property
- a distance property

Below is the following constructor.

```js
class Person {
    constructor( eyeColor, hairColor, speed, distance ) {
        this.eyeColor = eyeColor;
        this.hairColor = hairColor;
        this.speed = speed;
        this.distance = distance;
    }
}
```

</div>
</div>

<div id="functions" class="tabcontent">
<div class="tabhtml" markdown="1">

## Consider Object Functions

The next step might be to start writing the functions that this class may need. Since we are trying to write modular, highly-readable code, we want to try and write functions that do individual, well-defined tasks. With that in mind, we can think about what people can do.

- Want to see the properties of the Person.
- A walking function
- A time to travel function.

With this in mind, let's write three functions.

</div>
</div>

<div id="three" class="tabcontent">
<div class="tabhtml" markdown="1">

#### toString

The first of these we may want to write is the function to display the parameters of the Person. toString is the most common function in any language.  You can find this function in most Object-Oriented programming languages.

In this function, we need to access the Person's eyeColor, hairColor, speed, and distance properties and returned as a string.

```js
toString() {
    let str;
    str = `This person has ${this.eyeColor} eyes, has ${this.hairColor} hair, and is currently moving at ${this.speed} miles per hour.`;
    return str;
}
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/ZsP8v5D1ur4" frameborder="0" allowfullscreen></iframe></div>

#### Person walking

To walk, the Person will need a walking function.

```js
walk() {
    return `I am walking across the tundra at ${this.speed} miles per hour`;
}
```

#### Time to travel function

We may also want to know how long it takes them to travel a certain distance, so we would have a timeToTravel function to calculate this.

```js
timeToTravel()
{
    let time = this.distance/this.speed;
    return time;
}
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/G8zPtAv139U" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="getset" class="tabcontent">
<div class="tabhtml" markdown="1">

#### Getters and Setters

Remember when we were talking about changing the values of our properties directly and how that wasn't the best idea?  We want to use getters and setters -- these are special functions -- to make those changes for us.  It helps keep better control over who and when properties are changed. This technique is called **encapsulation**.  It just means we want the class to make changes to our properties, not the outside world.  So, we give access through getters and setters.

An example would be something like this:

```js
    get eColor() {
        return this.eyeColor;
    }
    set eColor(eyeColor) {
        this.eyeColor = eyeColor;
    }
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/jxKCJP51Rl8" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="together" class="tabcontent">
<div class="tabhtml" markdown="1">

#### Altogether

Altogether, the class definition might look like;


```js

class Person {
    constructor( eyeColor, hairColor, speed, distance ) {
        this.eyeColor = eyeColor;
        this.hairColor = hairColor;
        this.speed = speed;
        this.distance = distance;
    }
    get eColor() {
        return this.eyeColor;
            }
    set eColor(eyeColor) {
        this.eyeColor = eyeColor;
    }
   walk() {
        return `I am walking across the frozen tundra at ${this.speed} miles per hour`;
    }
    timeToTravel()
    {
        let time = this.distance/this.speed;
        return time;
    }
    toString() {
        let str;
        str = `This person has ${this.eyeColor} eyes, has ${this.hairColor} hair, and is currently moving at ${this.speed} miles per hour.`;
        return str;
    }
}
```

</div>
</div>

<div id="create" class="tabcontent">
<div class="tabhtml" markdown="1">

# Creating and Using a Person Object

To create and use a Person object in JS, we will need to;

- create a variable to store a reference to the object in
- create a new object and store it in the variable
- call the object's functions


#### Create a Variable

First, created a variable for which to store a reference to the object.

```js
let myPerson;
```

#### Create a new Person Object

Next, we will create a new Person object and then bind this object to `myPerson`. Also, we have four parameters that we need to pass to the Person's constructor function. Again these are; `eyeColor`, `hairColor`, `speed`, and `distance`.

```js
myPerson = new Person( 'blue', 'brown',3,10);
```

#### Call the Person's functions

Finally, we can use our Person object.


Look how clean and straightforward that code below looks! It is so easy to read and understand. By abstracting the Person into a class, we can create a person object that we can call the functions from each of those objects. Each one makes sense and is readable!

```html
<html>
<head>
    <title>OOP</title>
    <script>
        class Person {
        constructor( eyeColor, hairColor, speed, distance ) {
            this.eyeColor = eyeColor;
            this.hairColor = hairColor;
            this.speed = speed;
            this.distance = distance;
        }
            get eColor() {
                return this.eyeColor;
            }
            set eColor(eyeColor) {
                this.eyeColor = eyeColor;
            }
            walk() {
                return 'I am walking across the frozen tundra at ' + this.speed + ' miles per hour';
            }
            timeToTravel()
            {
                let time = this.distance/this.speed;
                return "It will take approximately " + 
                Math.round(time) + " hours to cover " + this.distance + " miles.";
            }
            toString() {
                let str;
                str = 'This person has ' + 
                this.eyeColor + ' eyes, has '
                + this.hairColor +
                ' hair, and is currently moving at ' + 
                this.speed + ' miles per hour.';
                return str;
            }
        }

        function createAndShow()
        {
            let myPerson = new Person( 'blue', 'brown',3,10);
            document.getElementById("myWalk").innerHTML = myPerson.walk();
            document.getElementById("myTimeToTravel").innerHTML = myPerson.timeToTravel();
            document.getElementById("myPerson").innerHTML = myPerson.toString();    
        }
    </script>
</head>
<body>
    <div id="myWalk"></div>
    <div id="myTimeToTravel"></div>
    <div id="myPerson"></div>
    <script>
        createAndShow();   
    </script>
</body>
</html>
```
<br/>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/hf-z7przdp0" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="VwmbOVq" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Classes and Objects - Full Example">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/VwmbOVq">
  Classes and Objects - Full Example</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

</div>
</div>
