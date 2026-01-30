---
layout: post
title: "The best (and worst) apartments in Salt Lake City, according to Google Maps"
date: 2026-01-30
tags: Utah GoogleMaps
published: True
---

With [more reports that rent is falling in Salt Lake City](https://buildingsaltlake.com/rent-is-falling-in-salt-lake-city-its-putting-the-squeeze-on-low-income-housing-developers/), there is less reason than ever to settle on a bad place to live. That's why I decided to grab every apartment I could find from Google Maps and rank them.

Before getting to the data, a couple of caveats:

1. This dataset isn't comprehensive, it's just what I was able to get from Google Maps with minimal effort. For various reasons, not every apartment shows up under this approach.
2. Google Maps is not the end-all, be-all when it comes to rating apartments. Google reviews can be manipulated and the 5-star scale doesn't leave much room for nuance.

***

# Dataset

I grabbed this data from the Google Maps Places API on January 25, 2026 by searching for apartment buildings and apartment complexes in Salt Lake Valley. After dropping anything with less than 10 reviews, I'm left with **445** distinct apartments.

* **Roughly half** of all apartments in the valley have a rating between **3.4 and 4.2**. 
* **Salt Lake City** accounts for **48%** of the apartments in the valley, followed by Midvale (**8.3%**), West Valley City (**6.7%**), and Murray (**6.5%**). The southern suburbs of the valley (Riverton, Herriman, Draper, Sandy, and Bluffdale) amount to just **7.6%** of the valley's apartments.
* Apartments closer to SLC also have fewer reviews on average (likely due to the prevalence of both small and new buildings) compared to the southern end. The median number of ratings for an apartment in SLC is just **38**, compared to **227** in South Jordan and **172** in Sandy.

## Methods

I've used a nearly identical approach to obtain Google Maps data in the past for [restaurant reviews]({% post_url 2024-08-09-slc-restaurants %}). The apartment search results seem to have more noise than restaurants, as I filtered out over half the locations immediately by dropping places with few (<10) reviews.

***

# Conclusions

## Top Rated Apartments (100+ ratings)

1. **Seasons at Library Square Apartments** - 310 E 500 S, SLC, with a **4.9** star rating over **327** reviews
2. **Seasons at Murray Crossing Apartments** - 196 W Vine St, Murray, with a **4.8** star rating over **413** reviews
3. **Parc Ridge Apartments** - 13129 Tower Ridge Dr, Riverton, with a **4.8** star rating over **166** reviews
4. **Seasons on City Creek Apartments** - 230 W North Temple, SLC, with a **4.7** star rating over **403** reviews
5. **Braxton at Trolley Square** - 727 E 600 S, SLC, with a **4.7** star rating over **127** reviews

What's going on with apartments named *Seasons*? 3 out of the 4 apartments with "Seasons" in their name in the dataset are in the top 5. Unfortunately, the fourth one--Seasons at Pebble Creek (1616 W Snow Queen Pl, SLC)--drags down the group's average with its 2.9 star rating.

***

## Worst Rated Apartments (100+ ratings)

1. **Brickgate at Fireclay** - 162 W 4490 S, Murray, with **2.3** stars over **191** reviews
2. **47seventy Settler's Point** - 4770 S Simmental Dr, Taylorsville, with **2.6** stars over **275** reviews
3. **Santa Fe at Cottonwood** - 1550 Fort Union Blvd, Cottonwood Heights, with **2.8** stars over **366** reviews
4. **Atherton Park Apartments** - 4545 Atherton Dr, Taylorsville, with **2.8** stars over **229** reviews
5. **Village at River's Edge** - 1251 W Village Main Dr, West Valley City, with **2.8** stars over **151** reviews

Interestingly enough, 3 of the worst 5 (1, 2, and 4) are all within a couple miles of each other and sit along the Taylorsville Expressway/4500 S.

***

## Biggest Apartments (based on number of ratings)

1. **The Redwood** - 4000 S Redwood Road, WVC (3.7; 833 ratings)
2. **Callaway Apartments** - 1141 W 3900 S, Taylorsville (3.4; 641 ratings)
3. **ICO Fairbourne Station Apartments** - 2986 Lehman Ave, WVC (4.4; 621 ratings)
4. **Broadmoor Village Apartments** - 3375 W 7800 S, West Jordan (4.1; 573 ratings)
5. **Enclave at Redwood** - 3810 S Redwood Road, WVC (3.5; 551 ratings)

***

## Complexes vs. Buildings

* Apartment *complexes* have a rating **0.2** points higher than apartment *buildings* on average
* While Google isn't entirely consistent on how these are classified, complexes tend to be larger (more reviews) and generally seem to have more amenities than apartment buildings
* Size alone (number of reviews) does not coincide with any difference in ratings, however, implying that complexes have other amenities that make them stand out

***

## Top Cities/Neighborhoods

* Surprisingly, there isn't that much variation in reviews across cities or general regions of the valley, with one exception. The far southwestern corner of the valley (Daybreak/Riverton/Herriman) exclusively has highly rated apartments, though there aren't very many of them.
* There is no detectable difference in reviews along the usual east-west divide (I-15), even when ignoring the southern half of the valley.
* Similarly, there is no appreciable difference between the southern and northern halves of the valley in terms of reviews.

![Apartment Ratings by City](/assets/images/slc_apartment_ratings_by_city.png)

***

# Map

Here is an interactive map of the apartments. The sizes of the points represent number of reviews and the colors represent the overall rating.

{% include slc_apartments.html %}

***