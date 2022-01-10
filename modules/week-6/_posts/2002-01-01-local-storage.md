---
title: Local Storage
module: 6
jotted: false
---

# Local Storage
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'page1')">Page 1</button>
    <button class="tablinks" onclick="openTab(event, 'page2')">Page 2</button>
  <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
  </div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
So, what is **local storage**? You have used the query string and cookies, but what other mechanisms are there for storing information?  One is local storage.  It allows us to store information on a client without having to have a domain (like a cookie does), and you don't have to worry about having data in the query string in cleartext.
</div>
</div>

<div id="page1" class="tabcontent">
<div class="tabhtml" markdown="1">
So, how does it work?  Here is the syntax of the two files required:

```html
<html>
    <head>
        <title>
            JSON FTW
        </title>
        <script>
            function getInformation()
            {
                var information = {"car": "dodge", "year":"2016", "color":"blue"};
                document.getElementById("info").innerHTML = information.car + ":" + information.year + ":" + information.color;
                localStorage.setItem("information", JSON.stringify(information));
            }
            
            function goNextPage()
            {
                window.location = "Page2.html";
            }
        </script>
    </head>
    <body onload="getInformation();">
        <div id="info"></div>
        <br>
        <button id="btnSubmit" onclick="goNextPage();">Go to Next Page</button>
    </body>
</html>
```

</div>
</div>

<div id="page2" class="tabcontent">
<div class="tabhtml" markdown="1">
Whereas Page 2 looks like this:


```html
<html>
    <head>
        <title>
            JSON FTW
        </title>
        <script>
            function getInformation()
            {
                var information = localStorage.getItem("information");
                document.getElementById("info").innerHTML = "<h1>" + JSON.parse(information).car + "</h1>";
            }
            
            function goNextPage()
            {
                window.location = "Page1.html";
            }
        </script>
    </head>
    <body onload="getInformation();">
        <div id="info"></div>
        <br>
        <button id="btnSubmit" onclick="goNextPage();">Go to Next Page</button>
    </body>
</html>
```

You may notice that I needed first to change the JSON object to a string before I stored it in local storage.  Then, when I got it out of local storage since it's formatted correctly, I parsed it back into a JSON object.

Again, the **stringify** and **parse** functions come from the JSON class.  Cool huh?

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/X-3_05yBklQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
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

