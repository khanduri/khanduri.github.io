---
layout: post
title: "VimTrick - Enable spellcheck on markdown files"
title_section:
    first: "VimTrick"
    second: " - Enable spellcheck on markdown files"
description: ""
image: "/assets/posts/img/vim.jpg"
category: "trick"
tags: [vim,markdown]
---
{% include JB/setup %}

I was just cleaning up my [dotfiles](https://github.com/khanduri/dotfiles),
particularly my [vimrc](https://github.com/khanduri/dotfiles/blob/master/vimrc)
file. While doing so, I realized I've been triggering spell check on my
markdown files when I'm done writing my posts (as a sanity check). I did so
by `:setlocal spell` in vim.

Well as soon as you one notices a pattern, they should also try to figure out
how to automate it. In my case it was making some edit in my vimrc files to
run the check as I'm making the edits on my markdown files. This can be done
by:

<pre>autocmd BufNewFile,BufRead *.mkd,*.md,*.mdown,*.markdown set spell</pre>

As you can imagine, we can define more file extensions here and make sure
they run spell checks there too.

I have something similar for my python source files too :)

regards
