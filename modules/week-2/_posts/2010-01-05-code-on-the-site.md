---
title: Code on This Site
module: 2
jotted: true
---

# Code on This Site
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
  <button class="tablinks" onclick="openTab(event, 'links')">Code Links</button>
   
</div>
<div id="Overview" class="tabcontent" style="display:block" >
<div class="tabhtml" markdown="1">
Whenever possible, I will try to provide code output in a way that is editable, changeable, and playable by you.

- "Result"
- "HTML"
- "JavaScript"

If you see one of these sections, you can;

1. change the code,
2. go back to "Results."
3. and see the changes live!

Try it below with the "Hello World!" example.

To do this;

- Click the "JavaScript" tab,
- change the `"Hello World!"` text in line 4,
    - perhaps add some more text or change the tag types...?
- and go back to Results. You should now see your changes!


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/02/02/script.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech/master/lecture_code/02/02/02_js_outside_html.html"

    }],
    showBlank: false,
    showResult: true,
    runScripts: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 100 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

</div>
</div>
<div id="links" class="tabcontent" >
<div class="tabhtml" markdown="1">
# Code Links

Below are some code examples

- [**[ Code Download ]**](https://github.com/Montana-Media-Arts/441-WebTech/blob/master/lecture_code/02/02/02_js_outside_html.zip)
    - This will be a zip folder containing all of the code for the example.
    - This is a way for you to download code examples to play with on your computers easily.
- [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/441-WebTech/tree/master/lecture_code/02/02)
    - This link will take you directly to the GitHub entry for this code so that you can look at it there.
- [**[ Live Example ]**](https://montana-media-arts.github.io/441-WebTech/lecture_code/02/02/02_js_outside_html.html)
    - This will take you to a webpage that only has the code in question presented.

</div>
</div>