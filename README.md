# Module 3 Project Submission

# Repository Contents

- index.ipynb - Our Jupyter Notebook containing all of our work
- README.md - This file
- data.zip -  contains the data for our project, obtained from https://www.kaggle.com/mlg-ulb/creditcardfraud
- presentation - contains a non-technical presentation for business interests

# Summary

In this project we examine the effectiveness of three models for predicting credit fraud: Logistic Regression, Support Vector Machine (SVM), and Isolation Forest. Our goal was to predict as many fraud cases as possible without generating many false positives. Our primary metric we use to judge this is our F1 score. Very little preprocessing is required as there is no missing data and most of our data has already been normalized using a PCA process.

After fitting and testing our models, we find that Logistic Regression is the best performing model, with an F1 score of .7, followed by Isolation Forest (F1 = .29), and finally our SVM model (F1 = .00). With more time and computing power, the scores of all three models could be improved greatly.

# Conclusions

It seems that there is a clear best and worst model here. The SVM model performed very poorly, perhaps due to too much noise in the data or maybe due to the extreme inbalance of the set. In its predictions, it has a high recall score because it has an extremely high false positive rate, as can be visualized in the confusion matrix above. 

The Isolation Forest model performed better, but not well. While the number of error was low (less than 1%), our model failed to predict many true negatives, and instead predicted a near equal amount of false positives and false negatives. This leads to low scores in nearly every metric.

The Logistic Regression model performed very well. It predicted 67% of our fraud cases, and mislabeled only 71 observations. With an F1 score of .7, it's safe to say that our logistic regression model is the one we would recommend. The great performance was likely aided by how clean our data set is. There was no missing data, and nearly all of the data has been normalized through PCA. This was also the least time intensive model. It took about 13 seconds to run this model, whereas the Isolation Forest took 20 seconds and the Support Vector Model took over 7 hours.

# Future Work

We believe that the performance of all three models can be improved. The largest improvement would come through feature selection using gridsearch or another method. We did not take that step in this analysis due to time constraints. With our SVM model already taking 7 hours to run, a gridsearch for feature selection would greatly increase our completion time. This could be addressed by alotting more time for completion or providing additional computing power.

Another performance boost could be attained by testing various boosting algorithms, such as adaboost or xgboosting. Our reason for not including this in our project today is the same as with gridsearch. With more time alotment or computing power, we would love to see how our models can be improved upon.