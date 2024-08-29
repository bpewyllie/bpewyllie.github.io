---
layout: post
title: "The best (and worst) restaurants in the rest of Salt Lake County, according to Google Maps"
date: 2024-08-21
categories: GoogleMaps
published: False
---

This post is a sequel to my guide to [The best (and worst) restaurants in Salt Lake City, according to Google Maps]({% post_url 2024-08-09-slc-restaurants %}). Read on for data, maps, and the top restaurants by region of the valley.

***

# Dataset

* I grabbed this data from the Google Maps Places API over the course of the past month. It roughly follows the boundaries of Salt Lake, Utah, Davis, and Weber Counties. This gives **2,695 total restaurant locations**.
* **~75%** of the restaurants in the dataset have a **4.0 average rating or higher**, with the median rating being a **4.3**.

*Disclaimer: this dataset is surely not comprehensive; let me know if a restaurant you enjoy (or hate) is missing from the list!*

## Methods

The general approach to obtain the data consists of requesting data from the Google Maps Places API - Nearby Search. This endpoint allows you to search for a keyword or type of establishment near a starting point. Up to 60 results can be achieved per search, though this requires pagination (only 20 results per page). The locations are ordered by Google Maps' own internal ranking system, which considers distance and popularity in its algorithm. Thus, to get a comprehensive list of restaurants in a city, we have to search many times, and even this approach does not guarantee comprehensiveness.

The code I wrote for this exercise allows a user to create a grid of points to search around. See below for a trivial example of such a grid, overlaid atop Salt Lake County.

![Salt Lake County Grid](/assets/images/slc_restaurants_grid.png)

Then, given the grid, the code submits GET requests to the Maps endpoint for each point. Clustering the points of the grid more densely leads to greater completeness in the final dataset, but also leads to greater inefficiency in the code execution as most locations are duplicates.

The code repository is available [here](https://github.com/bpewyllie/google_reviews_mapper). 

***

# Conclusions

Rather than present the data as a single unit, I divided the county into four quadrants (Southwest, Southeast, Northwest, Northeast), roughly defined by the I-215 - I-15 interchange.

## Southwest - West Jordan, South Jordan, Herriman, Riverton, Bluffdale, and western Midvale

### Top Rated Restaurants (>100 reviews)

1. Tacos El Pariente Main Office - Midvale (5.0, 131)
2. Hruska's Kolaches - West Jordan (4.9, 320)
3. Rio Acai - South Jordan (4.9, 428)
4. Aunty's Hawaiian Kitchen - Riverton (4.8, 362)
5. Bombay Garden - Cuisine of India - West Jordan (4.8, 4648)

### Most Popular Restaurants

0. Topgolf - Midvale (4.4, 5383) (*while technically they serve food, I don't think this should really count*)
1. Bombay Garden - Cuisine of India - West Jordan (4.8, 4648)
2. Texas Roadhouse - South Jordan (4.4, 4531)
3. Black Bear Diner - West Jordan (4.0, 4227)
4. In-N-Out Burger - West Jordan (4.5, 3547)
5. Olive Garden - South Jordan (4.2, 3421)

### Other Noteworthy Picks

## Southeast - Draper, Sandy, Midvale, Cottonwood Heights, and southern Murray

### Top Restaurants (>100 reviews)

1. Taqueria Los Primos - Draper (5.0, 129)
2. La Fogata Delicious Tacos Taco cart - Sandy (4.9, 235)
3. Nautical Bowls - Sandy (4.9, 175)
4. Pork N Roll - Draper (4.9, 102)
5. Robeks Fresh Juices & Smoothies - Sandy (4.9, 129)

### Most Popular Restaurants

1. The Cheesecake Factory - Murray (4.0, 6104)
2. Texas Roadhouse - Sandy (4.3, 4580)
3. Golden Corral Buffet & Grill - Midvale (4272, 3.9)
4. In-N-Out Burger - Midvale (4.5, 4119)
5. In-N-Out Burger - Draper (4.5, 4059)

### Other Noteworthy Picks

## Northeast - SLC, Murray, Millcreek, Holladay, South Salt Lake

[See my post on SLC specifically for more detail](({% post_url 2024-08-09-slc-restaurants %})). Rather than listing the same restaurants, here I'll include places either that I missed or were outside of my previous sample's search radius.

### Top Restaurants (>100 reviews)

1. Blatch's BBQ - SLC (5.0, 224)
2. Bombay Palace - Murray (4.9, 642)
2. 9-UP Night Market Food Trucket - Millcreek (4.9, 110)
3. Aranya Thai Kitchen - SLC (4.9, 173)
4. 
5.

### Most Popular Restaurants

1. The Cheesecake Factory - SLC (4.0, 6034)
2. Paradise Buffet - Murray (4.2, 5420)
3. Rodizio Brazilian Steakhouse - SLC (4.5, 5293)
4. Ruth's Diner - Emigration Canyon (4.6, 5268)
5. Crown Burgers - 118 N 300 W SLC (4.4, 4911)

### Other Noteworthy Picks

## Northwest - SLC, WVC, Murray, Taylorsville, Magna, Kearns, and western Millcreek

### Top Restaurants (>100 reviews)

1. Protein Cheers Nutrition - WVC (5.0, 120)
2. Victor's pizza co - Millcreek (4.9, 633)
3. Aroon Thai Kitchen - Murray (4.9, 562)
4. Cupbop Korean BBQ - Taylorsville (4.9, 119)
5. El Comal - Magna (4.9, 115)

### Most Popular Restaurants

1. Red Iguana - SLC (4.6, 9246)
2. Red Iguana 2 - SLC (4.6, 7892)
3. Texas Roadhouse - Taylorsville (4.4, 7623)
4. In-N-Out Burger - WVC (4.5, 6956)
5. Cracker Barrel Old Country Store - WVC (4.2, 5408)

### Other Noteworthy Picks

***

## The Top Chain Restaurants in SL County (highest average ratings for restaurants with >1 location)

## Worst Chain Restaurants in SL County

***

# Map

Here is an interactive map of the restaurants. I only plotted restaurants with at least 10 reviews and an average rating of 4 or higher, giving 678 locations total. The sizes of the points represent relative popularity (number of reviews) and the colors represent quality (average review).

{% include slc_restaurants.html %}

***