---
layout: post
title: "AngularJS: Quick intro"
title_section:
    first: "AngularJS:"
    second: "Quick intro"
description: ""
category: "setup"
tags: [angularjs,javascript,MVC,tutorial,yeoman]
---
{% include JB/setup %}


I'm hoping to write a few blogs that introduce basic [Angular](https://angularjs.org/) concepts. I'm not really sure how many topics I'd like to cover, however for this one I'm hoping to introduce Angular with a simple Pet Store app.

Given that I recently was [playing with Yeoman]({% post_url 2014-12-31-yeoman-first-impression %}), That's what We'll be using to setup the project.

![Yeoman project]({{ site.url }}/assets/posts/img/yeoman.png)

Just to quickly recap the Yeoman setup.

**First**

> npm install yo bower grunt-cli

**Second**

> yo angular

At this point the Angular project scaffolding setup is complete. All your app code is inside the **app** directory. We'll be taking a closer look at the files inside **app** in a bit, however for now try `grunt serve --force`. This will open up a browser pointing to [http://localhost:9000/](http://localhost:9000/) with Yeoman saying 'Allo!

Also, believe it or not, we've already used some [Angular directives](https://docs.angularjs.org/guide/directive), but before that ...

###What is AngularJS?
AngularJS is a Javascript MVC framework that was developed at Google as an open source tool that let user build well structures front end applications. For more information on the project checkout their [homepage](https://angularjs.org/).

AngularJS extends HTML attributes with **Directives**, and binds data to HTML with **Expressions**.

###What are directives?
From the docs:

<i>At a high level, directives are markers on a DOM element (such as an attribute, element name, comment or CSS class) that tell AngularJS's HTML compiler ($compile) to attach a specified behavior to that DOM element or even transform the DOM element and its children</i>.


###Where did we use Directives?

Ok. Time to look at the scaffolding structure that Yeoman setup for us.

Under the **app** directory we have `index.html`. This is the root page that has all the initialization code and our first directive.

**[ng-app](https://docs.angularjs.org/api/ng/directive/ngApp)**: This is used to bootstrap the Angular app. Notice the [<body ng-app="petstoreApp">](https://github.com/khanduri/yeoman-petstore/commit/a9987ca5100048dee3575ffd737dfe82e9233ac1#diff-b9707fe88797285e93483456d1389b61R18) in `app/index.html`.

Another directive that we've already used is **[ng-controller](https://docs.angularjs.org/api/ng/directive/ngController)**. This is where the **C** comes into play in MV**C**. The ng-controller directive specifies a Controller class; the class contains business logic behind the application to decorate the scope with functions and values. Checkout the [<div ng-include="'views/main.html'" ng-controller="MainCtrl"></div>](https://github.com/khanduri/yeoman-petstore/commit/a9987ca5100048dee3575ffd737dfe82e9233ac1#diff-b9707fe88797285e93483456d1389b61R34) in `app/index.html`.

###Our first edit!
Time to make our first change, so lets start with removing the default content from `app/views/main.html` page. We're going to be adding some logic in here that iterates over a predefined list of pets and displaying them on this view.

Lets define our list of pets in the main controller file (aptly named `main.js` found under app/scripts/controller directory). You can find a sample definition [here](https://github.com/khanduri/yeoman-petstore/commit/2674a212a2dafd6cc9a453e92787900de4eb5186#diff-108255b6eb54964fc88aa9594b1d0018R12)

At this point we have the data that we'd like to read. We need to tell our html how to render this information out. For this we'll be using the **[ng-repeat](https://docs.angularjs.org/api/ng/directive/ngRepeat)** directive. The following is what you can use in your `main.js` file.

<script src="https://gist.github.com/khanduri/3a3128efd2e50f8b7ca4.js"></script>

At this point we have a page that's displaying your list of pets .. It should look something like:

![PetStore Index html]({{ site.url }}/assets/posts/img/petstore_index.png)

###What's Next?
We'll pause here and continue with adding more functionality on this store with more Angular directives and some custom directives to really show what it means to write **Expressive HTML** with Angular's help.

regards
