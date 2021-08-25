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

# ACM Research Coding Challenge (Fall 2021)

## [](https://github.com/ACM-Research/Coding-Challenge-F21#no-collaboration-policy)No Collaboration Policy

**You may not collaborate with anyone on this challenge.**  You  _are_  allowed to use Internet documentation. If you  _do_  use existing code (either from Github, Stack Overflow, or other sources),  **please cite your sources in the README**.

## [](https://github.com/ACM-Research/Coding-Challenge-F21#submission-procedure)Submission Procedure

Please follow the below instructions on how to submit your answers.

1.  Create a  **public**  fork of this repo and name it  `ACM-Research-Coding-Challenge-F21`. To fork this repo, click the button on the top right and click the "Fork" button.

2.  Clone the fork of the repo to your computer using  `git clone [the URL of your clone]`. You may need to install Git for this (Google it).

3.  Complete the Challenge based on the instructions below.

4.  Submit your solution by filling out this [form](https://acmutd.typeform.com/to/zF1IcBGR).

## Assessment Criteria 

Submissions will be evaluated holistically and based on a combination of effort, validity of approach, analysis, adherence to the prompt, use of outside resources (encouraged), promptness of your submission, and other factors. Your approach and explanation (detailed below) is the most weighted criteria, and partial solutions are accepted. 

## [](https://github.com/ACM-Research/Coding-Challenge-S21#question-one)Question One

[Sentiment analysis](https://en.wikipedia.org/wiki/Sentiment_analysis) is a natural language processing technique that computes a sentiment score for a body of text. This sentiment score can quantify how positive, negative, or neutral the text is. The following dataset in  `input.txt`  contains a relatively large body of text.

**Determine an overall sentiment score of the text in this file, explain what this score means, and contrast this score with what you expected.**  If your solution also provides different metrics about the text (magnitude, individual sentence score, etc.), feel free to add it to your explanation.   

**You may use any programming language you feel most comfortable. We recommend Python because it is the easiest to implement. You're allowed to use any library/API you want to implement this**, just document which ones you used in this README file. Try to complete this as soon as possible as submissions are evaluated on a rolling basis.

Regardless if you can or cannot answer the question, provide a short explanation of how you got your solution or how you think it can be solved in your README.md file. However, we highly recommend giving the challenge a try, you just might learn something new!

