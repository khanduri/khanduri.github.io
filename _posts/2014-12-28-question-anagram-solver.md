---
layout: post
title: "Question: Anagram Solver"
title_section:
    first: "Question:"
    second: "Anagram Solver"
description: ""
image: "/assets/posts/img/interview.jpg"
category: "question"
tags: [python,algorithm,interview,anagram]
---
{% include JB/setup %}

###Problem
Given a list of input strings, check to see if any anagrams of these strings can be found in a predefined set of
valid strings.

###Algorithm
The main idea here is to sort the input and sort the valid dictionary terms so there *sorted* representation looks
alike. All these anagrams will have the same sorted representation, and can be placed in a python dict to be looked up
in O(1).

###My solution

<script src="https://gist.github.com/khanduri/f63c8407f74a3ffc3c27.js"></script>

###Resources

 > [Valid word dictionary]({{ site.url }}/assets/posts/data/anagram_valid_words_list.txt)

regards
