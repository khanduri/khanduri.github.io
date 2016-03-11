---
layout: post
title: "CSSTricks Print out the screen size while debugging"
title_section:
    first: "CSSTricks"
    second: "Print out the screen size while debugging"
description: ""
image: "/assets/posts/img/jekyll.png"
category: "trick"
tags: [css,html]
---
{% include JB/setup %}

I was having issues with bootstrap navbar and ran into this cool trick while
testing your style setup on different screens.

You can add the following on your base html page and get the bootstrap screen
categorization rendered back on the screen:

```
<div id="debug">
    <span class="visible-xs">SIZE XS</span>
    <span class="visible-sm">SIZE SM</span>
    <span class="visible-md">SIZE MD</span>
    <span class="visible-lg">SIZE LG</span>
</div>
```

Unfortunately I don't remember which post I saw this on, otherwise I'd love to
have left a reference link in here.

regards
