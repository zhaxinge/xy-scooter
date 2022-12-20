---
title: "What is happenning now in Austin and Chicago"
date: 2022-12-20
published: true
tags: [dataviz, matplotlib, altair]
excerpt: "This is an exploratory data analysis on census and scooter trip data in Austin and Chicago."
altair-loader:
  altair-chart-1: "charts/income_age_chicago.json"
  altair-chart-2: "charts/Austin_age_income.json"
toc: true
toc_sticky: true
read_time: false
---


### When will people use scooters?

#### Hourly usage analysis

![chicago_hour]({{ site.url }}{{ site.baseurl }}/assets/images/chicago_hour.png)

![austin_hourly]({{ site.url }}{{ site.baseurl }}/assets/images/austin_hourly.png)

From the weekly scooter usage, people's scooter usage patterns on weekends and weekdays are distinctly different. There are two peak periods of scooter usage on weekdays depending on the commuting time of local people, while weekend scooter usage is concentrated during the day, but there is no significant peak period. Generally speaking, the peak period of scooter use is located between 14:00-21:00 every day. 

Unlike Chicago, Austin scooter's weekend use is more than during weekdays, and the peak use of scooters in a day is nearly the same, while in Chicago scooter's hourly use fluctuates, but is mainly concentrated at around 18:00. This indicates that people in Chicago choose to use the scooter to commute in the evening, while people in Austin are likely to choose to use the scooter to commute in the evening and morning.

#### Daily usage analysis

![chicago_daily]({{ site.url }}{{ site.baseurl }}/assets/images/chicago_daily.png)

![austin_daily]({{ site.url }}{{ site.baseurl }}/assets/images/austin_daily.png)

As the figures show, between June 15 and October 15, 2019, Austin's trip count basically remained above and below the median, and it is especially noteworthy that the trip count peaked around September 7, which may be related to the city's College GameDay event, during which scooter use was nearly five times the daily use. This indicates that most tourists and people associated with the event choose to use scooter to travel during this period. In Chicago, the use of scooter is not optimistic, and the number of trips continues to decline during the pilot period. In Chicago, people's use of scooter is divided into three phases: the peak period of use from June 15 to July 15, the stable period from July 15 to September 1, and the decline period from September 1 to October 15.

#### Weekly usage analysis

![chicago_weekly]({{ site.url }}{{ site.baseurl }}/assets/images/chicago_weekly.png)

![austin_weekly]({{ site.url }}{{ site.baseurl }}/assets/images/austin_weekly.png)

These two figures also exhibit patterns of scooter usage in Chicago and Austin. There are many similarities, for example, both cities have a slowly upward trend in the usage from Monday to Friday and have the peak of the usage on Saturdays, which suggest that the scooters may mainly used for leisure. While the difference between the two cities is that the number of trips. Austin has obviously more trips than Chicago.

### Where will they use the scooter?

![chicago_scooter_line]({{ site.url }}{{ site.baseurl }}/assets/images/chicago_scooter_line.png)

![austin_scooter_line]({{ site.url }}{{ site.baseurl }}/assets/images/austin_scooter_line.png)

Scooter usage in Chicago is different from that in Austin. Generally, in Austin, scooters are more widely used as almost all the census tracts has trips of scooters, while in Chicago, the trips mainly cluster in the Northwest part of the city. On the other hand, Chicago has longer trips than Austin, as the two figures show.

## City context in Austin and Chicago

From previous studies, we can see that median age, transit mode choice, and household income are most likely to influence whether people choose to use scooter to travel, so here we compare and analyze the context of income in the two places.

###  Income and transit mode choice in Chicago

<div id="altair-chart-1"></div>

###  Income and transit mode choice in Austin

<div id="altair-chart-2"></div>


From the chart, we can see that compared to Chicago, Austin's population is relatively concentrated. The population of Chicago is mainly in the age range of 30-45, and the income is mainly in the range of 20,000-40,000. The population of Austin is mainly in the age range of 30-40, and the income is mainly around 30,000.

In terms of income and age composition, driving alone is still the main mode of travel, but there are still many people in Chicago who choose to walk and use public transportation, especially from the perspective of the main income groups in Chicago.