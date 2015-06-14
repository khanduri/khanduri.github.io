---
layout: post
title: "JSONp support on flask apps"
title_section:
    first: "JSONp"
    second: "support on flask apps"
description: ""
image: "/assets/posts/img/flask.png"
category: "learn"
tags: [flask,jsonp,javascript]
---
{% include JB/setup %}


###The problem
I was working on my sample project ([Yeoman PetStore](https://github.com/khanduri/yeoman-petstore)) and decided to call [another service](http://ezapps.herokuapp.com/facts/) I had build a while back. This is when I started getting the following error:

    No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin 'http://localhost:9000' is therefore not allowed access.

A quick search brought up the following:

<i>When Site A tries to fetch content from Site B, Site B can send an Access-Control-Allow-Origin response header to tell the browser that the content of this page is accessible to certain origins. (An origin is a domain, plus a scheme and port number.) By default, Site B's pages are not accessible to any other origin; using the [Access-Control-Allow-Origin header](http://www.html5rocks.com/en/tutorials/cors/) opens a door for cross-origin access by specific requesting origins.</i>

###My Solution
The correct fix is to change the server code to return the correct `Access-Control-Allow-Origin` property in the header. However I wanted to take a quick route out and another way of fetching data from the server was to use [JSONP](http://en.wikipedia.org/wiki/JSONP).

![Flask Logo]({{ site.url }}/assets/posts/img/flask.png)

I implemented my original service in [python](http://en.wikipedia.org/wiki/Python_%28programming_language%29) using [flask](http://en.wikipedia.org/wiki/Flask_(web_framework)). So I was hoping to easily extend the api to have jsonp support. Here an easy way of doing it:

NOTE: The following is not my code, but i can't find a reference to the original author's post
<script src="https://gist.github.com/khanduri/297319e52daafd8a56b9.js"></script>

And now we can just decorate all our API calls with `@support_jsonp` for jsonp support.

regards


