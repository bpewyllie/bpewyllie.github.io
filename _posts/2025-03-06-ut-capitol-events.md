---
layout: post
title: "Trends in Types of Events at the Utah State Capitol"
date: 2025-03-06
tags: Utah
published: True
---

There has recently been a lot of noise about protests, rallies, legislature meetings, and other types of events at the Utah State Capitol. How are things trending? What types of events are common right now, and what events have been common in the past? To answer these questions, I analyzed almost a year's worth of data from the Utah State Capitol's public events calendar.

***

# Dataset

All data was scraped from the Utah State Capitol's public events calendar: https://utahstatecapitol.utah.gov/events/. In other cases of public calendars, event data can be obtained via an .ical export, and then a simple conversion from .ical to .json. In this case, however, the Wordpress plugin used to display the calendar ([The Events Calendar](https://wordpress.org/plugins/the-events-calendar/)), limits the number of exported events to 30 events by default. So in this case, writing a simple scraper was the quickest approach.

Events prior to roughly 10 months ago appear to be archived on the Capitol events calendar. For this scrape, I've retrieved all data from June 5, 2024 through June 5, 2025 (future events are available). This gave **4,846** unique events over the period. Using the names of the events, I've placed each event into one of several categories of interest:

* Protests/Rallies
* Weddings
* Dances/Parties
* Yoga Classes
* Fashion Shows
* Other (mostly official business, but contains other miscellaneous events as well)

See the charts below to see how things have changed since last June.

***

# Event Trends

## Protests

![Protests](/assets/images/ut_capitol_protests.svg)

## Weddings

![Weddings](/assets/images/ut_capitol_weddings.svg)

## Dances, Yoga Classes, and Fashion Shows
![Dances](/assets/images/ut_capitol_misc_events.svg)

## All Other Events

![Other Events](/assets/images/ut_capitol_other_events.svg)