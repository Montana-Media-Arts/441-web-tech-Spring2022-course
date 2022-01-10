---
title: Debugging
module: 5
jotted: false
---

# Debugging
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'syntax')">Syntax</button>
  <button class="tablinks" onclick="openTab(event, 'runtime')">Run Time</button>
  <button class="tablinks" onclick="openTab(event, 'logical')">Logical</button>
  
  <button class="tablinks" onclick="openTab(event, 'ToDo')">ToDo</button>
  
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
The following two readings provide a wealth of information on _Bugs and Errors_, as well as how to find them, utilize them, and fix them.

- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 8; Bugs and Errors_](https://eloquentjavascript.net/3rd_edition/08_error.html)
- **Web Technology for Developers.** MDN web docs. 2018. Web.
    - [_Control Flow and Error Handling_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)

Okay, so let's talk about debugging.  I hope these two readings were helpful. I want to share with you some of the techniques I have used over the years too.

There's a couple of things we should define, though. What are the different types of errors, and how hard are they to find?
</div>
</div>
<div id="types" class="tabcontent">
<div class="tabhtml" markdown="1">
There are three types of errors.

1. Syntax Errors
2. Run-Time Errors
3. Logical Errors

I put them in this order on purpose.  Syntax errors are the easiest to find.  That means there is something wrong with the language or the syntax of the code you have written. Syntax errors are things like a missing semicolon, too many or too few curly braces, missing or too many parentheses, etc. 

</div>
</div>
<div id="syntax" class="tabcontent">
<div class="tabhtml" markdown="1">

Let's look at an example.

```html
<html>

    <head>
        <title>Arrays</title>

        <script>
            function printArray()
            {
                var food = new Array"apple", "orange", "grape");
                food.push("pear");
                var allFoods = "";
                for(var i = 0; i < food.length i++)
                {
                    allFoods += food[i] + "<br>
                }
                document.getElementById("myFoods").innerHTML = allFoods;
                   
        </script>
    </head>
    <body onload="printArray();">
        <div id="myFoods"></div>
    </body>
</html>
```

The previous section of code is a cornucopia of syntax errors.  It will help if you run this. How many errors appear?  I only see two. Why is that?  It tries to run as best as it can, and it shows you the first two (the function is not defined and the string error).  Once you fix those, you should see more.  Now, things get trickier because they aren't quite as clear.  So, we have to go line by line and look for the basics.  Are we missing any semicolons, parentheses, curly braces?  We will look at specific techniques in a second, but let's examine the second kind of error, the Run-Time Error

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/GeUV_JkrHWo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>
<div id="runtime" class="tabcontent">
<div class="tabhtml" markdown="1">

This type of error is something is syntactically correct, but when the program runs, it gives an error.  These are run-time errors, which include calling a function and sending it something that it doesn't expect, and it giving error.  Here is an example.

```html
<html>
    <head>
        <title>Arrays</title>
        <script>
            function printArray(number)
            {
                var food = new Array("apple", "orange", "grape");
                var allFoods = "";
                for(var i = 0; i < number; i++)
                {
                    allFoods += food[i] + "<br>";
                }
                document.getElementById("myFoods").innerHTML = allFoods;
            }        
        </script>
    </head>
    <body onload="printArray('three');">
        <div id="myFoods"></div>
    </body>
</html>
```

What did you see when you ran it?  Was the web page blank?  Was the console blank?  Gads!  That's not easy to figure out.  So, we have to debug.  We will need debugging tools!

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/B95O8zQj9UA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>
<div id="logical" class="tabcontent">
<div class="tabhtml" markdown="1">

The last type of error is logical errors. If you thought the run time errors were nasty, logical errors are even worse and much harder to find because everything looks like it's working correctly, but it's just giving the wrong answer.  What?  It's like having a function saying add two numbers together; it returns the product.  A simple example, but that's a problem if your test is with 2 and 2.  It gives the right answer in that scenario, so if you don't test further, you may never see the problem.  Here's another example.

```html
<html>

    <head>
        <title>Arrays</title>

        <script>
            function printArray()
            {
                var ages = new Array(3, 5, "0", 9);
                var sumOfAges = 0;
                for(var i = 0; i < ages.length; i++)
                {
                    sumOfAges += ages[i];
                }
                document.getElementById("myAges").innerHTML = sumOfAges;
            }        
        </script>
    </head>
    <body onload="printArray();">
        <div id="myAges"></div>
    </body>
</html>
```
Before you run the code, what do you think the answer is going to be?  It should be 17 if you take 3 + 5 + 0 + 9.  However, when I ran it, I got 809.  It's still a number, so to the casual observer, this could be correct.  However, we know that because the + sign can either add or concatenate, it was doing both here. It added the first two numbers together and then concatenated the last two the sum of the first two numbers.  Tricky!  

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/SfvOAlMhnB8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

So, how do we find these evil creatures?  Well, that's where we employ some tools.

1. Look at debugging tools.  This a tricky one because with JavaScript, we don't have a debugger.   In a lot of other programming languages, we can use what's called a debugger to help us find out where things have gone wrong.  However, in JavaScript, as you have probably noticed, it "silently" fails for you.  So, that's where the console comes in.  It will give you an error message and usually a line where something has gone wrong.  If you click on the link next to the line, it should show you which line is causing the error. 

2. If that doesn't help, then use the console.log to print out messages to yourself.  Print out words to see if it is getting to a particular line or past a specific line.  Print out values to know if you are getting what you expect to be getting.  You can also use the alert here too, but I find the console.log more pleasant.

3. Start commenting out code to minimize what you have to debug.  Notice I say to comment out code and not delete code.  If you delete code, it's hard to remember what you did before.  So, comment out code and get something working and then add lines back little by little to see what could be going wrong.

4. Search online.  Notice how search online is the four things on the list.  It's not first.  Everyone wants to rush to Google and look for a quick answer.  Online solutions might not exist or specific to your problem.  So, if you need Google knowledge, try to find a particular problem you are having and get that to work instead of trying to find a holistic problem (i.e., the whole program you are trying to create).  Instead, search for things like, "How do I iterate through an array in JavaScript."  You will find a lot of examples, but at least it will be more specific than, "How do I create a choose your adventure story in JavaScript."  That can have many different answers.  (I say that because you all had different solutions to the same problem).

5. Ask for help.  Don't be afraid to ask for help in forums, groups, classmates, colleagues, me (at the moment, but even after the class! --- I hope that's a value add).  You don't have to know everything about everything off the top of your head.  I don't, and I certainly have asked for help before.  It's good to ask for help. 

So, that's my story about debugging. I hope this has been helpful, and I hope you can employ some of these techniques to make your programming life easier and more enjoyable.

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/kFRJeELnsPI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

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