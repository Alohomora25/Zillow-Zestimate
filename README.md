# Zillow-Zestimate

# Understanding the Problem

Arguably the most important step, this is probably the biggest differentiator between a mediocre data scientist and a good data scientist. Spend some time reading about this problem and the data here to get started.

I'll summarize the key points for you:

Your target variable is the log error between Zillow's estimated value for the property (Zestimate) and the actual sales price. This is significant because your model will be picking up only whatever signal Zillow's internal model for predicting home value isn't picking up on.

logerror=log(Zestimate)−log(SalePrice)

There are two types of files you need to worry about: properties which has attributes (attributes) of the properties you're trying to predict on and train which has the sale date ( transactiondate) and logerror for the sale. Your model will be of the form:

logerror≈f(transactiondate, attributes)+ϵ

The evaluation metric will be Mean Absolute Error, or the average absolute value of the difference between the predicted logerror and the true logerror.

Your goal is to predict the logerror for 6 transaction dates: October, November, and December of both 2016 and 2017.

Note that the train data comes from 2016, but we're asked to predict on 2017 data.
