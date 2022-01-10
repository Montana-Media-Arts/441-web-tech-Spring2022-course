---
title: Control Structures
module: 4
jotted: true
---

# Control Structures 101
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'if')">if</button>
  <button class="tablinks" onclick="openTab(event, 'elseif')">else-if</button>
  <button class="tablinks" onclick="openTab(event, 'switch')">switch</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
Control structures are the decision-makers of the programming world.  We use [relational and logical operators](https://youtu.be/yjg6D7B7ozM) to help the computer decide which path it should take (not that different from a choose your own adventure story - is a relationship!)

Last week, we discussed control structures in a high-level way.  Let's now take a closer look.
</div>
<div id="if" class="tabcontent" >
<div class="tabhtml" markdown="1">

## if statements

If we look at them in JavaScript, they will look like this

```html
<html>
    <head>
        <script>
            // I created a variable here
            var temperature = 30;
            // I am defining my method here
            function whatToDo()
            {
                if(temperature < 40)
                {
                    document.write("Brrr.. put on a sweatshirt!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            whatToDo(); // remember I am calling my method here
        </script>
    </body>
</html>
```

Did you try it out?  It should print out the message.  What happens if it's above 40?  What about if it's equal to 40?

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/bUC0wf7haKw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

The other side of the if statement is the else.  Notice, the block inside of the if only executes if it's true.  However, with the else, we can do something if it's false.  Take a look below.

```html
<html>
    <head>
        <script>
            // I created a variable here
            var temperature = 30;
            // I am defining my method here
            function whatToDo()
            {
                if(temperature < 40)
                {
                    document.write("Brrr.. put on a sweatshirt!");
                }
                else
                {
                    document.write("Yasss!! It's so warm, I can swim in the Clark Fork!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            whatToDo(); // remember I am calling my method here
        </script>
    </body>
</html>
```
There are a couple of things to notice here. In the **else** notice that there are no parentheses.  That's because it's just saying, no matter what, if the if fails, then do whatever is in the else block.  Remember a block is anything that is surrounded by **{ }**

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/agJii1A-ocw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Finally, we can also pass a parameter into our function and then pass that parameter into our if statement.  Please take a look below to see what I mean.

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature)
            {
                if(temperature < 40)
                {
                    document.write("Brrr.. put on a sweatshirt!");
                }
                else
                {
                    document.write("Yasss!! It's so warm, I can swim in the Clark Fork!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            whatToDo(30); // remember I am calling my method here
        </script>
    </body>
</html>
```
Notice that I pass the number 30 into whatToDo, and store it in the temperature variable in the function.  That variable is then used in the if statement.  Keep in mind; we can create a variable down below and pass that in too.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/ilrJ0ZaFnHU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature)
            {
                if(temperature < 40)
                {
                    document.write("Brrr.. put on a sweatshirt!");
                }
                else
                {
                    document.write("Yasss!! It's so warm, I can swim in the Clark Fork!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            // I created a variable here
            var temperature = 30;

            whatToDo(temperature); // remember I am calling my method here
        </script>
    </body>
</html>
```
So, there are many ways in which you can interact with your if statements through functions and use variables.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/vouFdyW4Lic" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Also, keep in mind that you can use your logical operators here too, and evaluate multiple things all at once.  For example:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature, windChill)
            {
                if(temperature < 40 && windChill < 0)
                {
                    document.write("Brrr.. put on a sweatshirt! Or More!");
                }
                else
                {
                    document.write("Yasss!! It's so warm, I can swim in the Clark Fork!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            // I created a variable here
            var temperature = 30;
            var windChill = -50;
            whatToDo(temperature, windChill); // remember I am calling my method here
        </script>
    </body>
</html>
```
What happened here?  I wanted to make sure I checked not only the temperature but also the wind chill.  To do that, I sent the temperature variable into the function as well as the wind chill variable. Then, in the if statement, I create a **&&**, which translates to **AND**.  What that means is that both things must be true for the statements in the block to run.  So, in this case, the temperature must be below 40, and the windChill must be below 0 before a message appears telling you to wear a sweatshirt.. (if that's all you wear, you are way tougher than me). 

Now, you could have also used **\|\|**, which translates to **OR**.  That means only one of the conditions must be true for the statements in the block to be run.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/uyUmWMdfzwk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>
<div id="elseif" class="tabcontent" >
<div class="tabhtml" markdown="1">

## else if statements

Like if statements, we can create else if statements.  These are cool because it's like having multiple if statements in a row, but they function a little differently.  Let's look at a couple of examples:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature)
            {
                if(temperature < 0)
                {
                    document.write("Yikes! It's cold!");
                }
                if(temperature < 10)
                {
                    document.write("It's still pretty cold");
                }
                if(temperature < 20)
                {
                    document.write("We are tough in Montana, it's not that bad.");
                }
                if(temperature < 30)
                {
                    document.write("Break out the t-shirts and shorts!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            // I created a variable here
            var temperature = 29;

            whatToDo(temperature); // remember I am calling my method here
        </script>
    </body>
</html>
```

Okay, so put this into a file and tell me what happens?  Did you see what you would expect?

What if you change the temperature to -1.   Then, what happens?  Why?

It's because you have multiple **if** statements evaluated.  As such, -1 is less that every one of them.  So, not only do we get something we don't want, but we have extra processing, which in the world of programming, is something to avoid.

So, how can we fix that?  Use the **else if** statements!

Let's look at a scenario where else if is implemented.

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature)'s
            {
                if(temperature < 0)
                {
                    document.write("Yikes! It's cold!");
                }
                else if(temperature < 10)
                {
                    document.write("It's still pretty cold");
                }
                else if(temperature < 20)
                {
                    document.write("We are tough in Montana, it's not that bad.");
                }
                else if(temperature < 30)
                {
                    document.write("Break out the t-shirts and shorts!");
                }
            }
        </script>
    </head>
    <body>
        <script>
            // I created a variable here
            var temperature = -1;

            whatToDo(temperature); // remember I am calling my method here
        </script>
    </body>
</html>
```
Now, run this new page with the following script.  What do you see?  Is it what you expected?  Yes?  Good!  Why did it work this time?  

With else if statements, once one of them is true, all the others are ignored.  That is good stuff!  That means it only evaluates what is needed and no more.  And it keeps our code clean.  So, are there other control statements like this?  Yup!  It's called the **switch** statement.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/LbvWL_z-sjQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>
<div id="switch" class="tabcontent" >
<div class="tabhtml" markdown="1">
## Switch statements
This control statement works like else ifs.  They keep out code clean, but they only work with whole numbers (i.e., 1,4,9, but not 1.232 or 3.393) or the single letters or strings. Also, we can only check for equality (===).  We cannot do relational operators like <, >, <= or >=.

For example, we can do this:

```html
<html>
    <head>
        <script>
            // I am defining my method here
            function whatToDo(temperature)
            {
                switch(temperature)
                {
                    case 0:
                        document.write("Yikes! It's cold!");
                        break;
                    case 10:
                        document.write("It's still pretty cold");
                        break;
                    case 20:
                        document.write("We are tough in Montana, it's not that bad.");
                        break;
                    case 30:
                        document.write("Break out the t-shirts and shorts!");
                        break;
                }
            
            }
        </script>
    </head>
    <body>
        <script>
            // I created a variable here
            var temperature = 0;

            whatToDo(temperature); // remember I am calling my method here
        </script>
    </body>
</html>
```
This time to test, we have to put in the actual number that matches, like 0, 10, 20, etc.  Then, you should see messages according to the number.  If they don't match, you shouldn't see anything.

What is so special about switch statements?  Well, did you notice the **break**  That is new.  Well, that is what makes these work like else if's.  If the break statement is not there, the program will continue to evaluate everything to true, which is not what we want!  So, we use the break to make sure we get out of the switch.  Try this out and change the numbers to see what happens.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/zIePAo1S394" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

Next up, looping!  
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
</div>
</div>
