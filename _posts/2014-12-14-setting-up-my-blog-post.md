---
layout: post
title: "Setting up my blog post"
title_section:
    first: Setting 
    second: up my blog post
description: ""
category: "setup"
tags: [blog,jekyll,github-pages,jekyll-bootstrap]
---
{% include JB/setup %}

###Basic setup

I recently decided to swtich [my blog](http://techneekr.wordpress.com/), currently hosted on wordpress, to 
[github pages](https://pages.github.com/) and use [jekyll](http://jekyllrb.com/) to generate the site. The 
following is the story of how I set things up!

Github pages has the concept of a *User page* and *Project page*. For a given github account you get a single user page
but you get unlimited project pages. I decided to use the user page to host my blog. Although I've seen examples of 
people using the project pages for their blogs as well. Hopefully soon I'll add 
[my projects](http://ezapps.herokuapp.com/) to the project pages on github.

Github has [excellent documentation](https://pages.github.com/) on getting a basic page hosted 
on *http://khanduri.github.io*. Github also has good documentation on *Blogging with jekyll*, but that's not the 
route I took. I decided to use [jekyll-bootsrap](http://jekyllbootstrap.com/) which was easy to setup, as well.

### Installation 

The following is what I did in order to get he blog setup locally:

    $ ruby --version  # just making sure ruby is installed
    $ gem install bundler
    $ gem install jekyll
    $ git clone https://github.com/plusjade/jekyll-bootstrap.git khanduri.github.io
    $ cd khanduri.github.io
    $ vim _config.yml  # made edits to some obvious placeholder I found
    $ jekyll serve 

It took about a min for `jekyll serve` execution to print out

    Configuration file: /Users/pkhanduri/projects/blog/khanduri.github.io/_config.yml
        Server address: http://127.0.0.1:4000/
        Server running... press ctrl-c to stop.

At which point I could view the template site show up at [localhost:4000](http://localhost:4000). I then decided to 
install *[the-minimum](https://github.com/jekyllbootstrap/theme-the-minimum) theme*, which was as simple as running

    rake theme:install git="https://github.com/jekyllbootstrap/theme-the-minimum.git"

I then made some minor modifications to the theme's page/post layouts and a few more css changes to my liking. I hope to 
build more on this theme and maybe build one from scratch. However, that task is left for the future me to complete.

Finally, pushing this to github was

    git remote set-url origin git@github.com:khanduri/khanduri.github.io.git
    git push origin master

The blog soon appeared on [http://khanduri.github.io/](http://khanduri.github.io/)

regards
