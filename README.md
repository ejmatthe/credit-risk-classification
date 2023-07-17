# credit-risk-classification

## Overview of the Analysis
The purpose of this analysis was to find an effective model for predicting the riskiness of a given loan. Using the loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, total debt and "derogatory marks", we wanted to successfully and accurately predict the "loan status" as either "healthy loan" or "high-risk loan". In order to prepare and understand what our models would do, one measurement we took was "value_counts" for the "loan_status" column/variable. This tells us how many values for both outcomes (healthy or high-risking) the model will be trained on. I went through two separate models - one with the original "base" data, and another with over-sampled data. The over-sampled dataset allowed me to train the model on an equal number of "healthy" or "high-risk" outcomes, unlike the original dataset, which was overwhelmingly "healthy", and ideally, better predict both outcomes.

## Results

Once created and run, the two models provided the following results.

* Machine Learning Model 1: Using Original Data
  * The model did a very good job predicting "healthy loans" (0), with 100% of the positive predictions being correct, and 99% of positive predictions relative to the actual number of positives. With a F1 score of 1, it works very well. However, for "high-risk loans" (1), the model did not work nearly as well. It was only 85% precise (meaning 15% of the predictions were incorrect) and only 91% of correct predictions relative to the actual number. Overall, the model was 99% accurate, but had room to improve in regards to "high-risk" accuracy. 

  
* Machine Learning Model 2: Oversampled Data
  * The oversampled data set still predicts "healthy loans" (0) with high precision and recall. The changes are more noticeable for "high-risk loans" (1). The precision is not great (with only 84% of its predictions being correct), but the recall is at the high level as it is for "healthy loans". Of those confirmed to be "high-risk loans", the model correctly predicted 99% of them would be classified that way. While this model is similarly accurate overall (99%), it is ultimately less likely to generate false positives.

## Summary
Overall, between these two models, I would argue that the over-sampled model is a more reliable and effective model. It is more accurate, more precise and has better recall than the original model (the only minor exception is the precision for "high-risk loans" which drops a single percentage point in the oversampled model). Additionally, by looking at the confusion matrices, we can see that it also produces fewer false positive and false negatives combined.

However, this is assuming we want to be conservative with giving out loans. The oversampled data is more likely to produce a false negative (decide a loan is "high-risk" when it otherwise meets all the criteria for being "healthy". This is ultimately less risk for the institution, but does not provide the most accurate picture on loan health or risk.

I would feel comfortable beginning by utilizing the over-sampled tool, but would want to continue to iterate, update and check performance over time (as we receive more data) to create a better model.
