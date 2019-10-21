---
layout: post
title:      "Mod 5 Project Blog Post"
date:       2019-10-21 13:45:34 +0000
permalink:  mod_5_project_blog_post
---


Parameter Tuning



Parameter tuning is a big part of the modeling stage of a data science process.  It can take a long time if you search through enough parameter options but it can also lead to big improvements in your model performance when you find the best group.

Being a beginner data scientist, I used the sklearn documentation page for each of the 9 models I tested for my Module 5 Project.  They have very helpful information about each of the parameters.  It's also nice that they have listed the default values for each parameter because it helped me to get a sense of the values I should try in my grid search.  We covered many of these parameters in the course material during Modules 4 and 5 but there are so many different parameters and options within those parameters that the documentation pages from sklearn were invaluable.

In a perfect world, for each model I would have loved to try all the parameters and many values within each parameter but that is just not realistic on a regular personal laptop like the one I have.  I know there is a lot of valuable information to be had from just familiarizing yourself with all the major parameters and their possible values.

In the Logistic Regression model, the parameter 'solver' is intriguing to me.  The default value and the one used almost exclusively in the coursework is 'liblinear'.  The only other one I had either seen used or I tried myself was 'lbfgs'.  So these were the only 2 options I tested during my grid search.  I would have loved to try the other three possible values 'sag', 'saga', and 'newton-cg'.  This solver parameter just strikes me as something that could be really important to the implementation of this algorithm.  So I would be really interested to see if these were significantly better or worse than the two options I used.  For the record, lbfgs was the optimal parameter for my dataset.

Because of the limited number of choices, both in parameters and values of each parameter, I could use in my grid search, it was important to me to try to locate what I thought might be the top 2 or 3 most 'important' parameters for each model.  I assumed that those parameters would have the greatest positive impact on the model performance if the correct values were tested.

The K Nearest Neighbors model had, I believe, the 2nd longest runtime of any of the nine models I tried.  So I ended up only testing one parameter: 'n_neighbors'.  The default value was 5 so I tested that and three other values increasingly greater: 25,50, and 100.  100 turned out to be the optimal parameter for my dataset.  I wonder if I kept trying increased values if those would have been picked as 'optimal'.  I felt comfortable leaving the 'algorithm' parameter as the default of 'auto' because it automatically tries to pick the best option according to the data you passed to the fit() method.  But it would have been nice to explicitly try to test each of the three algorithm options: 'ball_tree', 'kd_tree', and 'brute'.  I wonder if testing the value 'brute' could lead to exorbitant runtimes based on the nature of its name.  One day I hope to find out.

Almost half of the models I tried were tree-based.  There was the basic decision tree algorithm and then I used a few tree-based ensemble methods as well.  So I saw the parameter option 'max_depth' a lot.  I remember at least one instance of being amazed at how much power that parameter had to affect the performance of the model.  I don't recall specifics as I was just tinkering around at the time.  The Decision Tree Classifier had the largest difference between baseline and optimized performance and I wouldn't be surprised if the optimization of that parameter max_depth was the cause.  Next time I will be sure to look into that more carefully.

This was my first real project where I was doing the parameter optimization process all on my own.  I look forward to trying again soon.







