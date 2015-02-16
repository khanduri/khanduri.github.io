---
layout: post
title: "Angular: Remove the hashtag"
title_section:
    first: "Angular:"
    second: "Remove the hashtag"
description: ""
category: "learn"
tags: [angularjs,yeoman]
---
{% include JB/setup %}

![Angular Logo]({{ site.url }}/assets/posts/img/angular.png)

After setting up a [Yeoman](http://yeoman.io/) base for an [AngularJS](https://angularjs.org/) project, I noticed the hashtag (# symbol) appended to the urls.

![Hashtag]({{ site.url }}/assets/posts/img/yeoman_angular_hashtag.png)

It seems it easy to get rid of them. All we need to do is configure [$locationProvider](https://docs.angularjs.org/api/ng/provider/$locationProvider) and set [html5Mode](ihttps://docs.angularjs.org/api/ng/provider/$locationProvider#html5Mode) to true:

<script src="https://gist.github.com/khanduri/b9d69574540e976c04fd.js"></script>

regards

