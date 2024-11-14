---
layout: post
title: "The most common areas for car accidents in SLC and the rest of the state"
date: 2024-11-13
tags: Utah
published: True
---

When one or more vehicles get in a major accident in Utah, police officers file reports with details of the crash. This means that the state has pretty comprehensive data when it comes to car crashes throughout the state. I used this data to analyze the most "dangerous" locations in Salt Lake County and the rest of the state.

***

# Dataset

There are two datasets used in this analysis, one for crash statistics and another for road geometries (used to pinpoint the exact locations of crashes):

* Crash Data - from the [Utah Department of Public Safety's data dashboard](https://udps.numetric.net/utah-crash-summary#/?view_id=7)
* Utah Roads - from the [Utah Automated Geographic Reference Center](https://opendata.gis.utah.gov/datasets/utah-roads/about)

The crash data provides details on car accidents anywhere in the state that are documented by law enforcement officers in crash reports. According to the [Highway Safety Office](https://highwaysafety.utah.gov/crash-data/), these reports are filled out "when a crash involves injuries, deaths, or at least \$2,500 in property damage." Therefore, many crashes are never officially reported. This dataset contains details on over **800,000** crashes since 2010.

Due to limitations in the crash data, I can only pinpoint crash locations for UDOT-managed roads. These are flagged in the Utah Roads dataset above with their own field.

## Methods

I used Google BigQuery's geospatial functions to merge and analyze the two datasets. As the crash data records provide only estimated locations (mile markers along state and federal routes in some instances, rough coordinates in others), I also use the Utah Roads dataset mentioned above. This dataset contains over **400,000** "segments" of state and federal routes (think of a segment as a short, straight section of a longer road). 

Using mile markers from the crash data and a mapping of milepoints to coordinates in the roads data, I'm able to pinpoint the exact location of crashes that occurred on state or federal routes (i.e, routes managed by UDOT). To summarize the locations, I round the coordinates to 4 decimal places (about 11 meters of precision at the equator).

***

# Findings

*Unless otherwise specified, all rankings consider locations on roads that are managed by UDOT in Salt Lake County only.* 

### Most Dangerous Locations based on Number of Accidents 

1. [I-15 North just after the merge of the 5300 S on-ramp in Murray](https://maps.app.goo.gl/Yd7gp7d9k4rEzrTq7) - 1,142 accidents
2. [I-15 North just before the 9000 S off-ramp in Sandy](https://maps.app.goo.gl/zapU8CbtGrxT31GB6) - 1,100 accidents
3. [I-15 North just after the merge of the 3300 S on-ramp in South Salt Lake](https://maps.app.goo.gl/dEV34XHb22CCsCB78) - 952 accidents
4. [I-15 North just after the merge of the 7200 S on-ramp in Midvale](https://maps.app.goo.gl/R35opyq3dgW3JmBGA) - 945 accidents
5. [I-15 South just before the merge of the 7200 S on-ramp in Midvale](https://maps.app.goo.gl/nfwrV2L2zvxLjm1r9) - 932 accidents

### Traffic-Adjusted 
*Minimum 1000 cars of traffic per day and at least 50 crashes in the sample. Accidents are adjusted based on [Annual Average Daily Traffic (AADT)](https://www.udot.utah.gov/connect/business/traffic-data/traffic-statistics/), a measure of the average number of cars to pass through a segment of road on a typical day.*

1. [Porter Rockwell Blvd near Life Dr in Bluffdale](https://maps.app.goo.gl/aXBMPZtjxsuzYX8r5) - 52 accidents; 1,000 AADT
2. [Redwood Road near 3395 S in West Valley City](https://maps.app.goo.gl/yw5sivgkz7RCY8h68) - 300 accidents; 25,000 AADT
3. [Redwood Road near 3860 S in West Valley City](https://maps.app.goo.gl/fTwXzRAPCxp8Ue6p8) - 416 accidents; 35,000 AADT
4. [3500 S 5450 W in West Valley City](https://maps.app.goo.gl/xaQHLVgx9jsMSNQD7) - 238 accidents; 21,000 AADT
5. [3400 S 1400 W in West Valley City](https://maps.app.goo.gl/YvuWLUNcuz2DpdpL6) - 301 accidents; 33,000 AADT

### Fatalities
*All of the following locations have had 3 fatalities recorded over the data period. No other locations have had 3 fatalities or more.*

1. [Bangerter Highway at 2100 S in West Valley City](https://maps.app.goo.gl/QNm2GpC3eQDbsYDa6)
2. [I-80 on the western end of the 7200 W on- and off-ramps in Salt Lake City](https://maps.app.goo.gl/uA6B9YsTi4KsRbV29)
3. [Mountain View Corridor at 3500 S in West Valley City](https://maps.app.goo.gl/hikDykdW7CzheYpp7)
4. [Redwood Road near 3860 S in West Valley City](https://maps.app.goo.gl/fTwXzRAPCxp8Ue6p8)
5. [I-80 near the Lambs Canyon exit](https://maps.app.goo.gl/4Lf7JjQgPjceHdAM9)

### Intersections
*Locations designated as "intersections" only*

1. [Redwood Road and 5400 S in West Valley City](https://maps.app.goo.gl/wKg3MYSfC7RjjaQs6) - 270 accidents
2. [State St and 4500 S in Murray](https://maps.app.goo.gl/nwzTp8ZK6M4aRG3F9) - 262 accidents
3. [Bangerter Hwy and 3500 S in West Valley City](https://maps.app.goo.gl/mPfJgeT9MuBgW8BE9) - 232 accidents
4. [State St and Edison St (just north of 4500 S) in Murray](https://maps.app.goo.gl/tPhEseqAJdyKD5GA8) - 223 accidents
5. [9000 S and Tiny Wood Dr (lol, just west of State St) in Sandy](https://maps.app.goo.gl/AKmHbQAWi1tfdn9FA) - 216 accidents

### Non-SL County
*Locations on UDOT-managed roads outside of Salt Lake County only, traffic-adjusted*

1. [Cedar Fort Rd and Mt Airey Dr in Eagle Mountain](https://maps.app.goo.gl/3jvfBGjrs8uzpowG9) - 62 accidents; 4,000 AADT
2. [1900 W and 5600 S in Roy](https://maps.app.goo.gl/J7LXbvwtEe72VMtY8) - 319 accidents; 22,000 AADT
3. [I-15 at the border with Arizona, right by the "Welcome to Utah" sign](https://maps.app.goo.gl/hmYnYknFTbW1R7N27) - 288 accidents; 23,000 AADT
4. [Main St and 1200 S in Heber](https://maps.app.goo.gl/rekXaNcpUWgMxNcV9) - 99 accidents; 8000 AADT
5. [Center St and Redwood Rd in North Salt Lake](https://maps.app.goo.gl/fqsg9f8oXRsfg9647) - 135 accidents; 11,400 AADT

***

# Conclusion / TL;DR

Avoid I-15, Redwood Road, and most major roads in West Valley