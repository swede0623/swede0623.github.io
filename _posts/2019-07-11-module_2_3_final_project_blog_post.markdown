---
layout: post
title:      "Module 2/3 Final Project Blog Post"
date:       2019-07-11 11:28:36 +0000
permalink:  module_2_3_final_project_blog_post
---

When coming up with our own hypotheses for the 2nd 3rd and 4th tests, the first thing I did was look at the ERD Diagram of Northwind's Database.  Looking over the tables and data contained in each table was the easiest way for me to try to think of things that would make for an interesting topic to look explore further.  It also made sense to start here because, at the end of the day, data is what is needed to run hypothesis tests.  So what better way to plan a good hypothesis test than to look directly at the data that is available to us.

Coming up with the initial question to which the hypothesis testing will be based on is extremely important.  Good hypotheses come from finding questions to things that people truly care about.  As this project was based in a business context, money is generally what people care about the most.  

But I think it sometimes takes time to formulate the question you will end up using as the basis of the hypothesis test.  That is why I just started first with a general topic that I thought could provide interesting information.  From there I actually used SQL to go into the database to try to flesh out what the data I was thinking about using really looked like and/or what was truly available to us.  This provides us the ability to easily start over with a new question if it turns out there is an insufficient amount of data or the tables contain data you did not expect, before you have spent more time than you would like.

If I am comfortable with the quantity (for the sake of n) and validity of the data I am seeing from my test queries this is when I finalize my question and come up with the null and alternative hypotheses for the t-test.  

This course has made me very familiar with Pandas and I enjoy working with it, so I used Pandas to display the information I received from almost all my SQL Queries.  A benefit of doing it this way was I could perform further operations on the data in Pandas that I think would have been more difficult to execute just using SQL queries.  I used the ORM SQLAlchemy but I did not end up using it's Object-Oriented Capabilities.  The SQL Queries I ended up using to source all my information were not too complex so I thought it was better in this situation to just write the SQL queries raw.

One last thing to check for before performing the hypothesis test is the distributions of your samples.  We do this because for the t-test to be reliable the data must be approximately normally distributed.  I enjoy using the Seaborn distplot() function because it also includes the kde approximation line which is helpful for visualizing the distribution beyond the histogram.  All the data in my tests were fine except for my test about the country location of the salesperson vs the customer.  Each sample had major outliers (to the positive) so I ended up dropping all the data points that were outliers.  I thought it was worth using less data for the hypothesis test than to jeopardize the validity of the t-test while using all the available data.

Luckily, doing the actual t-test to calculate the t-statistic and p-value is very easy with SciPy's different statistics testing libraries.  One thing that I ended up spending a good deal of time on, that I didn't think about before starting the project, was whether to use the Student's t-test or the Welch's t-test.  Once I figured out that using the Welch test was preferable when the samples have significant differences in variation, I had to figure out how to actually do that test using SciPy.  It turns out that the flag equal_var in the ttest_ind() method is how you toggle between the two tests.  I ended up using both types of test for my tests in this project.








