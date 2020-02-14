---
layout: post
title:      "Interesting things from my Capstone Project"
date:       2020-02-09 20:39:24 -0500
permalink:  interesting_stuff_from_my_capstone_project
---


One of my favorite parts of doing data science projects is when you come across something surprising or just plain interesting.  I don't know exactly why, but there is just something naturally fun about seeing a result that you didn't expect, or that goes against a belief you already had.  Maybe it's just because that can be a catalyst to true learning, which is naturally so essential to the human existence.

Nonetheless, there were quite a few interesting things that stood out as I was going through my work for the Capstone and I would like to share a couple of them with you.

#1 Better Without Preprocessing?

When I started this project, one of the areas I was most excited about was cleaning the data.  There seemed to be nearly endless possibility, each little piece of unnecessary text I could remove would be a small boost to my overall score, I thought.  When researching NLP projects, I came across things that would say that preprocessing, in general, doesn't add much benefit.  But I figured that I'm pretty smart so, with enough effort, I could surely find ways to clean the data that would help my model.

Welp, it turns out my optimism towards this step of the project producing fruitful results was unwarranted.  After I built my final, best-performing model (with preprocessing), I figured I should try a "placebo" model.  To be able to show everyone how much my preprocessing did, in fact, improve my results.  I was devastated to find out that this placebo model (without any preprocessing) performed better.  All those hours spent, learning the quirks to this particular dataset so I could remove the bloat that surely could not help identify toxicity, turned out to not be for the better.

Oh well.  Though it doesn't feel great at the time, I suppose failure in data science is just as important as success.  But to be honest, if I were to do another NLP project, it's not like I wouldn't attempt data cleaning again.  It would take many times of seeing first-hand that preprocessing didn't help the final results, to get to the point where I wouldn't want to keep trying it.

#2 Improvement by Guessing?

The dataset for this project, I feel, was a little odd.  There was a huge disparity in class representation for some of the labels.  Well, actually, the class imbalances were high for all the labels but they were extremely high for 3 in particular.  The severe toxic label, the threat label, and the identity hate label.  1.1% of the comments were labeled for identity hate, .57% of the comments were labeled as severe toxic, and a staggeringly low .33% of labels were labeled as a threat.

So it turns out my best model was performing worse for these labels (but only these 3) than you would get by just predicting every comment was negative for these labels.  So that made me think, maybe I could improve my model by overriding the predictions for only these 3 labels and just use all zeros as the probabilities.  I had never done something like this before in a data science project so I wasn't sure if this type of thing worked in practice vs. only in theory.  

I only thought about this during the very end of doing the project so I only tested it once when I was submitting my predictions to Kaggle to see my score.  Changing my predictions for severe toxic, threat, and identity hate, to 0 for all comments didn't help.  My score dropped substantially, to the point where I must have been doing something wrong.  It's possible that the evaluator didn't like the zeros because were actually reporting probabilities rather than a binary prediction of 0 or 1 (because scoring was done by roc_auc_score and not accuracy).

Nevertheless, this is something I would like to explore more in general.  Is it useful, or even common, to make manual tweaks to parts of a multi-headed model that aren't performing well?  






