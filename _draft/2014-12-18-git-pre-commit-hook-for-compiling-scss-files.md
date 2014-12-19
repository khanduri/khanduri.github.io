---
layout: post
title: "Git pre commit hook for compiling scss files"
title_section: 
    first: "Git"
    second: "pre commit hook for compiling scss files"
description: ""
category: ""
tags: [git,git-hook,scss]
---
{% include JB/setup %}

If using git, we can add a pre-commit hook for our repository that runs right before commiting your changes

chmod +x .git/hooks/pre-commit

if git status -s | grep  '^M.\+s[ac]ss$'
then
    for a in $(find . -name "*.scss" | grep -v _site)
    do
        echo "sass ${a:2} ${a:2:${#a}-7 }.css;"
        sass ${a:2} ${a:2:${#a}-7 }.css;
        git add ${a:2:${#a}-7 }.css;
    done
fi


Desired: 
 - while testing .. make modification to scss files and compile them after making the change
sass --watch

 - when committing .. minimize the compiled css files .. 
--style compressed

   * pkhanduri:~/projects/blog/khanduri.github.io (master)$sass --watch assets/themes/the-minimum/css/:assets/themes/the-minimum/css/ --style compressed
>>> Sass is watching for changes. Press Ctrl-C to stop.
>>> Change detected to: assets/themes/the-minimum/css/constants.scss
      write assets/themes/the-minimum/css/base.css
      write assets/themes/the-minimum/css/base.css.map
      write assets/themes/the-minimum/css/constants.css
      write assets/themes/the-minimum/css/constants.css.map
      write assets/themes/the-minimum/css/style.css
      write assets/themes/the-minimum/css/style.css.map
      write assets/themes/the-minimum/css/syntaxhighlighter.css
      write assets/themes/the-minimum/css/syntaxhighlighter.css.map
