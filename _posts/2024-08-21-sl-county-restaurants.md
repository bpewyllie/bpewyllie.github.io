---
layout: post
title: "The best (and worst) restaurants in the rest of the Wasatch Front, according to Google Maps"
date: 2024-08-21
categories: GoogleMaps
published: False
---

This post is a sequel to my guide to [The best (and worst) restaurants in Salt Lake City, according to Google Maps]({% post_url 2024-08-09-slc-restaurants %}). Read on for data, maps, and the top (and bottom) rated restaurants along the Wasatch Front.

***

# Dataset

* I grabbed this data from the Google Maps Places API over the course of the past month. It roughly follows the boundaries of Salt Lake, Utah, Davis, and Weber Counties. This gives **887 total restaurant locations**.
* **79.5%** of the restaurants in the dataset have a **4.0 average rating or higher**
* **50.6%** have a **4.5 rating or higher**
* **53.2%** have a rating between **4.2 and 4.6**

If you trust Google Maps reviews, you can basically discard any options with a sub-4 rating. Anyone know how the reviews are in other cities? I'm wondering if SLC suffers from some sort of ratings inflation that isn't as apparent in cities with a longer-standing food culture.

*Disclaimer: this dataset is surely not comprehensive; let me know if a restaurant you enjoy (or hate) is missing from the list!*

## Methods

The general approach to obtain the data consists of requesting data from the Google Maps Places API - Nearby Search. This endpoint allows you to search for a keyword or type of establishment near a starting point. Up to 60 results can be achieved per search, though this requires pagination (only 20 results per page). The locations are ordered by Google Maps' own internal ranking system, which considers distance and popularity in its algorithm. Thus, to get a comprehensive list of restaurants in a city, we have to search many times, and even this approach does not guarantee comprehensiveness.

The code I wrote for this exercise allows a user to create a grid of points to search around. See below for a trivial example of such a grid, overlaid atop Salt Lake County.

![Salt Lake County Grid](/assets/images/slc_restaurants_grid.png)

Then, given the grid, the code submits GET requests to the Maps endpoint for each point. Clustering the points of the grid more densely leads to greater completeness in the final dataset, but also leads to greater inefficiency in the code execution as most locations are duplicates.

The code repository is available [here](https://github.com/bpewyllie/google_reviews_mapper). 

***

# Conclusions

## Top Rated Restaurants (100+ ratings)

* **Kafe Mamai** downtown, with a 5 star rating over 204 reviews
* **The 14 Peaks** on State St, with a 5 star rating over 262 reviews
* **Parfe Diem Pudding Parfaits** in Sugar House, with a 5 star rating over 140 reviews
* **Mumbai House** on Parleys, with a 4.9 rating over 13,106 reviews
* **Matcha Cafe Kyoto** in Sugar House, with a 4.9 rating over 214 reviews

Given its overwhelming popularity and high rating, I think it's safe to crown **Mumbai House** as the champ of SLC Restaurants.

Another observation: most of the top rated restaurants are cheap. It isn't until *81*^(st) place out of 887 restaurants that we see one with a triple dollar sign rating ($$$) or more--**Matteo Ristorante Italiano** (4.8 over 285 reviews). Most of the top restaurants are food trucks or small mom and pop restaurants that serve more casual crowds.

***

## Worst Rated Restaurants (100+ ratings in SLC Proper; excludes airport locations)

* **Domino's Pizza** on 600 N, with a 2.7 rating over 877 reviews
* **A&W Restaurant** on 4th South, with a 2.9 rating over 109 reviews
* **Homecoming Southern Kitchen & Bar** downtown, with a 3.0 rating over 197 reviews
* **KFC** in Sugar House, with a 3.0 rating over 426 reviews
* **Fried Rice Express** on 4th South and 7th East, with a 3.0 rating over 380 reviews

Many of the worst rated restaurants fall into at least one of these categories:

1. Is a Fast Food Chain
2. Is in the Airport
3. Is in the City Creek Food Court

**Homecoming Southern Kitchen** stands out as different from the rest, and coincidentally it is owned by the same group that owns other low rated restaurants **Fat Jack's Tap House** (3.8 rating over 897 reviews) and **Christopher's Prime** (4.0 rating over 851 reviews). Anyone who has eaten at any of these restaurants want to chime in?

***

## Most "Popular" Restaurants (based on number of ratings)

1. **Mumbai House** (4.9; 13,106)
2. **Red Iguana** (4.6; 9,241) and **Red Iguana 2** (4.6, 7,884)
3. **Lucky 13** (4.6; 7,780)
4. **In-N-Out Burger** (4.5; 6,911) in WVC
5. **The Cheesecake Factory** (4.0, 6,034)

Not surprised to see **Red Iguana** dominating (when you add their two locations together). I was surprised to see **In-N-Out** so high up, but this could be due to there being a lack of In-N-Outs near SLC proper.

***

## (NEW) The Top Chain Restaurants in SL County (highest average ratings for restaurants with >1 location)

## Worst Chain Restaurants in SL County

***

# Map

Here is an interactive map of the restaurants. I only plotted restaurants with at least 10 reviews and an average rating of 4 or higher, giving 678 locations total. The sizes of the points represent relative popularity (number of reviews) and the colors represent quality (average review).

{% include slc_restaurants.html %}

***