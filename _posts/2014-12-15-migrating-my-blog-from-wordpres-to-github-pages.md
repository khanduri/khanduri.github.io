---
layout: post
title: "Migrating my blog from wordpress to Github Pages"
title_section:
    first: Migrating 
    second: my blog
description: ""
category: "setup"
tags: [jekyll,github-pages,blog,wordpress,jekyll-import]
---
{% include JB/setup %}

###Prerequisites

I wanted to move my posts from my [old blog](http://techneekr.wordpress.com/) to this new space. If you're hoping to 
do the same, first you need to be ready with your Github pages *User Page* setup. You can find information for those 
steps in [my previous post]({% post_url 2014-12-14-setting-up-my-blog-post %})

[Jekyll](http://jekyllrb.com/) has an easy to use importer, aptly named 
[jekyll-import](https://github.com/jekyll/jekyll-import) that we'll be using down the line. To get it installed,
all we need is a `gem install jekyll-import`

NOTE: These steps are for migrating from Wordpress, but [jekyll importer](http://import.jekyllrb.com/) supports a wide 
range of available importers to choose from.

###Migration
We first need to get to the admin export page on wordpress at 
[https://YOUR-USER-NAME.wordpress.com/wp-admin/export.php](https://YOUR-USER-NAME.wordpress.com/wp-admin/export.php). 
I chose to download all content of my blog and saved it in a file named *wordpress.xml*.

![Exporting from Wordpress admin console]({{ site.url }}/assets/exporting_from_wordpress_admin_console.png)

Move *workpress.xml* into a new folder (or the root directory of your blog) and run the following:
`ruby -rubygems -e 'require "jekyll-import"; JekyllImport::Importers::WordpressDotCom.run({ "source" => "wordpress.xml" })’`

This will generate a few folders for us. In my case they generated 4 folders:
    
    *_posts*: the core content of my blog posts
    *assets*: the media files (mainly images) used on my blog
    *_pages*: my about page from the wordpress blog
    *_attachments*: I don't really know what this saved. It seems to contain some metadata about the assets I had

I'm planning to make a few modifications before I post those entries here (meaning I'm planning on making some changes 
to the files in *_posts*. I can keep the *assets* file as is and merge it with my new blog *assets* folder. I'm 
planning on getting rid of the *_pages* section for now, since it only has my old about page. And I don't know what 
the use of the *_attachment* folder is. Hopefully I'll update this blog once I get to know what that did.

Let me know how it went for you if you chose a similar path.

regards
