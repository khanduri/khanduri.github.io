---
layout: post
title: "Question: Print Matrix diagonally"
title_section:
    first: "Question: "
    second: "Print Matrix diagonally"
description: ""
image: "/assets/posts/img/interview.jpg"
category: "question"
tags: [algorithm,interview,python]
---
{% include JB/setup %}


###Problem
Given a 2D matrix, print all elements of the given matrix in diagonal order.

![Matrix Base]({{ site.url }}/assets/posts/img/matrix_base.png)

There are 3 diagonal orders that we may want to consider.

1. Row oriented order:

    ![Matrix Row]({{ site.url }}/assets/posts/img/matrix_row.png)

2. Col oriented order:

    ![Matrix Col]({{ site.url }}/assets/posts/img/matrix_col.png)
    *NOTE*: this is just a "flipped" version of case 1

3. Zig Zag:

    ![Matrix ZigZag]({{ site.url }}/assets/posts/img/matrix_zig_zag.png)
    *NOTE*: Assuming we can solve the first 2 cases, this case is just swapping between them


###Approach
I always thought this question was more about tracking indexes carefully, remembering when to increment indexes as we run out of rows to print and have to move forward on columns (and using flags to remember direction in the zig zag case). I recently came across a solution where all of that goes away!

The idea is simple. We need to think in terms of traversing an "inflated" matrix in the row diagonal / column diagonal / zig zag pattern. The "inflated" matrix looks like:

![Matrix Inflated]({{ site.url }}/assets/posts/img/matrix_padded.png)

And here's how to traverse this matrix (making the traversal code just 4 lines!):

![Matrix Traversal]({{ site.url }}/assets/posts/gif/matrix_print.gif)

This means we'll never run out of rows before we're done all entries from the base matrix. Meaning, we can just use a single check and traversal pattern to scan through all entries.

We won't be building this matrix in memory, but the way we traverse our input matrix is going to be based on this "inflated" matrix. For everyone wondering what happens to indexes on this "inflated" matrix, that don't exist in the original base matrix .. we simply skip them!


###Code
<script src="https://gist.github.com/khanduri/a50995d53d49b773ebd0.js"></script>
