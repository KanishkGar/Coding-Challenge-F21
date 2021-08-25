# Solution

## Overall Score

- My model gave the input.txt file an overall sentiment score of 5/5.
- This is a bit surprising as there were quite a bit of words that I would associate with negative sentiment in both of the excerpts. I was expecting maybe a 3/5 or 4/5 due to the words such as "difficulty", "unhappy", or "rage". I felt that more than half of the words in input.txt was positive but not all of it. 
- One possible explanation for this is the datset that was used to train the model. I used an Amazon Musical Instruments dataset which might not have contained some of the more negative words that were present in input.txt so the model just ignored them, increasing the likelihood of higher scores. 
- Out of curiosity, I ran the model sentence by sentence to see if it would yield a different result. Surprisingly, the average score with this approach was 3.23, quite far away from the overall score of 5/5 and closer to my predicted score of 3/5 or 4/5. 
- I then looked at the frequency distribution of the scores and discovered that there were 12 5/5's, 9 1/5's, and a small number of scores in between. If the model internally used a softmax function at it's final step, then the overall sentiment score of 5/5 can be explained. The model simply looked at what class it had the highest probability for and chose it, rather than averaging scores like what I did with the sentence by sentence approach.
- Sentence score distribution: {5: 12, 1: 9, 4: 2, 2: 2, 3: 1}, average: 3.230769230769231
- This was a very interesting challenge and thanks for putting it up!

## Dataset

- Because I wanted more metrics than simply positive or negative sentiment, I decided to use an amazon reviews dataset to train the nlp model.
- Amazon reviews are rated on a 1-5 scale which allows for more precise metrics than a 0-1 scale.

## Approach to Problem

- I used a bag of words approach to solve this problem. Bag of words is a technique where the order of words in a sentence is discarded and just the frequency of different words is examined. This greatly eases the feature extraction process. 
- Because machine learning models cannot understand Strings of words by themselves, the sentences needed to be converted to a numerical representation. I first did this with CountVectorizer but later used TfidfVectorizer because it yielded better results.
- Tfidf is a technique where the comparative prevalence of words in a document is also looked at to better fit the model.
- After vectorizing the data, I used a Naive Bayes model from SKLearn to train the model.

## Sources:
- Tutorial: https://www.youtube.com/playlist?list=PLM8wYQRetTxCCURc1zaoxo9pTsoov3ipY
- Dataset: http://jmcauley.ucsd.edu/data/amazon/
- Pandas Documentation
- Numpy Documentation
- SKLearn Documentation
- https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html
- https://stackoverflow.com/questions/4455076/how-to-access-the-ith-column-of-a-numpy-multidimensional-array
- https://stackoverflow.com/questions/45346550/valueerror-unknown-label-type-unknown
- https://stackoverflow.com/questions/67795679/how-to-find-the-number-of-rows-and-columns-in-a-minmaxscaler-object/67795852#67795852
- https://medium.com/the-data-science-publication/how-to-predict-natural-language-sentiment-using-naive-bayes-classifier-6ab6eb28fd6d
