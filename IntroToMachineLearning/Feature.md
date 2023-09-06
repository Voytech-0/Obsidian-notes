# Feature
#MachineLearning 
- Features are a measurement, measurable property or characteristic of a phenomenon or physical object.
- The *quality* of the features is what defines the performance of your model
	- Good features will lead to good performance of your model
	- Bad features will prevent your model from making correct predictions. Model might not train at all
	- Features should be de-correlated and independent for best results. If features are related to each other, then they are redundant. 
###  Feature types:
- **Continuous**: real numbers
- **Discrete**: Integer numbers that can be ordered and countable
- **Categorical**: no order can be established

### Feature transformations 
- **Aggregation**: Mean, standard deviation, skew
- **Polynomials**: For a scalar feature x, use $x, x^2, x^3$, ..., $x^p$ The polynomial degree p is a *hyper-parameter*
- **Frequency**: Fourier transform of data is commonly used as features cut-off