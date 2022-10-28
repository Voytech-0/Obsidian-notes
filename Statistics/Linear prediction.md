22100709:47
Status:  #Statistics
Tags: 

# Linear prediction
We can make predictions for linear relations by extrapolating the data found. 
e.g. 
```R
lin.mod <- lm(MPG.highway ~ Horsepower, data=Cars93)
```
In which, after using `library(MASS)` we can make a linear model `lm` for *Mileage Per Gallon* in respect to *Horsepower*.
```R
summary(lin.mod)
```
will show the coefficients of the equation and 
```R
predict(lin.mod1,newdata=data.frame(Horsepower=225),interval = "prediction")
```
can show predictions for a car with 225 hp. 

---
# References