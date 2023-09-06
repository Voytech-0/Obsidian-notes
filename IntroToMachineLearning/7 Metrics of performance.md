# 7 Metrics of performance
22:12:1413:23
Status:  #MachineLearning
Tags: 

---
 **Mean Squared Error (MSE)**
	- most popular metrics for regression problems
	- Gets the average of the squared difference between the target value and the value predicted by the regression model
	- $$M S E=\frac{1}{N} \sum_{j=1}^N\left(y_j-\check{y}_j\right)^2$$
	- Due to the squaring factor it is more prone to outliers than other metrics.

**Mean Absolute Error (MAE)**
	- Average of the difference between the ground truth and the predicted truth
	- $$M A E=\frac{1}{N} \sum_{j=1}^N\left|y_j-\check{y}_j\right|$$
**Root Mean Squared Error (RMSE)**
	- MSE but squared
	- Scale is now the same as the random variable 

**R^2 Coefficient of determination**
	- The point of calculating it is to answer the questions of how much (what %) of the total variation in Y(target) is explained by the variation in X (regression line)
	- $R^2$ close to 1 indicates that the regression captures 100% of the variance of the target. Values close to 0 are worthless.
	- The range is actually $(-\infty , 1)$, not $(0, 1)$ 

**Adjusted R^2**
	- Vanilla $R^2$ metrics is prone to overfitting. 
	- It is always slower than $R^2$
	- It is adjusted to the number of independent variables

**Pearson Correlation Coefficient**
	- Shows linear relation of variables

**Kullback-Leibler Divergence**
	- Distance measure between probability distributions $p$ and $q$. The Cross-Entropy is a simplified version of the loss (with some assumptions). 

**Cosine Similarity**
	- Used to compare vectors. 
	- 
 *When to use what?*
	- MAE –when you have few or no outliers in the data, or when you want to ignore the outliers while fitting your model to the data 
	- MSE/RMSE– when you have alarge number of outliers that you want to emphasize (large penalty) while fitting your model 
	- The lower value of MAE, MSE, and RMSE implies higher performance of a regression model. However, a higher value of R square is considered desirable. 
	- R2 shows how well the data fits a curve or line. R2 increases with every predictor added to a model in the training set. As R2 always increases and never decreases, it can appear to be a better fit with the more terms you add to the model. This can be completely misleading. 
	- Adjusted R2 also indicates how well the data fits a curve or line, but adjusts for the number of variables in a model. If you add more and more useless variablesto a model, adjusted r-squared will decrease. If you add more useful variables, adjusted r-squared will increase. 

What are some classification metrics?
	- Accuracy
	- Confusion Matrix (not a metric itself but fundamental to others)
	- Precision and recall
	- F1-score
	- AUROC

**Accuracy**
	- classification only metrics with values in range \[0, 1]. 
	- *Top-k Accuracy* is a variation computes as considering any of the top k class predictions as correct.
	- *Binary Accuracy* measures how many observations, both positive and negative, were correctly classified 
		- It shouldn't be used on imbalanced problems (eg. Covid cases)
	- *Balanced Accuracy* is an accuracy adjusted for the imbalance of the dataset. 
	- It is a good metric for a balanced dataset and when every class is equally important to us. 

**Confusion matrix**
	- It is a metric that produces a matrix indicating how classes are predicted and confused with another class. 
	- For binary classification, the confusion matrix is always 2x2 and its elements are: $M=\left(\begin{array}{ll}\text { True Positive } & \text { False Negative } \\ \text { False Positive } & \text { True Negative }\end{array}\right)$

**Precision**
	- Ratio of true positives and total positives predicted:
	- It focuses on type-I errors, so False Positives. 
**Recall / Sensitivity / Hit-rate** 
	- The ratio of true positives to all the positives in ground truth. 
	- It focuses on type-II error, so false negatives.
![[7 Metrics of performance precision and recall.png]]

**Precision-Recall tradeoff (PR curve)**
	- a graph showing the relation between precision and recall, in which the higher the area under the curve, the better the model is. This area is known as the *average precision* of a model. 

**F1 score**
	- it is a special case of more general function *F beta*. It combines precision and recall into one metric by calculating the harmonic mean between those two.
	- The more we care about recall over precision, the higher beta we should choose. 
	- It should be used in every binary classification problem where you care more about the positive class

**ROC plots**
	- stands for Receiver Operating Characteristics. 
	- Y-axis: true positive rate, same as recall
	- X-axis: false positive rate, same as 1 - specificity
**Lift plot** is a derivative of ROC plot which compares the performance of the actual classifier against random ordering

---
# References