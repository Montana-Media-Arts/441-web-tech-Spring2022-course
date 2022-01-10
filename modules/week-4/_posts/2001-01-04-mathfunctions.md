---
title: Math Functions
module: 4
jotted: true
---

# Math Functions
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'random')">Math.random</button>
  <button class="tablinks" onclick="openTab(event, 'abs')">Math.abs</button>
  <button class="tablinks" onclick="openTab(event, 'pi')">Math.PI</button>
  <button class="tablinks" onclick="openTab(event, 'round')">Math.round</button>
  <button class="tablinks" onclick="openTab(event, 'pow')">Math.pow</button>
  <button class="tablinks" onclick="openTab(event, 'sqrt')">Math.sqrt</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
The nice thing about most languages and JavaScript is no different is that there are built-in functions to help us to perform actions and we don't have to worry about creating them ourselves.  What is the Math class?

The Math class is a class built by someone else and is automatically available to us by just making a call to math.  What does this look like?
</div>

<div id="random" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Random
The beautiful thing about most languages and JavaScript is no different is that there are built-in functions to help us to perform actions, and we don't have to worry about creating them ourselves.  What is the Math class?

The Math class is a class built by someone else and is automatically available to us by just making a call to math.  Some of the functions are listed below.

Random is one of the most common math functions used because coming up with random numbers is hard to do.  So, how does one use random?

They work something like this:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getARandomNumber()
            {
                    document.write(Math.random());
            }
        </script>
    </head>
    <body>
        <script>
            getARandomNumber(); // remember I am calling my method here
        </script>
    </body>
</html>
```
What did you get when you ran it?  Did you get an integer or a whole number (one without decimal points) or a double (one with decimal points)?

You should see a double.  That is because random returns a number between 0 and 1.  It includes 0, so theoretically, you can get zero, but it goes up to 1, which means it never gets to one.  Another way to put it is that it is inclusive of 0 and exclusive of 1.  So, what if we want whole numbers?

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getARandomNumber()
            {
                var randNumber = Math.random();
                document.write(Math.floor(randNumber * 10));
            }
        </script>
    </head>
    <body>
        <script>
            getARandomNumber(); // remember I am calling my method here
        </script>
    </body>
</html>
```
This time, we are adding a couple of new things.  First, look at the Math.random() - we know that returns something between 0 and 1.  Then, we multiply it by 10. So, if Math.random() returns .83302 and we multiply it by 10, then we should have 8.3302.  However, it's still a double or decimal number.  So, we have to use another method in the Math class called the floor method.  This method returns the whole number rounding down.

You can prove it to yourself by running the following example:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getARandomNumber()
            {
                var randNumber = Math.random();
                document.write("actual: " + randNumber + "<br>");
                document.write(Math.floor(randNumber * 10));
            }
        </script>
    </head>
    <body>
        <script>
            getARandomNumber(); // remember I am calling my method here
        </script>
    </body>
</html>
```

You may have to refresh a few times, but you should see it.

Now, what about if you want a range.  Like I want a random number between 5-10?

You might consider creating a method like this.

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getARandomNumber(min, max)
            {
                return Math.floor(Math.random() * (max - min + 1) ) + min;
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getARandomNumber(5,10)); // remember I am calling my method here
        </script>
    </body>
</html>
```

If you read through this code, we are getting a number between 5 and 10 because we subtract five from 10, which gives us 5.  Then, we add one which provides us with 6. Then, we take six and multiply it by whatever is returned by Math.random(), which means it could be between 0 and up to 6 (but not quite! So we get five because of the Math.floor).  Then, we add five, and that should give us something between 5 and 10.  Pretty cool, huh?  

Oh, yes, and one more thing.  There is a **return** in the method getARandomNumber.  This time, nothing prints in the function, but the results return from the function and printed.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/2h1crDRLVn0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

What other methods are there?
</div>
</div>
<div id="abs" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Math.abs

Math.abs is a good one to have in your back pocket as it gives you the absolute value between two numbers.  That means if you subtract two numbers and take the absolute value, it will always be positive.

For example:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getAbsoluteValue(number1,number2)
            {
                return Math.abs(number1-number2);
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getAbsoluteValue(5,10)); // remember I am calling my method here
        </script>
    </body>
</html>
```

So, you can see even though 5-10 is -5, because of the absolute value, it returns 5.  This method is convenient when you need to know the difference between two numbers, like when you need to know the distance between two points.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/wqFoSl8cDDk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Are there any others that are useful?  How about Math.PI?
</div>
</div>
<div id="pi" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Math.PI

What is PI?  PI is a distinctive number.  As stated by piday.org - "Pi (π) is the ratio of a circle's circumference to its diameter. PI is a constant number, meaning that for all circles of any size, PI will be the same."

[Learn More](https://www.piday.org/learn-about-pi/)

It is handy when trying to figure out which direction players should turn in games.  To get Pi, we don't have to memorize it; we can use Math.PI, and it will return a value for us.  There is no end, so users typically stop at a certain point.

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getPI()
            {
                return Math.PI;
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getPI()); // remember I am calling my method here
        </script>
    </body>
</html>
```
<br />

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/hLwKsR7YX-E" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Another handy method is the round method.
</div>
</div>
<div id="round" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Math.round

Math.round performs rounding for you, so you don't have to create an if statement that says if a number is five or above, round up, otherwise, round down.  Here is an example:


```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getRound(number)
            {
                return Math.round(number);
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getRound(3.943232)); // remember I am calling my method here
        </script>
    </body>
</html>
```

In this case, it will return 4, and if you were to change the .9 to something below 5, then it will return 3.  

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/IN8tjxH8cuc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Another method that you might need is Math.pow.
</div>
</div>
<div id="pow" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Math.pow

So, the power function is quite useful because there isn't an operator for it in basic math.  In your prior math classes (I am not sure how long it's been), you probably saw something like this ^ for power.  It was maybe on your calculator.  However, in programming, that means something completely different so, you have to use the Math.pow so that you can raise a number to a power.  For example, you may have two raised to the three power, which should return 8.

Here's an example:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getPower(number, power)
            {
                return Math.pow(number, power);
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getPower(2,3)); // remember I am calling my method here
        </script>
    </body>
</html>
```
<br />

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/zhBhAzROKN4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

The last one we will look at for now is the Math.sqrt.
</div>
</div>
<div id="sqrt" class="tabcontent" >
<div class="tabhtml" markdown="1">

## Math.sqrt

When we square a number like 2*2, we get 4.  But what about the square root?  To do that, we would have to do a lot more programming that is necessary, so we use the Math.sqrt and that will take the square root of a number and return the value.  For example, Math.sqrt(4) = 2.

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function getSquareRoot(number)
            {
                return Math.sqrt(number);
            }
        </script>
    </head>
    <body>
        <script>
            document.write(getSquareRoot(16)); // remember I am calling my method here
        </script>
    </body>
</html>
```

When you ran this code, what did you get?  Did you get 4?  Good!

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/YJkL-faZbjU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

That's it for this week. Let's do some more hand-on work and your homework.  As always, let me know if you have more questions!
</div>
</div>
<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">

Please feel free to experiment with the code from the other tabs.

Click on **Edit on CodePen** to experiment.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="result" data-user="retrog4m3r" data-slug-hash="OJbJLvb" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Workspace">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/OJbJLvb">
  MART 441 Workspace</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

That's it for this week.  Let's do some more hand-on work and your homework.  As always let me know if you have more questions!
</div>
</div>