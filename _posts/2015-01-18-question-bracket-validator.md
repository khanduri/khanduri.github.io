---
layout: post
title: "Question: Bracket validator"
title_section:
    first: "Question:"
    second: "Bracket validator"
description: ""
category: "question"
tags: [algorithm,interview,python]
---
{% include JB/setup %}

###Problem
Write a braces/brackets/parentheses validator.

> (, {, [ are called "openers"

> ), }, ] are called "closers"

Write an efficient function that tells us whether or not an input string\'s openers and closers are properly nested.

Examples:

> { [ ] ( ) } - should return **true**

> { [ ( ] ) } - should return **false**

> { [ } - should return **false**

###Algorithm
Let's use a Stack to keep track of the open brackets coming in. As we see a close bracket, check its match by popping from the stack.

If we don't see the pop matched, then we return false right away. If we exhaust the stack and are done with the input string, then we know we have a valid bracket string

###My solution
<script src="https://gist.github.com/khanduri/561be1a12969cdc5f178.js"></script>

regards
