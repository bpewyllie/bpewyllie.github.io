---
layout: post
title: "Is ignorance bliss? Salt Lake County restaurant health inspection grades, ranked best to worst."
date: 2024-09-15
categories:
published: False
---

Salt Lake County's Health Department collects great data on different types of establishments' adherence to health and safety guidelines. I thought it'd be interesting to grab this data, specifically for restaurants, and see who are the worst offenders. If you don't share my natural curiosity for this, I'd recommend turning back now. Otherwise, read on for insights on the cleanest (and dirtiest) restaurants in the county as well as some county-wide trends and maps.

***

# Dataset

The data comes from the [Salt Lake County Health Department's Inspections page](https://www.saltlakecounty.gov/health/inspection/). I scraped this data on 9/14/2024. It includes (up to) the ten most recent inspections for all currently in-business establishments. The dataset includes **5,311** establishments and **31,745** individual inspections.

## Definitions

The Health Department has two different ways of measuring establishments: a relative **ranking** and an absolute **score**. 

The **ranking** value is expressed as a percentage of establishments with a similar "risk level" that perform worse on health and safety, where all establishments are grouped into one of four risk levels based on probability of contamination. For example, if a sushi restaurant has a ranking of 45%, that means it scores better than 45% of similar establishments (worse than 55%). Higher rankings are better.

The **score** value is a cumulation of strikes against an establishment for health and safety violations, where each strike counts as 1, 3, or 6 points depending on severity. There is no upper limit on an establishment's score. Lower scores are better.

You can read more about rankings, scores, and risk levels on the [Health Department's website](https://www.saltlakecounty.gov/health/food-protection/inspections/).

## Methods

The approach I used to grab the data consists of a simple scraper that submits parameters to the site's ASP.NET form and paginates to retrieve all data. To retrieve latitude and longitude coordinates for mapping purposes, I use the `geopy` package to geocode the provided addresses.

The code can be accessed at [my GitHub](https://github.com/bpewyllie/slc_health_inspections).

***

# Conclusions

## The Good - highest ranked establishments

Below are the top 5 rankings by type for bar, coffee shop, food truck, and restaurant types. There are a lot of weird records in the data (dog patios, duplicates, and mis-categorized establishments) that I've manually excluded. Remember that high rankings are good, and high scores are bad.

In summary, if you care *solely* about sanitation standards, I'd recommend eating and drinking at high-end hotels and large chains.

### Bars

1. **Alta's Rustler Lodge** (100%; 8)
2. **Hilton SLC Lounge** (100%; 12)
3. **Grand America Hotel - The Gibson Lounge**, SLC (100%; 14)
4. **Baldy Brews at the Alta Watson Shelter** (100%; 25)
5. **Bongo Lounge**, SLC (93%, 14)

### Coffee Shops / Cafes

1. **Starbucks**, various locations; best location is in the 8th S 9th E Smith's (100% rating; max score of 6)
2. **3 Cups**, Woodbine Food Hall, SLC (100%; 12)
3. **Beans and Brews**, various locations; best location is in the airport (96%; 15)
4. **Brio Cafe** in the University of Utah's Biology Building (93%; 14)
5. **District Coffee Co**, SLC (93%; 15)

### Food Carts & Trucks

1. **La Catrina Flavors of Mexico**, South Salt Lake (100% rating; max score of 7)
2. **Smoke-A-Billy BBQ & Grill**, South Salt Lake (100%; 7)
3. **Pig Boys**, Millcreek (100%; 8)
4. **Tacos El Conde**, SLC (100%; 9)
5. **Touch of Polynesia**, West Valley City (100%; 9)

### Restaurants

1. **Fillings and Emulsions** in the airport (100% rating; max score of 3)
2. **Sweetaly Gelato**, Holladay (100% rating; max score of 3)
3. **Wendy's**, various locations; best location is 5673 W 6200 S, West Valley City (100%; 4)
4. **McDonald's**, various locations; best location is 2310 E 2100 S, SLC (100%; 20)
5. **In-N-Out Burger**, various locations; best location is 7206 S Union Park Ave, Midvale (99%; 7) 

## The Bad - lowest ranked establishments

Below are the bottom 5 rankings by type for bar, coffee shop, food truck, and restaurant types. As before, I've manually excluded any unusual data.

In summary, if you care *solely* about sanitation standards, I'd avoid eating and drinking at buffets and smaller mom-and-pop places.

### Bars

1.
2.
3.
4.
5.

### Coffee Shops / Cafes

1.
2.
3.
4.
5.

### Food Carts & Trucks

1.
2.
3.
4.
5.

### Restaurants

1.
2.
3.
4.
5.

## The Ugly - the worst individual inspections

Below are the worst individual inspections in the dataset, ranked on total score (high = bad).

1. **King Buffet**, South Salt Lake - April 25, 2024 (266 Total Score; 28 Critical Violations)

    *description*

2. **Seafood Bucket Cajun Style**, South Salt Lake -

    **

3. ****

    **

4. ****

    **

5. ****

    **

As a point of reference, below are the summary stats for *all* inspections' scores in the dataset:
* 1st quartile: 5
* Median: 12
* 3rd quartile: 24

## Overall Trends

restaurants with biggest improvements

restaurants with biggest falls

overall health trends (average scores over time)

map of current rankings

what cities have the best rankings
