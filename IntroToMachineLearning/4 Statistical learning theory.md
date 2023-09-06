# 4 Statistical Learning THeory
22:12:0708:59
Status:  #MachineLearning
Tags: 

---
- What are the variables and parameters that influence the training process?
	- The number of training samples (*N*)
	- Feature dimensionality (*D*) is the length of number of dimensions of training samples
	- The number of learnable model parameters, the total number of elements of the vector / matrix W. It is typically denoted using *P*
- What are some rules of thumbs of ML?
	- The number of training samples should be 10 times the number of parameters
	- Have at least three times the number of dimensions as training samples.
- What are methods of tackling *imbalanced class data*?
	- Class weights: Assign weights to classes, so that the underrepresented class has a higher weight.
		- It is commonly done with multiplicative inverse: $w_c = \frac{N}{C_c}$ where $C_c$ is the number of samples for class $c$
		- For a very unbalanced dataset it can be smoothed with logarithmic function $W_c = \log \left( \frac{N\mu}{C_c} \right )$, where $\mu$ is the smoothing factor (by default $\mu=0.15$)
	- Sample weights: same as for class weights, but assigned individually to each sample.
- Oversampling: Transform the dataset into a balanced one, by oversampling the minority classes.
	- SMOTE: Create new synthetic samples
	- Data Augmentation: Increase the number of samples in the minority classes through data augmentation 
	- Both are only applicable to the training set (due to leakage)
- What does **Cover's theorem** points?
	- It shows that increasing the feature dimensionality improves the probability that the data points are linearly separable
	- This is the reason why  Kernel methods are used.
- What is **generalization**?
	- It is the ability to make correct predictions for inputs that are far from the training set.
	- It is generally measured by the gap between training and validation / testing set. 
- What can cause overfitting?
	- Little training data
	- model misspecification (using incorrect model)
	- Model learning from the incorrect features that do not generalize.
	- Model too large for the data available
- What is **bias** of a model?
	- An abstract measure of how well the model fits the data, comparing it to a true model f(x) (which we generally do not know)
	- Usually related to underfitting
- What is **variance** of a model?
	- Variance of the estimated model $\hat f(x)$ with respect to data, basically how well the model fits small variations to the training data
	- Usually related to overfitting 
- What is **shattering**?
	- Given a binary classifier f with parameters θ and a set of points (x1, x2, ..., xn). The classifier is said to shatter these points if for any possible (binary) labelling of these points, there is a set of parameters θ that obtains zero error
	- ![[4 Statistical learning theory shattering.png]]
- What is **VC-Dimension**?
	- Vapnik-Chervonenkis dimension D of a binary data classifier f is the maximum number of data points that can be shattered, irrespective of the actual label values of the points.
	- It basically measures how many functions can be approximated perfectly by a machine learning model.
---
# References