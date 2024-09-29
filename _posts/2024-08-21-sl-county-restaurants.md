---
layout: post
title: "The best (and worst) restaurants in the rest of Salt Lake County, according to Google Maps"
date: 2024-08-21
tags: Utah GoogleMaps
published: True
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

Rather than present the data as a single unit, I divided the county into four quadrants (Southwest, Southeast, Northwest, Northeast), roughly defined by the I-215 - I-15 interchange. Only non-chain restaurants are included in these sections.

## Southwest - West Jordan, South Jordan, Herriman, Riverton, Bluffdale, and western Midvale

### Top Rated Restaurants (>100 reviews)

1. Hruska's Kolaches - West Jordan (4.9, 320)
2. Rio Acai - South Jordan (4.9, 428)
3. Aunty's Hawaiian Kitchen - Riverton (4.8, 362)
4. Bombay Garden - Cuisine of India - West Jordan (4.8, 4648)
5. Dee Garden Thai Kitchen - West Jordan (4.8, 439)

### Most Popular Restaurants

1. Bombay Garden - Cuisine of India - West Jordan (4.8, 4648)
2. Bawarchi - South Jordan (4.6, 2307)
3. Puerto Vallarta Mexican Grill and Cantina - West Jordan (4.4, 1994)
4. Lucky's Iron Door Roadhouse - West Jordan (4.3, 1772)
5. Tacos Lopez Tijuana Style - West Jordan (4.5, 1767)

### Lesser Known Picks (<200 reviews)

1. Katsu City - West Jordan (4.9, 52) - *korean casual*
2. Bocados Venezuelan Food - South Jordan (4.7, 54) - *food truck empanadas*
3. Spice Bay - West Jordan (4.8, 123) - *casual Indian*
4. Arigato Sushi - West Jordan (4.7, 101) - *unique sushi rolls*
5. Sukihana - South Jordan (4.7, 170) - *sushi and other Japanese dishes*

## Southeast - Draper, Sandy, Midvale, Cottonwood Heights, and southern Murray

### Top Restaurants (>100 reviews)

1. Taqueria Los Primos - Draper (5.0, 129)
2. La Fogata Delicious Tacos Taco cart - Sandy (4.9, 235)
3. Nautical Bowls - Sandy (4.9, 175)
4. Pork N Roll - Draper (4.9, 102)
5. Robeks Fresh Juices & Smoothies - Sandy (4.9, 129)

### Most Popular Restaurants

1. Belgian Waffle & Omelet Inn - Midvale (4.0, 3574)
2. Midvale Mining Cafe & Catering - Midvale (4.3, 3566)
3. Lone Star Taqueria - Cottonwood Heights (4.6, 3377)
4. Yi Sushi Bistro - Midvale (4.3, 2280)
5. The Philadelphian - Sandy (4.5, 2197)

### Lesser Known Picks (<200 reviews)

1. Las Ellie's Foodtruck - Cottonwood Heights (4.9, 59) - *mexican food truck specializing in tortas*
2. Tacos El Calentano - Sandy (4.9, 88) - *street tacos*
3. The Peppered Vine - Sandy (4.9, 72) - *fresh sandwiches and salads, plus daily specials*
4. Supremo Pizza - Midvale (4.7, 183) - *new york style pizza*
5. Susy's Kitchen - Midvale (4.7, 134) - *laid back, southern italian*

## Northeast - SLC, Murray, Millcreek, Holladay, South Salt Lake

[See my post on SLC specifically for more detail](({% post_url 2024-08-09-slc-restaurants %})). Rather than listing the same restaurants, here I'll include places either that I missed or were outside of my previous sample's search radius.

### Top Restaurants (>100 reviews)

1. Blatch's BBQ - SLC (5.0, 224)
2. Bombay Palace - Murray (4.9, 642)
3. 9-UP Night Market Food Trucket - Millcreek (4.9, 110)
4. Aranya Thai Kitchen - SLC (4.9, 173)
5. Bhansa Ghar - SLC (4.9, 735)

### Most Popular Restaurants

