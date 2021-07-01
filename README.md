# Probability-Estimation
# The-Advantage-Over-Bookmakers
# Summary of Report
For the full report please see Probability Estimation; [The Advantage over Bookmakers pdf.](JaW02/The-Advantage-Over-Bookmakers/Probability Estimation; The Advantage over Bookmakers.pdf)

For the project notebook please see football_match_estimation.ipynb.

For the cross platform conda environment to run the notebook please see xp_environment.yml

## Introduction
When it comes to football betting there can be a lot of money to be made, bookmakers each year make hundreds of thousands if not millions on the public betting on football games. With that being said bookmakers use probability to gain advantage over the football games being bet on and this then reflects on the odds that the public get, what if we could gain some advantage back over the bookmakers. With the digital era that we are in there is no shortage of statistics being recorded for these football matches, so being able to gather and leverage this data is becoming easier and if we can estimate the probabilities for the home teams and away teams winning from the data gathered, we can stand a greater chance of gaining an advantage over the bookmakers.

## Project Outline
For this project the goal was to estimate the probabilities of winning for the home teams and away teams of football matches in the premier league, championship and league one of english football. The reasoning behind only obtaining probabilities of just winning is because the actual chance of two teams cancelling each other out for a draw is usually unlikely, it is more likely that one team underperforms, one team overperforms, either or both teams are just unlucky on the day. As we cant factor these outcomes in, predicting for a draw would be rather difficult. So the idea for this project was to create two classification models, one for modelling the estimation of home team win probabilities and one for modelling the estimation of away team win probabilities.
The metric of choice for both models was fbeta with slightly more weight towards maximising recall and minimising false negatives. This was because the distribution of classes for both models were unbalanced more so for the away win model, also because minimising false negatives allows the models to be more risk accepting as decreasing false negatives will imply increasing false positives, in this domain when minimising  predicting no win when it actually
is a win (false negatives) implies an increase in predicting win when it's actually not a win (false positives). Therefore allowing the model to make more win predictions with the risk of making win predictions when it is actually not win, allowing more risk.

## Results
It was found that for a majority class predicting baseline, the home win model produced an F-beta score of approximately 0.42 and the away win model produced an F-beta score of approximately 0.61. A simple model was produced using the most informative feature, both simple home and away win models produced an F-beta score of approximately 0.56. As can be seen due to the bigger class imbalance the away win model F-beta score decreases with the simple model showing more false positive/negative predictions. 
With the home win final model we achieved an F-beta score of approximately 0.60 which is an approximate 42% increase over the majority class predicting baseline and an approximate 7% increase over the simple model baseline. The away win final model achieved an approximate F-beta score of 0.68 which is an approximate 11% increase over the majority class predicting baseline and an approximate 21% increase over the simple model baseline. The top performing final models produced a combined expected profit of £3.74, in the long term on average we can expect £3.74 profit from betting on teams the models estimate betting on.
