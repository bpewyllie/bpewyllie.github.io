---
layout: post
title: "The best (and worst) restaurants in Salt Lake City, according to Google Maps"
date: 2024-08-09
categories: GoogleMaps
---

When I am looking for new places to eat, I usually rely on Google Maps. Over time, I've noticed a couple of flaws with this approach:

1. *Google doesn't show you everything in the map.* You can search for "restaurants" in an area and some will be hidden even at the closest zoom level unless you search for the place by its exact name. This makes it hard to find new places to eat at until they're already popular. Grabbing the data directly from the source allows me to form more comprehensive rankings.
2. *People are very hesitant to give places anything less than a 5 star rating.* I had a hunch that the "true" rating scale was from 4 to 5, as it's rare for a restaurant to be less than a 4, so I wanted to see how accurate that was.

Keep reading for some stats and maps of the results.

***

# Dataset

* I grabbed this data from the Google Maps Places API on August 6, 2024. It roughly follows SLC Boundaries, but reaches a little into southern suburbs and WVC. This gives **887 total restaurant locations**.
* **79.5%** of the restaurants in the dataset have a **4.0 average rating or higher**
* **50.6%** have a **4.5 rating or higher**
* **53.2%** have a rating between **4.2 and 4.6**

If you trust Google Maps reviews, you can basically discard any options with a sub-4 rating. Anyone know how the reviews are in other cities? I'm wondering if SLC suffers from some sort of ratings inflation that isn't as apparent in cities with a longer-standing food culture.

***

# Top Rated Restaurants (100+ ratings in SLC Proper)

* **Kafe Mamai** downtown, with a 5 star rating over 204 reviews
* **The 14 Peaks** on State St, with a 5 star rating over 262 reviews
* **Parfe Diem Pudding Parfaits** in Sugar House, with a 5 star rating over 140 reviews
* **Mumbai House** on Parleys, with a 4.9 rating over 13,106 reviews
* **Matcha Cafe Kyoto** in Sugar House, with a 4.9 rating over 214 reviews

Given its overwhelming popularity and high rating, I think it's safe to crown **Mumbai House** as the champ of SLC Restaurants.

Another observation: most of the top rated restaurants are cheap. It isn't until *81*^(st) place out of 887 restaurants that we see one with a triple dollar sign rating ($$$) or more--**Matteo Ristorante Italiano** (4.8 over 285 reviews). Most of the top restaurants are food trucks or small mom and pop restaurants that serve more casual crowds.

***

# Worst Rated Restaurants (100+ ratings in SLC Proper; excludes airport locations)

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

# Most "Popular" Restaurants (based on number of ratings)

1. **Mumbai House** (4.9; 13,106)
2. **Red Iguana** (4.6; 9,241) and **Red Iguana 2** (4.6, 7,884)
3. **Lucky 13** (4.6; 7,780)
4. **In-N-Out Burger** (4.5; 6,911) in WVC
5. **The Cheesecake Factory** (4.0, 6,034)

Not surprised to see **Red Iguana** dominating (when you add their two locations together). I was surprised to see **In-N-Out** so high up, but this could be due to there being a lack of In-N-Outs near SLC proper.

***

# Hand-Picked Hidden Gems (interesting, highly rated restaurants with <=50 reviews)

* **El Zamorano** (5.0, 25) - Poplar Grove Mexican restaurant
* **Fresh Sushi** (4.9, 37) - inside the University of Utah Hospital
* **Marcato Kitchen** (4.9, 49) - serving stromboli inside Square Kitchen
* **The GM Guy Cafe** (4.7, 35) - good vibes and diner fare inside a car dealership
* **Janis Filipino Cuisine** (4.6, 50) - located inside **Salt Lake City Eats** off North Temple, a kitchen space for to-go meals

I haven't been to any of these places so let me know if the numbers lie!

***

# Map

Here is an interactive map of the restaurants. I only plotted restaurants with at least 10 reviews and an average rating of 4 or higher, giving 678 locations total. The sizes of the points represent relative popularity (number of reviews) and the colors represent quality (average review).

{% include slc_restaurants.html %}

***