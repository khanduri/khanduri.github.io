---
layout: post
title: "Fetch rows in random order (seeded)"
title_section:
    first: "Fetch"
    second: "rows in random order (seeded)"
description: ""
image: "/assets/posts/img/postgres.png"
category: "learn"
tags: [flask,sqlalchemy,postgres]
---
{% include JB/setup %}


<i>
NOTE: THE FOLLOWING ONLY WORK for [PostgreSQL](http://www.postgresql.org/). I'm sure there might be ways to achieve the same on other databases, but I didn't get a chance to look into those
</i>

![PostgreSQL Icon]({{ site.url }}/assets/posts/img/postgres.png)

I was almost done implementing pagination on a list page while working on a side project that had a list and detail page. When all of a sudden I this this brilliant idea to get the server to return the list data in random order per user per visit. Ideally you want it returned in some sane ordering (by creation time / item id or some other function yielding some sort of ranking). However I wanted to pursue this "random" idea a little further.

Just to be clear: if UserA and UserB are both visiting my site, UserA get a different shuffle on the item list than UserB. However every other page call within UserA's or UserB's session should abide by the original shuffle (keeping the shuffle consistent for the particular user). In other words I need to place use a seed before randomizing the items. NOTE: I could do this in the app logic itself, but if the data size grows this wasn't feasible, so I wanted to do this at the DB layer.

Before we get to how I solved the issue, We should take a look at how I implemented pagination. Remember: the pages on the paginator should always return the same unshuffled data for each user, but has to change for different users.

Pagination was achieved using simple limits and offsets, as follows:

``` python
PER_PAGE = 20

items = tables.Item.query\
    .limit(PER_PAGE)\
    .offset((page - 1) * PER_PAGE)\
    .all()
```

Now to randomize the order in sqlalchemy we can use the `func.random()` operator in the query we just built:

<i>
NOTE: this only works on Postgres. There are similar `random()` calls defined for Oracle and MySQL dbs, but I don't remember them off the top of my head
</i>

```python
items = tables.Item.query\
    .order_by(func.random())\  # NOTE: This is the only change
    .limit(PER_PAGE)\
    .offset((page - 1) * PER_PAGE)\
    .all()
```

Now this will generate a random list every time the method is invoked. So we need to set a seed right before we make the call, and make sure the result ordering is consistent during a user's visit. We could do it many ways:

1. Use the users session to manage the seed
1. Save some seed information on the cookie
1. Make it part of the query parameter and let the front end code track it

I went with the query parameter approach since I don't have to keep state information on the server that way (session approach) or make it completely consistent for a user (cookie approach, it was ok for the same user to see a different order the next time they visit)

Agnostic of which approach you choose to take, you need to generate the seed and set it for sqlalchemy / postgres to use.

The following is what I did:

```python
from sqlalchemy import text
sql = text('select setseed({0});'.format(SEED_VAL))  # save the SEED_VAL per user/visit
db.engine.execute(sql)
```

Now I think its ugly that I have to [setseed](http://www.postgresql.org/docs/7.4/static/functions-math.html) this way. Although this did the trick for me, I have a feeling there might be a better way to do this. If you know of it, I'd love to learn.

regards
