---
title: Callbacks
module: 7
jotted: true
---

# Callbacks

You have already been exposed to and used [Higher-order Functions]({{site.baseurl}}/modules/week-4/higher-functions/) sometimes also known as _Callback Functions_.

For our purposes, we will currently define a _Callback Function_ as being a function you pass to another function, with the goal that the other function will eventually _call it_.

```js
// passed in as a function declaration
otherFunc1("some value", function(){alert("haha")} );

// passed in as a function reference
otherFunc2("some value" callBackFunction );
```

# Timers

One common use of callback functions in web-based javascript is in timers.

A _timer_ is a function that waits some specified amount of time then _does something_.

Timers may be used to refresh elements of a page at set intervals, change the picture in a gallery, add a "pop-up", etc.

## setTimeout()

One built in timer function `setTimeout()`, which takes as a minimum two input parameters;

- a callback function to execute.
- the amount of time in _milliseconds_ to delay execution.

```js
setTimeout( functionToCall, timeToWait );
```

In the following example of the `setTimeout()` function, it is used to call another function after 3 seconds, which changes the background color of the example page and creates a popup alert.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_01/script.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_01/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    runScripts: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_01/01_timer_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/441-WebTech/lecture_code/07/01_timer_01/) |


## setInterval()

Like `setTimeout()` the `setInterval()` function can be used to execute a supplied callback function after a specified amount of time. The major difference is that `setInterval()` creates a reoccurring callback that is executed constantly, at the interval specified.

<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_02/script.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_02/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    runScripts: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_02/01_timer_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/441-WebTech/lecture_code/07/01_timer_02/) |


## Cancelling Timers

You can cancel a timer function, by passing a reference to the timer function to the appropriate clear function (i.e. `clearTimeout()` and `clearInterval()`).

To pass a a reference to a timer function, simply create a binding that references the function and pass that to the appropriate clearing function. In the following example, a single timer (i.e. `setTimeout()` ) is used to _stop_ the reoccurring, `setInterval()` timer after 5 seconds.

<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_03/script.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/07/01_timer_03/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    runScripts: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_03/01_timer_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/441-WebTech/raw/master/lecture_code/07/01_timer_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/441-WebTech/lecture_code/07/01_timer_03/) |


## Further Reading on Timers

Please read the following from w3schools;

- ["JavaScript Timing Events", https://www.w3schools.com/js/js_timing.asp](https://www.w3schools.com/js/js_timing.asp)
- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 11; Asynchronous Programming_](http://eloquentjavascript.net/11_async.html)
    - Please only read up to (and not including "Promises")

# Callbacks Revisited

Again, a callback is just a function that is passed to another function, so that it can later be called back and executed. As we move forward this week, you will be working a lot with callback functions.
