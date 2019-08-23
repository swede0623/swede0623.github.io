---
layout: post
title:      "Module 4 Project Blog Post"
date:       2019-08-23 18:00:43 +0000
permalink:  module_4_project_blog_post
---


Criteria For Determining "Best" Zip Codes

This project was about working with Time Series data and Forecasting using an ARIMA model, but I thought most of the work actually took place in having to determine the criteria to use for picking the 5 zip codes to recommend for investment.  

Even though this is obviously just a toy example, it was fun to pretend to think like an actual Financial Consultant.  To determine what I thought were the most important traits a group of data could have that would make me want to invest money in that group.  

The time period of the data was only from 1996 to 2018.  Coming up with small group of important criteria would have been more difficult if this date range was larger.  There likely would have been more trends and fluctuations that needed to be analyzed and disected.

Looking at the data, in general, it was interesting to see the overall consistent upward trend of housing prices.  Besides the recession years, housing prices almost never went down even for a single period.  I thought there would be more volatility in the housing market in terms of negative trending.  

Percentage change ended up being the statistic I used to measure 'success' in the data.  I liked using this because using percentages helped avoid dealing with raw dollar $ totals.  Since there was a huge range of the price of houses being sold in the data, looking at how many dollars a house price went up or down over time would not have been helpful.  This is because a 1 million dollar house going up $100k in a month would have been measured the same as $200k going up $100k in a month when in reality the 2nd example would have been much more impressive.  

So I used % change to make three new data points in the dataframe for each zipcode.  Each data point was to analyze the % growth (or loss) during a different time split of the existing data.  One was the total, using all years of the data.  The second was looking at just the last 5 years and the last new data point only looked at the recession years.  I thought that covered all bases in determining a successful zipcode.  

The total growth statistic would be able to weed out those zipcodes whose growth may have just been a 'flash in the pan' for a short time.  The recession statistic would weed out the zipcodes that were too volatile.  Volatility is bad because not every investor will be able to cash out of the market when they planned to so they don't want to have to take a loss if they are forced to cash out during a down period. The last 5 year period statistic would weed out zip codes who were once growing but have since stagnated.

Each criteria has importance that none of the other criteria provide so I would want to pick the zip codes that were top performers in ALL.  For example, I would not feel comfortable investing in a zip code whose houses had huge growth overall and also did relatively well during the recession but had relatively poor growth the last 5 years.  That would be a sign that housing market had reached it's maturity and even though it would have been a good investment 15 years ago it would not be a good investment today.  

I think the type of work done in this part of the project; categorizing, subsetting the data, making evaluation statistics from existing data; is important for data science in general. 






