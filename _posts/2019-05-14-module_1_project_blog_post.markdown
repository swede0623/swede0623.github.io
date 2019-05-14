---
layout: post
title:      "Module 1 Project Blog Post"
date:       2019-05-14 10:07:49 +0000
permalink:  module_1_project_blog_post
---


EDA

The first thing I did in this step was to check for multi-collinearity between the independent variables.  We do this because the accuracy of regression analysis depends on the assumption that each predictor only has a relationship with the target variable.  I used a correlation threshold of .76 (absolute value) and greater to determine how much collinearity was too much collinearity.  Using the heatmap method in Seaborn was a useful way to visualize the levels of collinearity present in the data.  But when deciding exactly which variables were too collinear with each other, I had to use a boolean comparison with the corr() method on the dataframe in Pandas.  It turned out that one of the features had collinearity greater than .76 with two other variables.  So we could get rid of all multi-collinearity above .76 by dropping that one column.  

The next step was to explore the distributions of each feature.  Distributions give us a sense of skewness, kurtosis, and symmetry.  These are all important parts of proving the assumptions that must be true for Regression Analysis to be accurate.  I used histograms to visualize distribution.  I used two different libraries to make the histograms, MatPlotLib using the hist() method of the dataframe, and also using SeaBorn.  The function in SeaBorn used is distplot() which has the histogram but also adds a kernel density estimate line that aids in visualization.  Both of these forms of visualizations are very helpful but I often found myself needing to find exact values that are hard to determine from a visualization.  The Pandas dataframe methods I used most often in this part of exploration were describe() and value_counts().  The describe() function helped me find outliers and the exact mean and median to help diagnose skewness and normality.  Value_counts() was helpful for the variables that had a small range of values.  Instead of having to mess around with the binsize of the histogram I could look at exactly how many of each value there was.  

The third step was to check if there was a linear relationship between each independent variable and the target.  Linearity is another example of an assumption that must hold true for Regression models to be able to make accurate predictions.  None of the visualizations we have used up until this point give us insight into linearity so we now use scatterplots to do so.  But instead of just using a regular scatter plot from MatPlotLib, Seaborn's jointplot() method complements a scatterplot with a few other plots that help us get familiar with the data all in one look.  

This Exploration step in the data science process is so important.  I used these three steps to determine which variable's had data that was too flawed to include in the model.  This is an unfortunate part of the process because you are losing precious raw data when you drop columns.  But if you include variables that have data that horribly fails the assumptions necessary for good regression, then you are tainting the valuable information you could have gotten from the data that did pass enough of the assumptions.  That would leave you with no good information from your model, which is way worse than an accurate model that only uses part of the total given data.

One other reason this step is so important is during all of the micro-analysis and visualization of each variable you are getting familiar with the data in a real sense.  The data becomes less a group of numbers, and more a picture of the story that data is meant to tell.  An example of this would be when I was exploring the independent variable, view.  Examining the distribution led me to realize that there were only 4 values to this variable and that they really didn't make much sense from a real-world perspective.  At that point I made a mental note to de-emphasize this variable because I felt that since this variable might be mislabeled or have incorrect data, I might not be able to trust it's value in predicting the target variable even if the data said it could be trusted.  Even though it might be included in the model, I would certainly shy away from drawing real conclusions about this variable's affect on the target, at least until I could find new information to make sense of what the variable was truly meant to measure.

The OSEMN process has an Exploratory step, but I assume practically any type of data science process does,  even if it may have a slightly different name.  This step was the longest and most involved of any of the steps for my King's County Housing Prices project.  But that's not surprising.  Due to it's importance I expect it to be the most involved step for many data science projects to come.




