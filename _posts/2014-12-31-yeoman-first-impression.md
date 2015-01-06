---
layout: post
title: "Yeoman: First impression"
title_section:
    first: "Yeoman:"
    second: "First impression"
description: ""
category: "experiment"
tags: [javascript,angularjs,yeoman,frontend,grunt,bower]
---
{% include JB/setup %}

![Yeoman project]({{ site.url }}/assets/posts/img/yeoman.png)

I have a LONG way to go when it comes to
[front end development](http://en.wikipedia.org/wiki/Front_end_development),
but its a path I'm really exited to walk on. I have a rough idea of the
tools I'd like to try. However with all the
really nice open source tools available, I (like many individuals) get nervous
when trying to pick one.

A tool that got my attention, while I was trying to explore <i>what
[MVC framework](https://github.com/showcases/front-end-javascript-frameworks)
to pick for my FE projects?</i>, was [Yeoman](http://yeoman.io/). Yeoman is not an
MVC framework, but it provides the setup around the FE development process to
rapidly create / test webapp ideas.

###What's Yeoman?
As it states on their website: *THE WEB'S SCAFFOLDING TOOL FOR MODERN WEBAPPS*.
It boils down to 3 tools:

 - [yo](https://github.com/yeoman/yo) - the site scaffolding
 - [bower](http://bower.io/) - package manager
 - [grunt](http://gruntjs.com/) - build tool

I highly recommend going through their [codelab](http://yeoman.io/codelab.html)
tutorial. The site claim it takes about 1 hour, but it
[took me a bit longer](https://github.com/khanduri/YeomanTodo). Here's a quick
tutorial overview:

- `npm install yo bower grunt-cli` (node is required)
- Install your generator (the tutorial picked AngularJS)
- `yo angular` sets up the project
- `grunt serve` starts up the included server and watches over file changes to reload as they change
- `bower install --save` packages that you wish to include. They get added to the html automatically
- `grunt test` to run tests
- To get everything ready for production .. just `grunt` .. and the files should be ready to be deployed

###Some really nice features

 - Live reload: See your changes on the page as soon as you make them. No need
 to manually reload the page

![Yeoman LiveRelaod Demo]({{ site.url }}/assets/posts/gif/yeoman_livereload_demo.gif)

 - Code linting: runs as part of the build process
 - Minification of css/js files
 - The build process completely automated
 - All those generators (but I'll probably be focusing on Angular for now)
 - Backed up by some awesome folks - known for their open source contributions

###Next Steps

I can see myself loving Yeoman, but its too early as I haven't really built
something real with it yet. For now, I've picked
[AngularJS](https://angularjs.org/) as my choice of front end MVC framework (the
primary Yeoman generator) that I'd like to learn more of.

A good way to wrap up 2014 .. and a good todo list for 2015 :)

![Yeoman rocket]({{ site.url }}/assets/posts/img/yeoman_rocket.png)
