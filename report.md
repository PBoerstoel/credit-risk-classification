# Module 12 Report Template

## Overview of the Analysis

For this analysis we saw if we could get a model that'd tell us if a loan was "high risk" or not. A model like that would be very useful for banks, for example, since it could give the bank insight about what loans might be worth giving or not. In this way, we could help those who would stand to benefit from a loan and help mitigate loans where the recipient might not benefit or even be harmed by their inability to pay it back.

Our data was on loans given out and their riskiness. The variables we used in our predictions were as follows: Loan_size-the amount loaned out in USD, interest_rate - how much interest was on the loan; Higher meaning the additional debt on the loan will grow faster, borrower_income-how much the borrower makes per year in USD, debt_to_income-the ratio of the debt the borrower has to their income; Higher meaning they have proportionally more debt, num_of_accounts-the number of bank accounts the borrower has, derogatory_remarks-negative remarks on their banking statements. 

For our predicted values, we had data for "healthy" loans (0) and "high-risk" loans(1). The vast majority of loans in our dataset were healthy ones, with about 75000 to the 2500 high risk ones. For this analysis. We first split the data into the various variables and our target, the healthy vs high-risk loans, as well as split each of those into training and testing data. We created a logistic regression model to try to accurate predict which category a loan would fall under. We then fit it to our training data. From there we used our model to predict the state of the loans in the testing data, and compared how our model did to the actual results.

We then repeated this process but instead of just using the original data we oversampled the data, using RandomOverSampler from imblearn.

## Results


* Machine Learning Model 1:
  * This was the normally sampled data. The balanced accuracy score was about 95%, the precision score was 92% unweighted and 99% weighted, and the recall score was 95% unweighted and 99% weighted.



* Machine Learning Model 2:
  * This was the over sampled data. The balanced accuracy score was about 99%, the precision score was 92% unweighted and 99% weighted, and the recall score was 99% unweighted and weighted.

## Summary

* The oversampled model seemed to work best, with all the accuracy scores rising save for precision. That said, it should be noted that the overall scores are being brought up significantly by the sheer number of "healthy" loans, which seem to be easier to predict. If we were to only look at the performance on high-risk loans, then our precision especially drops to around 85%. This is an important thing to note because we are mostly concerned precisely with these high-risk loans. 

* It is for that reason that I am hesitant to fully endorse this model. I think it would be a useful tool for sure, even 85% precision is still high, but I don't think it should be one that's trusted to always get it right. I think it would work best not as a standalone tool, but rather another tool in the arsenal to help. Of the two models, I would recommend the over sampled model more, as it's scores were roughly the same or higher as the standard model.