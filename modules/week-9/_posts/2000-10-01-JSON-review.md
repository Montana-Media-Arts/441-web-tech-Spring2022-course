---
title: JSON Review
module: 9
jotted: true
---

# JSON Review

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>

  <button class="tablinks" onclick="openTab(event, 'jsexample')">JS Example</button>
  <button class="tablinks" onclick="openTab(event, 'jqueryexample')">jQuery Example</button>
  <button class="tablinks" onclick="openTab(event, 'todo')">To Do</button>
</div>
<div id="Overview" class="tabcontent" style="display:block">
<div class="tabhtml" markdown="1">

Before we look at how to access data using AJAX, we will review JSON. Recall JSON stands for JavaScript Object Notation.  This way, we can store data as an object.

Remember, JSON is a standardized method for storing and transporting unordered collections of data. Data storage is through a _name:value_ pairs or key:value pairs. Furthermore, the _values_ in JSON data can be;

* strings
* numbers
* booleans
* arrays
* or other nested JSON objects

<br />


JSON Objects, once in JavaScript (i.e., after being sent over from an API on a remote server), appear as JS objects. As such, they can be traversed and manipulated using standard JS object notation and techniques.

As an example, the following code creates a JS Object, which is also valid as JSON.

```js
let bike = {
    "manufacturer" : "Santa Cruz",
    "model" : "5010",
    "owner" : {
        "firstName" : "Bob",
        "lastName" : "Jones"
    },
    "sizes" : [
        "small",
        "medium",
        "large",
        "x-large"
    ]
}
```

Once this object is bound to the variable `bike`, we can navigate through it and access its unique values.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/KQMSfQr8GT4" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="jsexample" class="tabcontent">
<div class="tabhtml" markdown="1">

The following example creates the same object as above but also demonstrates how to access values within the object.

```html
<html>
    <head>
        <script>
            let bike = {
                "manufacturer" : "Santa Cruz",
                "model" : "5010",
                "owner" : {
                    "firstName" : "Bob",
                    "lastName" : "Jones"
                },
                "sizes" : [
                    "small",
                    "medium",
                    "large",
                    "x-large"
                ]
            }

            function showBikeInfo()
            {
                document.getElementById("bikeInformation").innerHTML = "Manufacturer: " + bike.manufacturer 
                + "<br>Model:" + bike.model + "<br>First Name:" + bike.owner.firstName + "<br>Last Name:" 
                + bike.owner.lastName + "<br>Sizes Available:<br>" +
                bike.sizes[0] + "<br>" + bike.sizes[1] + "<br>" + bike.sizes[2] + "<br>" + bike.sizes[3];
            }
        </script>
    </head>

    <body>
        <div id="bikeInformation"></div>
        <button id="btnSubmit" onclick="showBikeInfo();">Show Information</button>
    </body>
</html>
```
This shows us traditional JSON key/value pairs, as well as JSON inside of JSON and an array inside of JSON.  That is good stuff!

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/ND9uNZIv9g8" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="jqueryexample" class="tabcontent">
<div class="tabhtml" markdown="1">

But that's not all!  What about if we were doing this in jQuery?  Could you do it?

Let's look at an example:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
         let bike = {
                "manufacturer" : "Santa Cruz",
                "model" : "5010",
                "owner" : {
                    "firstName" : "Bob",
                    "lastName" : "Jones"
                },
                "sizes" : [
                    "small",
                    "medium",
                    "large",
                    "x-large"
                ]
            }
        
        $(function () {
            $("button").click(function () {
                showBikeInfo();
            });

        });
       
        function showBikeInfo()
            {
                $("#bikeInformation").html("Manufacturer: " + bike.manufacturer 
                + "<br>Model:" + bike.model + "<br>First Name:" + bike.owner.firstName + "<br>Last Name:" 
                + bike.owner.lastName + "<br>Sizes Available:<br>" +
                bike.sizes[0] + "<br>" + bike.sizes[1] + "<br>" + bike.sizes[2] + "<br>" + bike.sizes[3]);
            }
        </script>
    </head>

    <body>
        <div id="bikeInformation"></div>
        <button id="btnSubmit" onclick="showBikeInfo();">Show Information</button>
    </body>
</html>

```

Keep in mind that I used the `.html` function so that I could display the break tags correctly.  Otherwise, everything else was pretty much the same.  All this information is exciting! It's all coming together.  So, why do we review JSON?  Well, as we talked about before, it's a ubiquitous delivery method from many different sources so we can read information from databases and server-side pages because they will give information back to the client via JSON.  So, let's look at AJAX.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/485pJBoSrpg" frameborder="0" allowfullscreen></iframe></div>

</div>
</div>

<div id="todo" class="tabcontent">
<div class="tabhtml" markdown="1">
#### JavaScript Example

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="RwoBVrJ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="JavaScript Example - read JSON">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/RwoBVrJ">
  JavaScript Example - read JSON</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### jQuery Example

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="retrog4m3r" data-slug-hash="GRNBmpX" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="jQuery Example - read JSON">
  <span>See the Pen <a href="https://codepen.io/retrog4m3r/pen/GRNBmpX">
  jQuery Example - read JSON</a> by Michael Cassens (<a href="https://codepen.io/retrog4m3r">@retrog4m3r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>
</div>
