---
layout: post
title: "Utah billboards and distracted driving accidents"
date: 2022-01-26
categories: Billboards
---

Billboards are designed to distract drivers. Can we demonstrate how effective they are in the data?

***

# Dataset

To answer this question, I combine two datasets:

* Car crash data, from the Utah Department of Public Safety's Highway Safety Office. This includes (albeit sparsely) police officers' determination of what caused the crash.

* Billboard data, from the Utah Department of Transportation's LiDAR inventory of state and federally funded routes.

## Methods

This post is not designed to answer the deeper question of whether billboards distract drivers so much that they actually *cause* them to crash at higher rates. Instead, I am only interested in mapping the two datasets and seeing if any obvious trends appear.

***

# Conclusions

The current data sets are too limited to offer much insight. Responding police officers rarely fill out reports comprehensively, and so the population of "distracted driving" accidents, let alone those directly attributable to "Signs/billboards/etc." is too small. Moreover, the billboard inventory is restricted to major roads. Regardless, the fact that there are any instances where police officers have cited billboards as a contributing circumstance in car crashes (about 50 in a 10-year period) is amusing to me.

## Limitations

Even with perfect versions of the acquired datasets, analysis would be limited to drawing a associative link between billboards and car crashes. It would be more interesting to see something resembling a natural experiment.

## Opportunities

Given that UDOT completes its LiDAR-captured inventory of billboards on major routes on a periodic basis (roughly every 2-3 years), it's possible to construct a dataset of "new" billboards and estimate their date of construction. We can also construct the inverse; that is, a dataset of billboards that have been dismantled and their rough date of deconstruction. In doing so, we can design a natural experiment: over a given stretch of road, how many accidents occur when a billboard is present versus when a billboard is not present?

***

# Map

{% include ut_billboard_crashes.html %}

***