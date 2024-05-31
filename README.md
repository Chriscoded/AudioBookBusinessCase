# Audiobooks business case
I created a machine learning algorithm based on our available data that can predict if a customer will buy again from the Audiobook company.

## Problem
You are given data from an Audiobook App. Logically, it relates to the audio versions of books ONLY. Each customer in the database has made a purchase at least once, that's why he/she is in the database. We want to create a machine learning algorithm based on our available data that can predict if a customer will buy again from the Audiobook company.

The main idea is that if a customer has a low probability of coming back, there is no reason to spend any money on advertising to him/her. If we can focus our efforts SOLELY on customers that are likely to convert again, we can make great savings. Moreover, this model can identify the most important metrics for a customer to come back again. Identifying new customers creates value and growth opportunities.

You have a .csv summarizing the data. There are several variables: Customer ID, ), Book length overall (sum of the minute length of all purchases), Book length avg (average length in minutes of all purchases), Price paid_overall (sum of all purchases) ,Price Paid avg (average of all purchases), Review (a Boolean variable whether the customer left a review), Review out of 10 (if the customer left a review, his/her review out of 10, Total minutes listened, Completion (from 0 to 1), Support requests (number of support requests; everything from forgotten password to assistance for using the App), and Last visited minus purchase date (in days).

### These are the inputs (excluding customer ID, as it is completely arbitrary. It's more like a name, than a number).

The targets are a Boolean variable (0 or 1). We are taking a period of 2 years in our inputs, and the next 6 months as targets. So, in fact, we are predicting if: based on the last 2 years of activity and engagement, a customer will convert in the next 6 months. 6 months sounds like a reasonable time. If they don't convert after 6 months, chances are they've gone to a competitor or didn't like the Audiobook way of digesting information.

The task is simple: create a machine learning algorithm, which is able to predict if a customer will buy again.

This is a classification problem with two classes: won't buy and will buy, represented by 0s and 1s.


# Preprocess
Preprocess the data. Balance the dataset. Create 3 datasets: training, validation, and test. Save the newly created sets in a tensor friendly format (e.g. *.npz)
Since we are dealing with real life data, we will need to preprocess it a bit. This is the relevant code, which is not that hard, but is crucial to creating a good model.

If you want to know how to do that, go through the code with comments. In any case, this should do the trick for most datasets organized in the way: many inputs, and then 1 cell containing the targets (supersized learning datasets). Keep in mind that a specific problem may require additional preprocessing.

Note that we have removed the header row, which contains the names of the categories. We simply want the data.
