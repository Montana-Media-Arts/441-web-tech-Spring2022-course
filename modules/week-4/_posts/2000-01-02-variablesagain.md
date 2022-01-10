---
title: Variables again
module: 4
---

# Variables again <br />


<br />
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'Example1')">Example 1</button>
  <button class="tablinks" onclick="openTab(event, 'Example2')">Example 2</button>
  <button class="tablinks" onclick="openTab(event, 'Video')">Video</button>
  <button class="tablinks" onclick="openTab(event, 'ToDo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block"  markdown="1">
You might be asking yourself, why are we covering variables again?  Well, they are the cornerstone of programming, so it's good to have a solid grasp on them.

What does that mean to us?

Remember from last week, that we can declare a variable like this:

- var
- let
- const

Now, do you remember what those all mean?

</div>
<div id="Example1" class="tabcontent" >
<div class="tabhtml" markdown="1">

If I were to ask you to create a program that gets a user's name and then put it into a variable, do you think you could that? 

If not, that's okay!  I will show you how.

First, create a file called GetName.html.

Then, add a textbox into that file.

```html
<html>
    <body>
        <label id="lblName">Your Name Goes Here</label><br>
        <input id="txtName" type="text"><br>
        <button id="btnSubmit">Submit</button><br>
    </body>
</html>
```

Now, open the file in your favorite browser (still hopefully Chrome).  Does it show a textbox and a button? Great!
</div>
</div>
<div id="Example2" class="tabcontent" >
<div class="tabhtml" markdown="1">

Now, we need to get the information out of the text box.  How are we going to do that?  Well, first, then we need to do is get the text from the label.

We need to add some JavaScript to access the DOM (quick check, you remember the DOM right?  If not, it stands for Document Object Model)

```html
<html>
    <body>
        <label id="lblName">Your Name Goes Here</label><br>
        <input id="txtName" type="text"><br>
        <button id="btnSubmit">Submit</button><br>

         <script>
           var currentText = document.getElementById("lblName").innerHTML;
           
           // to see what is stored in the tag, we have two options
           
           // we can either use the console.log
           //console.log(currentText); 
            
           // we can also use the window.alert function 
           //window.alert(currentText); 
        </script>
    </body>
</html>
```
</div>
</div>
<div id="Video" class="tabcontent" >
<div class="tabhtml" markdown="1">

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/g2SFQfttRYg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="ToDo" class="tabcontent" >
<div class="tabhtml" markdown="1">
Feel free to explore the code and make changes on CodePen.  

Click on **Edit on CodePen** to experiment.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="retrog4m3r" data-slug-hash="qBqWeQK" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MART 441 Variable Example">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/qBqWeQK">
  MART 441 Variable Example</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>
</div>