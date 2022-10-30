22102115:04
Status:  #Statistics
Tags: 

---
![[Pasted image 20221024162508.png]]
```R
library(reshape2)
library(ggplot2)
```
`c(1,2,3,)` creates a matrix of elements 1, 2, 3

ggplot(data.frame(Nile), aes(x=Nile)) + geom histogram()

`reshape2` can be used to `melt()` data from multiple 

`rnorm(n, mean, sd)` generates `n` numbers in from the normal distribution

`sample(n:m, k)` simulates randomly choosing $k$ elements from $n$ to $m$

`replicate(n, x)` repeats $x$ $n$ times

`dbinom(x, size, prob)` probability of getting `x` elements out of `size`

`pbinom(x, size, prob)` cumulative probability of an event. Probability of getting `x` or less. Can be modified with `lower.tail = FALSE`

`qbinom(p, size, prob)` how many elements will make `p` density distribution out of `size`

`rbinom(n, size, prob)` produces `n` numbers 

`with(data, ...)`

	`prop.test(x=c(560,570), n=c(1000,1200), conf.level=0.95)` 

`subset(babies, age < 99 & dage < 99)`

`chisq.test(x=c(315,197,141,39,16,79),p=c(0.486,0.315,0.125,0.028,0.006,0.04))`
`chisq.test(x=oral.lesion, simulate.p.value = TRUE)` we can simulate p-value for a small number of observations

`with(normtemp, shapiro.test(temperature))` *shapiro test*

`predict(lm(rating ~ price * location, data), interval="prediction", level=0.99, newdata = data.frame(location=c("Inner City"), price=c(21)))`

`sapply(with(female.inc, split(income,race)), mean)`

```R
acceptableCars = c("SUV", "midsize", "subcompact")
oneway.test(Driver.deaths ~ type, data=subset(carsafety, type %in% acceptableCars))
kruskal.test(Driver.deaths ~ type, data=subset(carsafety, type %in% acceptableCars))
```

`aggregate(Other.deaths ~ type, data = carsafety, mean)`

`par(mfrow=c(2,2))` enables display of 2x2 grid of plots

`TukeyHSD(aov(size ~ species * pestcontrol, data))`

`glm(spam ̃ ., data=emails10, family=binomial)`
## bootstrapping 
- Approximates the population distribution without assumptions 
- Can be used for confidence intervals for population parameters

---

[[Stat week 4#Nonparametric test|Nonparametric tests]] vs parametric tests

[[Hypothesis testing#Type I error | Type I]] and [[Hypothesis testing#Type II error|Type II]] error

## Linear regression


---
## Revision lecture




---
# References
[[7.4 Bayesian analysis 2nd edition]]
[[8.4 Confidence intervals for differences second edition]]
[[Nonparametric]]