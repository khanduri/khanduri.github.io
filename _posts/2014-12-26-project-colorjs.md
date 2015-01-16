---
layout: post
title: "Project: color.js"
title_section:
    first: "Project:"
    second: "color.js"
description: ""
category: "project"
tags: [project,javascript,open-source,github]
---
{% include JB/setup %}

<div class="font-mono">
------------------__------------------------------------------------<br>
------_____-___--/ /___---____----------(_)____---------------------<br>
-----/ ___/ __ \/ / __ \/ ___/---------/ / ___/---------------------<br>
----/ /__/ /_/ / / /_/ / /------------/ (___ )----------------------<br>
----\___/\____/_/\____/_/-----(_)--__/ /____/-----------------------<br>
----------------------------------/___/-----------------------------<br>
</div>
<br>

The [theme](https://github.com/jekyllbootstrap/theme-the-minimum) I've been using for my blog uses
[LESS](http://lesscss.org/) as its
[CSS preprocessor](https://www.urbaninsight.com/2012/04/12/ten-reasons-you-should-be-using-css-preprocessor).
I recently made my fork switch to [Sass](http://sass-lang.com/). There are plenty of blogs that compare the two
technologies, so I won't go into the comparison in this post. I might write soon on why I decided to choose Sass,
but that'll have to wait.

For making the transition, I used an online [css2scss](http://sebastianpontow.de/css2compass/) converter and noticed
something interesting. The tool was coming up with names for the colors being used in the css. For some reason
I wanted to see if I could figure it a way myself as well (I could generate easy to remember (potentially
programmatically generated) names for my constants, this way.

So I started [playing with colours](/projects/play_with_colours/main.html) with the hope to get somewhere with
just the names. I very quickly realized that I can pack a few more operations into a library and use it for any
other project I work on. This is where *[color.js](https://github.com/khanduri/color.js)* came into existence.

*[color.js](https://github.com/khanduri/color.js)* is a library for JavaScript that hopes to provides easy operations
over hex colors. The project is [open source](https://github.com/khanduri/color.js/blob/master/color.js) so please
feel free to take a look for yourself and please suggest improvements (Pull Requests are welcome!).

However to give you a taste, here's a sample on how we can currently use it (More samples are available
[here](https://rawgit.com/khanduri/color.js/master/sample.html)):

* Initialization and assignment:
    <pre>var color = Color('#123456');</pre>
* Check If the colour is valid:
    <pre>color.isValid(); // true</pre>
* Color name (find approximate, if exact is missing):
    <pre>color.getName(); // taupe_approx</pre>
* Get Colour models:
    <pre>
    color.getRGB(); // 18, 52, 86<br>
    color.getHSL(); // 148, 166, 52<br>
    color.getYUV(); // 0.179, 0.0868, -0.095
    </pre>
* Gradient helpers:
    <pre>
    color.getShades(5); <br>
    // #123456,#0e2a44,#0a2032,#061620,#020c0e,#000000<br>
    color.getTints(5); <br>
    // #123456,#163e68,#1a487a,#1e528c,#225c9e,#FFFFFF
    </pre>

I know I have a long way to go with this library, but it’s a nice start :)

regards
