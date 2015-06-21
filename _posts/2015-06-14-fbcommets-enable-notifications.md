---
layout: post
title: "FBComments: Enable notifications"
title_section:
    first: "FBComments:"
    second: "Enable notifications"
description: ""
image: "/assets/posts/img/fbcomments.png"
category: "setup"
tags: fb-comments blog
---
{% include JB/setup %}

After fixing the [scoping Facebook comments per blog post]({% post_url 2015-06-13-fbcomments-scoping-them-per-post %}) bug, another thought came to mind. Why did I not get a notification of my friends comment on Facebook? I was sure about Facebook already having such ability, but I wasn't sure if I missed any steps when trying to set this up.

It turns out getting notification on comments is in fact turned off by default and you have to enable it. I couldn't find a straightforward way to get to the settings page and it took a little searching.

The page you want to visit for configuring this is [https://developers.facebook.com/tools/comments/](https://developers.facebook.com/tools/comments/) (be sure to be logged in). Select the app, that maps to the comments section you wish to monitor, from the drop down.

![FB Comments tool landing page]({{ site.url }}/assets/posts/img/fbcomments_tool_landing.png)

Get to the settings page, and add yourself (and/or any individual you are connected to) as a moderator.

![FB Comments tool settings page]({{ site.url }}/assets/posts/img/fbcomments_tool_settings.png)

You will also need to make sure the [FB App](https://developers.facebook.com/apps/) you are using to connect your comment section on, is turned on for general public use.

![FB app settings page]({{ site.url }}/assets/posts/img/fbcomments_app_settings.png)

You should now be able to receive notifications as the comments come in!

![FB notifications working]({{ site.url }}/assets/posts/img/fbcomments_notifications_working.png)

regards
