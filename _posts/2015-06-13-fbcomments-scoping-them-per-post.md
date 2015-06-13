---
layout: post
title: "FBComments Scoped per post"
title_section:
    first: "FBComments"
    second: "Scoped per post"
description: ""
category: "setup"
tags: fb-comments blog jekyll-bootstrap
---
{% include JB/setup %}

A good friend of mine, [Scott Lobdell](http://scottlobdell.me/), recently
discovered that I was "trying" to maintain a blog!

![Scott Lobdell comment bug]({{ site.url }}/assets/posts/img/scott_lobdell_comments_bug.png)

Although his surprise didn't come as a shock to me, but it did surface a fun bug. His comment was showing up on all my blog post pages. My original intention was to scope the comment conversation down per post.

It turns out the fix was simple.

A quick search online landed me on the [FB coments documenation](https://developers.facebook.com/docs/plugins/comments), and in the *settings* section it is mentioned that we need to make sure the *data-href* attributes points to the current URL.

Moral of the story: *When in doubt, read the documentation!*

That change lives under the [facebook comment plugin](https://github.com/khanduri/khanduri.github.io/blob/master/_includes/JB/comments-providers/facebook) for Jekyll Bootstrap. So I just had to make the [appropriate change](https://github.com/khanduri/khanduri.github.io/commit/0190936e75ea13ab08bd7edda97ceb6e96fe6e84), and the comments section were now scoped per post.

Unfortunately fixing this bug also meant that Scott's original comment, linked to the root page, is not be visible anymore .. sorry Scott! You do get your comment snapshot saved on this post, but you can't like your comment anymore (A very rare occurrence, for whoever knows Scott).

regards

