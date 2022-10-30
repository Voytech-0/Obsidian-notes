22092608:58
Status:  #Statistics
Tags: 

# Stat week 4
## Non-normality
- In [[Central limit theorem]], performing t-test with $\alpha=0.05$ we accidentally reject one in 20 correct null hypotheses.
- Outliers can strongly affect $sd$ of the distribution.

-   Logarithmic transform
	- Taking a logarithm of a distribution can reduce skew to the right
	- It is often done for variables that cannot be negative
-   **Shapiro-Wilk test** for normality.
	- Used when we want to check whether a population is normally distributed. 
	- It tests population distribution, not the population mean.
	- A significantly non-normal distribution does not invalidate the t-test. 
	- A result of p-value < 0.05 means we can reject the null hypothesis and the sample does not follow normal distribution.
	- Probability of rejecting the normal distribution goes up with the sample size. 

## Nonparametric test
### Sign test
- t-test is mostly vulnerable to outliers and skew
- We could base our method on median to limit the influence of outliers
- A random variable different from median m should follow a binomial distribution with n = n and p = 0.5
- The sign test only uses the sign of the sample observations
	- It reduces assumptions on the distribution
	- But also removes information about the spread 
- The likelihood of rejecting null hypothesis is lower for sign test than t-test, as type II error is higher for sign test.

### Wilcoxon signed rank test
- Let's assume that distribution is symmetric
	- It is not as strong an assumption as normality
	- Due to symmetry P(X − m > x) = P(X − m < x) for all x.
- Let $x_1, x_2, x_3, ... , x_n$ be our sample.
- Place those observations in order of (absolute) distance to the hypothesised median $m_0$. 
- Calculate the sum T of these ranks for the observations that are higher than m_0
- Under the null hypothesis, T should be about half the sum of all ranks.

### Wilcoxon rank sum test
- For the Wilcoxon signed rank test, we split our sample 
	- Observations below the median  
	- Observations above the median
- We could also use this method for two independent samples .
	- We no longer assume symmetry  
	- Instead, **we assume that both samples are drawn from populations with the same distribution shape**
### Chi-squared test of independence
	If you want to know whether two variables are independent, you put them together in a frequency table to then perform a χ2-squared test. This table is obtained through xtabs(∼ var1 + var2). For the χ2-squared test of ind pendence, your H0 is that the two variables are independent of each other and are not related. The HA is that the variables are dependent. The output of chisq.test(table) function will be a p-value that allows you to decide whether to reject the null hypothesis or not.

```R
chisq.test(table(dat$Species, dat$size))
```

Works on paired samples X and Y of categorical data

### Chi-squared goodness of fit test
Sometimes you want to know whether given proportions are statistically different from the sample proportions. For example, if you want to know whether a die is fair, the given proportions are all 1/6. If you then measure the proportions of each rolled number for, say, 100 die rolls, you can test if these pro- portions are significantly different from 1/6 as follows: `chisq.test(x, p = rep(1/6, times=6))` with x being a data vector with the measured proportions.
```R
chisq.test(x, p=...)
```
The data is given in tabulated form in `x`; the null hypothesis is specified with the argument `p` as a vector of probabilities. 


---
# References