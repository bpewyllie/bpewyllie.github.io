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

Rather than present the data as a single unit, I divided the county into four quadrants (Southwest, Southeast, Northwest, Northeast), roughly defined by I-215 horizontally and I-15 vertically, to find out the top restaurants by region.

## Southwest

### Top Restaurants (>100 reviews)

1.
2.
3.
4.
5.

## Southeast

### Top Restaurants (>100 reviews)

## Northeast

### Top Restaurants (>100 reviews)

## Northwest

### Top Restaurants (>100 reviews)

## 

***

## The Top Chain Restaurants in SL County (highest average ratings for restaurants with >1 location)

## Worst Chain Restaurants in SL County

***

# Map

Here is an interactive map of the restaurants. I only plotted restaurants with at least 10 reviews and an average rating of 4 or higher, giving 678 locations total. The sizes of the points represent relative popularity (number of reviews) and the colors represent quality (average review).

{% include slc_restaurants.html %}

***