1. Mumbai House - SLC (4.9, 13312)
2. Paradise Buffet - Murray (4.2, 5420)
3. Ruth's Diner - Emigration Canyon (4.6, 5268)
4. The Park Cafe - SLC (4.7, 3798)
5. The Dodo Restaurant - SLC (4.4, 3540)

### Other Noteworthy Picks

1. Early Owl - SLC (5.0, 39) - *recently opened brunch spot*
2. Encanto Restaurant - SLC (4.9, 33) - *colombian food with nice vibes*
3. Vegan Daddy Meats - SLC (4.9, 98) - *the plant "butcher"*
4. Uncle Hot Pot & All you can eat - SLC (4.8, 110) - *extravagant seafood hot pot*
5. Drunken Kitchen - SLC (4.7, 84) - *taiwanese and chinese classics*

## Northwest - SLC, WVC, Murray, Taylorsville, Magna, Kearns, and western Millcreek

### Top Restaurants (>100 reviews)

1. Protein Cheers Nutrition - WVC (5.0, 120)
2. Victor's pizza co - Millcreek (4.9, 633)
3. Aroon Thai Kitchen - Murray (4.9, 562)
4. El Comal - Magna (4.9, 115)
5. Chang's Food - WVC (4.8, 1170)

### Most Popular Restaurants

1. Red Iguana + Red Iguana 2 - SLC (4.6, 9246 + 7892)
2. King Buffet - Taylorsville (4.0, 4455)
3. El Paisa Grill - WVC (4.2, 3248)
4. La Casa Del Tamal - WVC (4.6, 2390)
5. Ogie's Cafe - WVC (4.6, 2372)

### Other Noteworthy Picks

1. Jade's Corner Deli LLC - Taylorsville (5.0, 75) - *vietnamese food in an airy atmosphere*
2. Habanero Express - South Salt Lake (4.9, 47) - *mexican classics*
3. Kika's Kitchen - WVC (4.9, 30) - *gigantic burritos*
4. Elko Cafe - SLC (4.8, 39) - *chinese dishes and sushi rolls*
5. Namash Swahili Cuisine - SLC (4.9, 53) - *food truck operating out of Square Kitchen*

***

## The Top Chain Restaurants in SL County (highest median ratings for restaurants with at least 5 locations)

1. Cupbop - Korean BBQ in a Cup (4.7 median rating; 12 locations)
2. In-N-Out Burger (4.5 median rating; 5 locations)
3. Swig (4.5 median rating; 13 locations)
4. Mo' Bettahs Hawaiian Style Food (4.45 median rating; 6 locations)
5. Zao Asian Cafe (4.5 median rating; 9 locations)

## Worst Chain Restaurants in SL County

***

1. It's Just Wings (Chili's [ghost restaurant](https://en.wikipedia.org/wiki/Virtual_restaurant)) (2.9 median rating; 5 locations)
2. Pizza Hut (3.0 median rating; 28 locations - not including Pizza Hut Express)
3. KFC (3.05 median rating; 14 locations)
4. Chipotle Mexican Restaurant (3.3 median rating;  11 locations)
5. A&W Restaurant (3.4 median rating; 7 locations)

## Most Popular Chain Restaurants in SL County (ranked by number of total reviews across all locations)

1. McDonald's (73,059 reviews; 40 locations)
2. Cafe Rio Fresh Modern Mexican (28,194 reviews; 20 locations)
3. Wendy's (27,432 reviews; 28 locations)
4. Chick-fil-A (24,350 reviews; 12 locations)
5. In-N-Out Burger (21,882 reviews; 5 locations)

## Busiest Chain Restaurants in SL County (ranked by average number of reviews per location)

1. In-N-Out Burger (4,376 average reviews; 5 locations)
2. Olive Garden Italian Restaurant (3,526 average reviews; 5 locations)
3. Black Bear Diner (3,321 average reviews; 5 locations)
4. Apollo Burger (2,675 average reviews; 7 locations)
5. Buffalo Wild Wings (2,638 average reviews; 5 locations)

# Map

Here is an interactive map of the restaurants. I only plotted restaurants with at least 10 reviews and an average rating of 4 or higher, giving 1,761 locations total. The sizes of the points represent relative popularity (number of reviews) and the colors represent quality (average review).

{% include slc_restaurants.html %}

***