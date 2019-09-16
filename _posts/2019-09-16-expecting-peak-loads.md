---
layout: post
title: Background Processing &ndash; Dealing With Peak Loads  
---

It is extremely useful to unload some asynchronous processing to background workers
to ensure smooth synchronous web requests processing and improving overall web site performance. 
E.g., at [drop2amz](https://drop2amz.com) we run all user searches in background, as well as periodic refreshes, orders and inventory sync and many more.

![performance chart](/images/performance-screenshot.png)

Every day we process more than 30,000,000 background tasks, and at times it can get particularly challenging
to evenly process the queue and ensure lowest latencies. However, the load is variable throughout the day.
Of course we could spin up a few dozens cloud workers to just stay there to handle peak loads,
but that is a waste of money and resources. 

## Dynamic Scaling &ndash; Cure or Curse?

A wiser solution is to deploy more resources as demand grows - the higher is average load, the more resources you deploy.
However this approach has one flaw - since it is based on moving average, **it has some noticeable lag**,
so you may suffer over-load until the new resources got deployed, configured and actually kick in.

## Data Science to the Rescue!

An even wiser approach would be to analyze load statistics for past periods and calculate expectations of throughput increasing / decreasing.
Since usually it depends on a number of factors like time of day, day of week and other variables that can be quantified and used in the calculations,
we can calculate such expectations. This way we can spin up additional resources in advance and prevent latency from growing.