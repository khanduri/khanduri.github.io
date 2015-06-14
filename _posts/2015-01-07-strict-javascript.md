---
layout: post
title: "Strict Javascript"
title_section:
    first: "Strict"
    second: "Javascript"
description: ""
image: "/assets/posts/img/js_logo.png"
category: "learn"
tags: [javascript,ECMAScript]
---
{% include JB/setup %}

![JS Logo]({{site.url}}/assets/posts/img/js_logo.png)

I saw `'use strict';` being used at a top of a few **.js** files, in some open source projects, and wanted to better understand what this meant. I found a definition that stated:

> "use strict";  Defines that JavaScript code should be executed in "strict mode".

Ok .. That didn't help much. Digging a bit more, I found out it was introduced in [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) version 5.

Let's take another step back .. What's ECMAScript? .. and how is that related to JavaScript?

###ECMA International
**JavaScript** was originally developed at Netscape (~1996) and looking at the widespread success of the language Microsoft decided to build their own version of it, calling it **JScript**. Both were client side scripting languages and had a huge overlap (with some unique functionalities as well).

![ECHMA International]({{site.url}}/assets/posts/img/echmaInc.jpg)

In an attempt to standardize the process, Netscape delivered JavaScript to [ECMA International](http://en.wikipedia.org/wiki/Ecma_International) to try and build a specification that could be used as a base. Moving forward both JavaScript and JSript tried to be compatible with these **ECMASript** specs.

You can find a summary of each version [here](http://en.wikipedia.org/wiki/ECMAScript#Versions), but for now version 5 is what's important for us. This is the [when "strict mode" was added in](http://www.w3schools.com/js/js_strict.asp).

###What is "strict mode" and why use it?
"use strict" is a literal expression that is ignored by JavaScript < 1.8.5. This is for backward compatibility. However, for compatible versions, this means we'd like to be harsh on checking the JavaScript code and would not accept previously accepted "bad syntax" code. As a quick example, in a non strict JS code, if a variable is not declared, we create a global variable for it. This is not allowed under strict mode, and we will get an error. There are [tons of examples](http://www.nczonline.net/blog/2012/03/13/its-time-to-start-using-javascript-strict-mode/) on strict code out there so I won't echo those out again.

However I would like to list out the reasons why we **should** use the strict mode. It will

 - Help you write "secure" JavaScript
 - Catch common mistakes during the early stages of development
 - You can even scope it down to a local scope so you only have partial strict code restriction

So .. What about when **NOT** to use it?

 - In your legacy code: It might start to throw exceptions and break functionality. You may want to slowly roll it out with unit tests baking up the changes
 - To any modules you do not own (Third party libraries might fail on this too)

For more detailed information, feel free to checkout the [NCZOnline blog post](http://www.nczonline.net/blog/2012/03/13/its-time-to-start-using-javascript-strict-mode/) that helped me better understand this topic.

regards
