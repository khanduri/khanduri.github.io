---
layout: post
title: "Mac: Hidden files in finder"
title_section:
    first: "Mac:"
    second: "Hidden files in finder"
description: ""
image: "/assets/posts/img/mac_hidden.jpg"
category: "trick"
tags: [mac,osx]
---
{% include JB/setup %}


By default, finder on Mac OS X hides hidden files from the view. However I like to keep them in the view.

To get this done was quick and simple. In a terminal window type the following:

> defaults write com.apple.finder AppleShowAllFiles YES

> killall Finder

The next time you open up your finder window, you'll see the hidden files in there.

![Hidden finder]({{ site.url }}/assets/posts/img/hidden_finder.png)

regards

