22091909:07
Status:  #Statistics
Tags: 

# Hypothesis testing

## Proportion test
What is a result which we consider to be consistent with random picks?
How do we check whether people's choice of a random number between 1 and 6 was indeed random?
We know that if people pick randomly, the number of sixes in a sample of 100 people follows a binomial distribution with n = 100 and p = 1/6
	- Every outcome between 0 and 100 is possible 
	- Not every outcome is likely.

Let's say that 90% of results are probable.
	Suppose we want $P(X<b_{low}) = P(X>b_{high}) = 0.05$
```R
qbinom(0.05 , 100 , 1/6) 
[1] 11
pbinom(11 , 100 , 1/6) 
[1] 0.07771922
qbinom(0.95 , 100 , 1/6) 
[1] 23
pbinom(23 , 100 , 1/6) 
[1] 0.9621356
pbinom(23 , 100 , 1/6) − pbinom(10, 100, 1/6)
[1] 0.9194399
```

### Hypothesis testing
	is the process of contrasting two hypotheses about one or more population parameters
	
$H_0: p = p_0$
$H_1: p \neq p_0$
Given **significance level** $\alpha$ we define **critical values** for our test statistic
- Values that fall within the critical values to be consistent with the null hypothesis
- Values outside the critical values fall in the **rejection region**
- The probability of making an observation in the rejection region, assuming that the null hypothesis is true, should be $\alpha$
	- Traditionally, $\alpha = 0.05$
- If our observation falls between the critical values, we *fail to reject* the null hypothesis
	- We *never accept* a null hypothesis!
- The significance level $\alpha$ describes the maximum p-value that we consider **statistically significant**
	- If the p-value is smaller than $\alpha$, we reject the null hypothesis
	- If the p-value is larger than $\alpha$, we fail to reject the null hypothesis 

### Type I error
The level of significance $\alpha$ describes the maximum p-value that is statistically significant
The higher $\alpha$, the more often we reject the null hypothesis
$\alpha$ represents the probability of rejecting a true null hypothesis
Rejecting a true null hypothesis is called **type-I error**

### Type II error

The lower α, the less often we reject the null hypothesis (orange)
- Failing to reject a false null hypothesis is a type-II error
	- The **power** of a test is its ability to reject false null hypotheses 
- $\alpha$ balances type-I errors against type-II errors

# Proportion confidence

***Confidence intervals for population proportions***
- We use the proportion rather than the number of sixes because the population is potentially infinite
- In $C\%$ of the cases, a $C\%$ confidence interval for the population proportion will include the true population proportion p
	- Where $C = 100*(1-\alpha)$ 

- A proportion is a mean, so we can use the [[Central limit theorem]]
- The parameters $\mu$ and $\sigma$ follow from the Bernoulli distribution, where mean $\mu = p$ and variance $\sigma^2 = p(1-p)$ 
	- z* is a critical value for standard normal distribution
	- p hat is sample of proportion. Ex. we get 11 sixes in 50 trials, then p hat is 11/50

prop.test() may give different results than calculating by hand, as it does more complex calculations 

- The Wilcoxon signed rank test assumes a symmetrical distribution 
- Wilcoxon signed rank test should only be preferred over the t-test for small samples (n<10) from symmetric, but non-normal distribution
- The Wilcoxon rank sum test assumes identical distribution shapes
- The sign test assumes independent observations from a single population





---
# References