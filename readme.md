# Prosper Loans Data Exploration
## by Ahmed Abdelhafez


## Dataset

The data consists of information regaring 114,000 loans records. There are 81 features about the loans. The selected features are 11 including the interest rate, annual percentage rate, the estimated losses and returns, the loan terms, income range, and the number of investors.
The dataset can be found [here] (https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv), 
The metadata can be found [here](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit?usp=sharing)


## Summary of Findings

In the univariate exploration I found the following:
The distribution of the interest rate and the APR are nomal like with a spike towards the tail of the distribution.
The loan Status 'Completed' ranked first status to be given followed by 'current' followed by 'chargedoff'.
There is a visible spikes in the distributions of the EstimatedEffectiveYield, EstimatedReturn and EstimatedLoss, the reason is the interpolation was mean intepolation which filled around 30,000 missing rows with the mean value which made the spike apparent.
Regarding the income ranges, the most common range was between $25,000 and $50,000 followed by $50,000 to $75,000 on the second place.
Most of the recommendations feature was the value '0' which made it hard to correlate it with other features.
The original distribution of investors was sharp right skewed, therefore, a log-normal transformation was required to see the distribution of the values in the log scale. The result distribution is unimodal with a peak around 100.
The most common term length is 36, the second is 60, and the least is 12. 

In the bivariate exploration, I found that there was a strong relationship between the interest rate and estimated return and loan term. The higher the term the higher the median rate; however, the maximum is at the 36 Term not the 60. 
There wasn't any visible relationship between the interest rates or APR with the loan status or the income range. There is no indication that a lower rates more common with "Complete" status. 
The same happens with income range, the interest rate varies accross the spectrum of income ranges without any visible trend or relationship.

Outside the main variables of interest, The Estimated Return also increases with the term value. Longer loan terms corresponds with higher returns. 
There is also a strong relationship between the lender Yield and the estimated effective yield plotted with the interest rates.

In the multivariate exploration, the BorrowerRate appeared to have stronger correlation with estimatedReturn if the term length is 36.
In the EstimatedLoss the correlation with Rate was stronger if the term length is 60.
LenderYield has a strong positive correlation with the rate accross the three terms.
The EstimatedEffectiveYield has a similar result as the LenderYield with values more scattered in the term 36.
In the last three graphs, the positive correlation between LenderYield and BorrowerRate was subject to three variables: EstimatedReturn, EstimatedLoss, and EstimatedEffectiveYield.
Higher values of estimated return is more common with the mentioned correlation, in the opposite lower values of estimated loss is more common.
The estimated Effective Yield showed direct correlation with the two plotted variables as well. 

## Key Insights for Presentation

For the presentation, I focus on the effects of term length and estimated return on the final interest rates and the annual percentage rates (APR).
Leaving out the data wrangling and cleaning process, I start with presenting the distribution of both the interest rate and the APR. 
Afterwards, I jump to the relation between the term length with both of them and demonstrate that there is a relation between the term and interest rate and nothing visible with the APR.
Finally, I finish with the scatter plot of the rate against the estimated return and showing the relation among the different terms available.

