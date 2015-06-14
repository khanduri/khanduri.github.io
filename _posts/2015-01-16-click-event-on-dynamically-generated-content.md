---
layout: post
title: "Click event on dynamically generated content"
title_section:
    first: "Click event"
    second: "on dynamically generated content"
description: ""
image: "/assets/posts/img/jquery.jpg"
category: "learn"
tags: [javascript,JQuery]
---
{% include JB/setup %}

While continuing my work on [playing with colours](/projects/play_with_colours/main.html) I ran into an interesting problem.

After printing the color grid on the main canvas, I wanted to add the ability for the user to remove particular colors from this grid. I was hoping to place an "X" button near the top left of every color and define a click handler to the class of these button, and just remove their parents.

It felt [simple](https://github.com/khanduri/khanduri.github.io/commit/8b4068a661e3b6d3fc5329e8e4f68961538c1d77#diff-472e4a11e6f84501cefc0ddc707ecbccR232), but the initial approach I took wasn't really working.

    $(".color-remove").click(function(e){
        console.log('here');
        this.parent().remove();
    });

This didn't work. The log just won't show up! I was stuck on this for a while , and then it hit me. The parent of `'.colour-remove'` is dynamically being inserted in the page's `'#canvas'` and I'm attaching an event at page load. So no wonder the click handler is not getting attached!

<i>NOTE: If you know of a way I can catch these errors faster, please do leave a comment! I'd love to learn better debugging tricks</i>

Once I realized this could be the issue, a quick search returned back the [correct answer](http://stackoverflow.com/a/1207393/2069749).

![JQuery Logo]({{site.url}}/assets/posts/img/jquery.jpg)

We needed to use **[.on()](https://api.jquery.com/on/#on-events-selector-data-handler)** methond to bind the event handler our class. (Since I'm using jQuery 1.11+, I didn't really read through the <i>.live()</i> docs)

And the issue was [fixed](https://github.com/khanduri/khanduri.github.io/commit/f4aed17ade1184c8363746e63d782a1c90fb7eae#diff-472e4a11e6f84501cefc0ddc707ecbccR232). Thanks StackOverflow!
