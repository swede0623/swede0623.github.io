---
layout: post
title:      "Bigrams vs Unigrams"
date:       2020-02-12 16:21:18 -0500
permalink:  bigrams_vs_unigrams
---


I'd like to talk for a little bit about the different results I got when doing vectorization using TF-IDF scores with both unigrams and bigrams.  This all comes from my Capstone Project, which I just completed.  The project was in the field of Natural Language Processing (NLP), where things like TF-IDF, bigrams, and unigrams are common subjects.

TF-IDF is just a way to apply scores (in the form of a number) to the words found in a text.  Basically, the higher the score, the more important that word is deemed to be in characterizing a text.  Unigrams and bigrams come into play here because TF-IDF scores can be given to individual words (unigrams) but also to sequences of 2 words in a row (bigrams).  This can also be done for sequences of 3 words, known as trigrams, and so on.  

The purpose of wanting to use a unigram instead of a bigram is more self-explanatory than the other way around.  When looking for the most important words in a text, it makes sense to want to look at each word on its own.  Because each word has it's own meaning and grouping words in pairs on average probably muddies up the meaning of the words rather than making it more clear.

But that is not always the case, which is why bigrams are an important part of NLP.  Certain pairs of words can give huge insights into the true meaning of a text.  For example, take the words "screw" and "you".  Seen individually, "screw" would most likely be interpreted as a tool for nailing.  And "you" is just an extremely common word that would give practically no insight into the meaning of a text.  But seen as the bigram "screw you", that combination of words has a totally different meaning.  If that word combo was seen even just once in a text, it would probably be safe to assume the content of that text would be combative and derogatory in nature.

*My Capstone Project dealt with classifying potential toxic comments between users on the internet so, unfortunately, this type of mean-spirited communication is not too uncommon 

The unigram results (when applied to TF-IDF) in my project were pretty straight forward.  The non-toxic comments contained words you would expect people to use when discussing Wikipedia edits like "Wikipedia", "article", and "please". The toxic comments contained mostly cuss words and similar words like "hate" and "suck".

The bigram results were more interesting though.  For the non-toxic comments, the top bigrams gave more detail to the things being discussed in the text.  "talk page", "speedy deletion", "fair use" are good examples of this.

But the top bigrams for the toxic comments were interesting in a different way.  6 of the top 10 bigrams were the same word twice.  And the other 4 were just sets of the same words but mirrored!  Thinking about this further it became clear to me that these results occurred because so many of the toxic comments were just bad or hateful words being spammed, not actual conversation.  This goes to show that toxic comments are not just defined by the words that people use but they are fundamentally different types of communication.  Toxic comments have an exponentially higher tendency to just be jumbles of bad words, often the same one or two repeated over and over.  Non-toxic comments tend to be real sentences, something that they want the other person to understand and respond back to.

Whether you are sorting by frequency or importance, unigrams and bigrams are great ways to analyze the true meaning/essence of a text.  This is why they are so helpful in NLP classification tasks.



