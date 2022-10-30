22100309:08
Status:  #Statistics
Tags: 

--- 

# Linear regression
	assumes that the true relationship between variables X and Y can be described by a linear equation
We can check linear regression with summary(lm(...)) which gives us the significance and linear model of the regression
	
$$ Y = \beta_0 + \beta_1 X + \epsilon $$
$Y$ is the response variable that we want to describe  
$X$ is the predictor variable that use to predict Y  
$\epsilon$ is the error term that represents unexplained variation
We assume that $\epsilon$ is normally distributed with με = 0  
$\beta_0$ and $\beta_1$ are population parameters called the regression coefficients

For a sample of paired observations we have the following: $$ y_i = \beta_0 + \beta_1 x_1 + e_i $$Our goal is to minimise the **residuals** $e_i = y_i - b_0 - b_1x_i$
	It is easy to get the sum $\sum _i e_1 = 0$
	Instead, ==minimise the residual sum of squares== $RSS = \sum e_i^2$
A hat on betas shows that these are estimates, not real values. e.q. $\hat{\beta}_1$ 

In R we can describe a model using ==tilde== ~
	y ~ x is read as 'y is modelled by x'

According to [[Central limit theorem]] $\hat{\beta_0}$ is normally distributed with $\beta_0$ 
$$variance =  \hat{\sigma}^2 = \frac{\sum_ie_i^2}{n-2} = \frac{\sum_i(y_i - \hat{\beta}_0 - \hat{\beta}_1x_i)^2}{n-2} $$
![[centralLimitTheoremForSimpleLinearRegression.png]]

We can do t-test to check whether $\beta_1$ is different from 0 with $H_0: \beta_1=0$
If we can reject the null hypothesis, there is a significant correlation

We assume that errors (residuals) are  independent of each other and the value of x

When variation in a random variable depends on the value of other factors, it is called **[[heteroskedastic]]**
also see [[homoskedastic]]


---

Regression assumes that predictors $X_i$ are linearly independent
- When predictors are **collinear**, their coefficients cannot be estimated
- Highly correlated predictors have *interdependent* estimated coefficients

Watch correlation is not causation! 

**RSS** - **Residual sum of squares** - $RSS = \sum e_i^2$ 
**total sum of squares** **STT** $SST = \sum{(y_i - \bar{y})^2}$ where $\bar{y}$ is the average $y$
**Regression sum of squares** - **SSReg** $SSReg = \sum{(\hat{y}_i - \bar{y})^2}$ 

## Coefficient of determination
The sums of squares give us an impression of how good the predictions of our model are expected to be
	The proportion of the variation in y that is explained by regression is represented by **the coefficient of determination** $$R^2 = \frac{SSReg}{SST}$$
	$R^2$ → 0 indicates that the regression model does not explain y at all 
	$R^2$ → 1 indicates that the regression model explains y almost perfectly

For a simple linear regression of y on x, the coefficient of determination equals the squared correlation between x and y $$R^2 = r^2_{xy}$$
## F-statistics
We want to test the explanatory power of the entire model at once 
H0: β1 =β2 =···=βp =0  
H1: $βi = ̸0$ for at least one 1≤i≤p

In other words: *does our model explain any variation in y?*  
We want to reject the null hypothesis if the unexplained variation RSS is small in comparison to the explained variation SSReg
# The F-statistic:

$$F = \frac{SSReg / p}{RSS / (n-p-1)}$$ Adding a new variable cannot decrease $R^2$, as if it would, we set its beta value to 0

# Anova

## One-way ANOVA
**ANalysis Of VAriance (ANOVA)** compares differences in means
Rather than having $p$ indicator variables, we divide our sample
- $y_{ij}$ is the $j_{th}$ observation of the group for treatment $i$
- E.g. $y_{12}$ is the second observation for *len* when *dose* is 1 
- $n_i$ is the number of observations for treatment $i$
$$SSReg = SSTr = \sum_in_i(\bar{y_i}-\bar{y})^2$$
$$RSS = \sum_i \sum_j(y_{ij}-\bar{y_i})^2$$

![[ANOVA.png]]

Like a t-test but for more than 2 categories

In R we can get ANOVA using:
- Note that we are taking **factor()** instead of dose itself
```R
summary(aov(len ~ factor(dose), ToothGrowth))
```
- this option gives us slightly more precise answers
```R
anova(len ~ factor(dose), ToothGrowth)
```
- This one does not assume linear regression, so we do not have to specify sth is a factor
```R
oneway.test(len ~ dose, ToothGrowth)
```

## Two-way ANOVA

	tests all indicator variables corresponding to a single categorical variable at once
```R
summary(aov(x ~ factor(y) * factor(z), data=someData
```
Make sure to use a balanced model - one with the same amount of data for both factors

---
***Adjusted $R^2$*** 
The adjusted $R^2$ modifies $R^2$ by dividing the sum of squares by their degrees of freedom$$R^2_{adj} = 1-\frac{SSReg/(n-p-1)}{SST/(n-1)}$$
The higher $R^2$, the better the model

The **Akaike Information Criterion (AIC)** and the **Bayesian Information Criterion (BIC)** use different ways of weighing explanatory power of the model against number of parameters.
	For both AIC and BIC, lower is better
**stepAIC** of the library MASS automatically removes variables to minimise the Akaike Information Criterion


# Tukey's Honestly Significant Difference (HSD) 
	tests corrects for the number of tests and returns adjusted p-value
The function `TukeyHSD` works in combination with `aov`
```R
TukeyHSD(aov(len ̃ factor(dose), data=ToothGrowth))
```

Number of rejections does not increase that much with the number of means
Tukey's HSD is only appropriate when the ANOVA has a significant result

# ANCOVA 
Analysis of covariance (ANCOVA) is an extension of ANOVA
- Includes both categorical and continuous variables
- Equivalent to multiple linear regression with indicator variables and continuous variables
- In R, ANCOVA is performed through `lm`.

# Kruskal-Wallis test
	is a nonparametric alternative to ANOVA
```R
kruskal.test(x ~ f,  data=...,  subset=...)
```
- [[Nonparametric]] data
- The Kruskal-Wallis test does not assume normality of errors
- Like the Wilcoxon rank sum test, the Kruskal-Wallis test does assume equal distribution shapes

---
# References
[[Linear prediction]]