---
layout: post
title: "AngularJS routeProvider"
title_section:
    first: "AngularJS"
    second: "routeProvider"
description: ""
image: "/assets/posts/img/angular.png"
category: "learn"
tags: [angularjs,javascript,MVC,yeoman]
---
{% include JB/setup %}

Let's continue building out our PetStore from the earlier [Angular intro]({% post_url 2015-01-05-angularjs-quick-intro %}) post.

Let's recall we had the following line in our `app/index.html`

    <div ng-include="'views/main.html'" ng-controller="MainCtrl"></div>

We didn't really go over **[ng-include](https://docs.angularjs.org/api/ng/directive/ngInclude)** when going over [Angular intro]({% post_url 2015-01-05-angularjs-quick-intro %}). It's a new directive that fetches and includes an external html fragment.

####What's wrong here?
Nothing .. It's OK to use the **[ng-include](https://docs.angularjs.org/api/ng/directive/ngInclude)** directive to load the internal view on the main page, however if we want better control over what to display on that view based on some routes the user is interested in, we may have more flexibility. For example: on the PetStore we'd like to show a list of pets when the user wants to visit the home page (clicks on the "home" tab), or we'd like to display the "about us" information when the users wants to visit the about page (clicks on the "about" tab). We can do so by using Angular Routes.

####Angular Routes

![Angular Logo]({{ site.url }}/assets/posts/img/angular.png)

Angular provides **[ngRoute](https://docs.angularjs.org/api/ngRoute)** module for routing ([$routeProvider](https://docs.angularjs.org/api/ngRoute/provider/$routeProvider)) / deeplinking services ([$route](https://docs.angularjs.org/api/ngRoute/service/$route)) and directives ([ng-view](https://docs.angularjs.org/api/ngRoute/directive/ngView)). Instead of me describing these in detail and echoing the docs that are already out there, let's get straight to using these in our PetStore.

The first step is installing the module. The following does the trick:

    bower install --save angular-route#1.2.16

<i>NOTE</i>: the `--save` tells yeoman to save the dependency in the `bower.json` file and running `grunt serve` again after the change is saved, will allow grunt to push those changes in the `app/index.html` (meaning we'll have all the js files inserted for us). For the version number locking, checkout the issue section at the end of this post

So first things first ... lets replace the **ng-include** with the **ng-view** directive.

That means, we need to replace

    <div ng-include="'views/main.html'" ng-controller="MainCtrl"></div>

with

    <div ng-view=""></div>

All we need now is some way to control this view based on when a route is picked. [$routeProvider](https://docs.angularjs.org/api/ngRoute/provider/$routeProvider) to the rescue.

In our `app/script/app.js` we need to add the `$routeProvider` and the locations we'd like to support:

<script src="https://gist.github.com/khanduri/9332b949e1af3552dec8.js"></script>

We need to add the about view `views/about.html` and a controller for it in the mix. Also note the `otherwise` condition that points back to home page. The complete change commit is available [here](https://github.com/khanduri/yeoman-petstore/commit/204cc6b83dc6de59e8c9e62f28d1f2e02f108eda#diff-2). Hope this helps!

####Issues I ran into

There were some issues I ran into and thought may as well share them here:

- I kept getting `Unknown provider: $templateRequestProvider <- $templateRequest ...`
Remember `bower install --save angular-route#1.2.16` .. locking it down to the version number was the solution.

- `grunt serve` wasn't working so I had to use `grunt serve --force`
Following the advise [here](https://github.com/yeoman/generator-angular/pull/842/files) the change we'll have to make is [here](https://github.com/khanduri/yeoman-petstore/commit/204cc6b83dc6de59e8c9e62f28d1f2e02f108eda#diff-0)


regards
