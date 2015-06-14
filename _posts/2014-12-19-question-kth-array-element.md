---
layout: post
title: "Question: K-th Array Element"
title_section:
    first: "Question:"
    second: "K-th Array Element"
description: ""
image: "/assets/posts/img/interview.jpg"
category: "question"
tags: [python,algorithm,interview,array]
---
{% include JB/setup %}

###Problem
Given an array of integers find the k-th element in the sorted order (not the k-th distinct element).

So, if the array is [3, 1, 2, 1, 4] and k is 3 then the result is 2, because it’s the 3rd element in sorted order
(but the 3rd distinct element is 3)

###Algorithm
An easy way out is by using python *[heapq](https://docs.python.org/2/library/heapq.html)* module. The main idea being
keep a priority queue of length *k* while reading the input stream of values. Once done, just pop what's at the top.

###My solution

<script src="https://gist.github.com/khanduri/7c1278a0448402eebac5.js"></script>

regards
