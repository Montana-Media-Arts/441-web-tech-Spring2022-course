---
title: Query Strings
module: 5
jotted: false
---


# Query Strings
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'page1')">Page 1</button>
  <button class="tablinks" onclick="openTab(event, 'page2')">Page 2</button>
  <button class="tablinks" onclick="openTab(event, 'explain')">Explain</button>
  <button class="tablinks" onclick="openTab(event, 'form1')">Form 1</button>
  <button class="tablinks" onclick="openTab(event, 'form2')">Form 2</button>
  <button class="tablinks" onclick="openTab(event, 'explain2')">Explain </button>
  <button class="tablinks" onclick="openTab(event, 'video')">Video</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">
Query strings are a simple way to send information from page to page.  However, items in the query string appear as clear text in the address bar of the browser.  What does that mean?  That means anyone can see the information in the address bar, and it is NOT secure.  However, it's nice when we need to send data to another page that doesn't require high security.  It's easy to do.  How do we do it?

We need two pages.  

</div>
</div>

<div id="page1" class="tabcontent">
<div class="tabhtml" markdown="1">

Page 1

```html
<html>
    <head>
        <title>
            Query String
        </title>
        <script>
            function sendToNextPage()
            {
                var information = document.getElementById("information").value;
                window.location="querystring2.html?info=" + information;
            }
        </script>
    </head>
    <body>
        <input type="text" id="information">
        <button id="btnSubmit" onclick="sendToNextPage();">Submit</button>
    </body>
</html>
```
</div>
</div>

<div id="page2" class="tabcontent">
<div class="tabhtml" markdown="1">
Page 2

```html
<html>
    <head>
        <title>
            Query String
        </title>
        <script>
            function getInformation()
            {
                var information = new URLSearchParams(location.search);
                document.getElementById("message").innerHTML = information.get("info"); 
            }
        </script>
    </head>
    <body onload="getInformation();">
        <div id="message"></div>
    </body>
</html>
```

</div>
</div>

<div id="explain" class="tabcontent">
<div class="tabhtml" markdown="1">

The first page uses the **getElementById** to get the information and then pass it through to the next page using **window.location**.  

Then in the second page, you can get the information by using the **location.search** along with the **URLSearchParams** class (don't worry about that yet; we will talk about that at greater length later).

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/6bsF1D3i_vY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

</div>
</div>

<div id="form1" class="tabcontent">
<div class="tabhtml" markdown="1">
Another option to access the query string is through the **form** tag. Let's look at it now.

This technique also needs two pages.  The first page looks like this:

```html
<html>
    <head>
        <title>
            Form
        </title>
    </head>
    <body>
        <form method="get" action="form2.html">
                <input type="text" name="info">
                <button id="btnSubmit">Submit</button>
        </form>
    </body>
</html>
```

</div>
</div>

<div id="form2" class="tabcontent">
<div class="tabhtml" markdown="1">
The second page looks like this.

```html
<html>
    <head>
        <title>
            Form
        </title>
        <script>
            function getInformation()
            {
                var information = new URLSearchParams(location.search);
                document.getElementById("message").innerHTML = information.get("info"); 
            }
        </script>
    </head>
    <body onload="getInformation();">
        <div id="message"></div>
    </body>
</html>
```

</div>
</div>

<div id="explain2" class="tabcontent">
<div class="tabhtml" markdown="1">
This time, we have just a form with no JavaScript.  We use the **action** and **method** attribute of the form to send information to the second page.  Another thing to notice is that the text box uses the **name** attribute instead of the **id**.  Finally, the **onload** event of the body calls the **getInformation** function.

</div>
</div>

<div id="video" class="tabcontent">
<div class="tabhtml" markdown="1">

<div class="embed-responsive embed-responsive-16by9"><iframe width="560" height="315" src="https://www.youtube.com/embed/Z2O1wLnNC-0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>


</div>
</div>


