---
title: Workspace
permalink: /:title/
jotted: true
---

# Blank Workspace


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            content:"//test code here\n\n"
        },
        {
            type: "html",
            hide: false,
            content:'<!DOCTYPE html>\n<html>\n\t<head>\n\t\t<meta charset="utf-8">\n\t\t<title>Test</title>\n\t\t<meta name="viewport" content="width=device-width, initial-scale=1.0">\n\n\t</head>\n\t<body>\n\n\t</body>\n</html>'
        },
        {
            type: "css",
            hide: false,
            content:'body {\n\t\n}'
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 100 } },
        { name: 'console', options: { autoClear: true } },
        { name: 'play', options: { /* firstRun: false */ } },
    ]
});
</script>
