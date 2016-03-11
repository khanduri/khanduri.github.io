---
layout: post
title: "Bootstrap's collapsable navbar with icon"
title_section:
    first: "Bootstrap's"
    second: "collapsable navbar with icon"
description: ""
image: ""
category: "[learn]"
tags: [css,html,bootstrap]
---
{% include JB/setup %}


I was working on rendering a navigation bar using the basic bootstrap layout,
when I noticed the collapsable functionality (when you decrease the screen
size, I was expecting to see the button that allows me to expand the
navigation bar).

![Bootstrap Collapse Icon]({{ site.url }}/assets/posts/img/bootstrap_navbar_collapse_icon.png)

My original code looked like (note that I had the appropriate .js files
included as well):

```html
<nav role="navigation" className="navbar navbar-default navbar-static-top">
    <div className="container">
        <div className="navbar-header">
            <a href="/" className="navbar-brand">CompanyLogo</a>
        </div>
        <div className="navbar-collapse collapse navbar-main-collapse">
            <ul className="nav navbar-nav">
                <li><a href="/">Link 1</a></li>
            </ul>
            <ul className="nav navbar-nav navbar-right">
                <li><a href="/">Link 1</a></li>
            </ul>
        </div>
    </div>
</nav>
```

... and of course, you may have guessed, I was missing the actual code for the
button in the navbar-header tag:

```html
<button type="button" className="navbar-toggle" data-toggle="collapse" data-target=".navbar-main-collapse">
    <i className="fa fa-bars"></i>
</button>
```

Here's what the fixed code looks like:
<script src="https://gist.github.com/khanduri/2dabdf79240374c357d1.js"></script>

regards

